build:## Generate the website from the markdown and configuration files in the directory dist/.
	@hugo --destination ./dist

clean:## Cleanup the content of the directory dist/.
	@rm -Rf ./dist

post:## Create a new blog post whose filename and title come from the environment variables POST_TITLE and POST_NAME.
	@rm -Rf /content/posts/$(POST_NAME).md
	@hugo new posts/$(POST_NAME).md
	@sed -i 's+title.*+title: "$(POST_TITLE)"+g' content/posts/$(POST_NAME).md

package:## Produces a file awesome-website.zip, containing the binary awesome-api and the directory dist/ directory
	@hugo
	@zip awesome-website.zip ./dist

lint:## Lint markdown
	@markdownlint README.md
	@markdownlint DEPLOY.md

unit-tests:## Unit tests

integration-tests:## Integrations test

validate:## Validate file

help:## Prints out the list of targets and their usage.
	@fgrep -h "##" $(MAKEFILE_LIST) | fgrep -v fgrep | sed -e 's/\\$$//' | sed -e 's/##//'
