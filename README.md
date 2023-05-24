# Introduction 
This project have been created in order to demonstrate API tests automation using Postman collections and Newman as test runner. Besides that, there is an example using templates to create Azure pipelines including schedulers triggers.

# Pre-requisites
- [Node](https://nodejs.org/en/)

# How to run locally
## Installation
After installing node, install Newman using the command:

```bash
npm install -g newman
```

## Run tests
Navigate to project folder that contains the collection and environment files, then:
- If you are not using the environment variable, run:

```bash
newman run <your_postman_collection.json> -r cli
```

- If you are using environment variable, run:
```bash
newman run <your_postman_collection.json> -e <your_environmentfile.json> -r cli
```
The argument (-r cli) at the end is to print the test results in the terminal.

## To generate Newman report
Install Newman report:
```bash
npm i -g newman-reporter-htmlextra
```
Execute the tests passing the argument (-r htmlextra) at the end of the run command:
```bash
newman run apiTests/viacep/viacep.postman_collection.json -e apiTests/viacep/viacep.postman_collection.json -r htmlextra
```
A folder named newman containing the html report will be generated in the project root.

## To generate Allure report
Install Allure report:
```bash
npm i -g newman-reporter-allure
```
Execute the tests passing the argument (-r allure) at the end of the run command, as below:
```bash
newman run apiTests/viacep/viacep.postman_collection.json -e apiTests/viacep/viacep.postman_collection.json -r allure
```
A folder named allure-results containing some files will be generated in the project root. On project root, run allure-commandline to open the report:
```bash
allure serve allure-results
```
A local server will be started and the reporter will be opened in your browser.

# Pipeline
You can use the azure-pipelines.yml localized under .pipelines folder as example to create an Azure pipeline.
