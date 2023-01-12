build:
	hugo --destination ./dist

clean:
	rm -Rf ./dist

post:
	@rm -Rf /content/post/$(POST_NAME).md
	hugo new post/$(POST_NAME).md
	sed -i 's+title.*+title: "$(POST_TITLE)"+g' content/post/$(POST_NAME).md