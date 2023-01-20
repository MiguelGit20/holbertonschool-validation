build: ## Compile the source code of the application to a binary named awesome-api.
	make lint
	go build

run: ## Run the application in background by executing the binary awesome-api.
	./awesome-api >./awesome.log 2>&1 &.

stop: ## Stop the application with the command kill.
	kill $(shell pgrep awesome-api)

clean: ## Delete the binary awesome-api and the log file awesome-api.log.
	-make stop
	-rm ./awesome-api awesome.log

test: ## Testing to ensure that it behaves as expected.
	curl http://localhost:9999
	curl http://localhost:9999/health

lint: ## Lints all the go files using golangci-lint.
	golangci-lint run

unit-tests:	## Runs implemented unit test using go test.
	go test -v -short -coverprofile=coverage-units.out

integration-tests: ## Runs integration test using go test.
	go test -v -coverprofile=coverage-integrations.out

help: ## Show commands help.
	@fgrep -h "##" $(MAKEFILE_LIST) | fgrep -v fgrep | sed -e 's/\\$$//' | sed -e 's/##//'
