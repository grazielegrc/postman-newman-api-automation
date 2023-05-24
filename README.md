# Introduction 
This project have been created in order to demonstrate API tests automation using Postman collections and Newman as test runner. Besides that, there is an example using templates to create Azure pipelines including schedulers triggers.

# Pre-requisites
- [Node.js](https://nodejs.org/en/)

# How to run locally

## Setup
- Clone or download the project
- Import the project into VSCode or other IDE

## Installation
After installing Node.js, install Newman using the command:

```bash
npm install -g newman
```

## Run tests
Go to project root and to run viacep api tests:
```bash
apiTests/viacep/viacep.postman_collection.json -e apiTests/viacep/viacep.postman_env.json -r cli
```
To run zipcode api tests:
```bash
apiTests/zipcode/zipcode.postman_collection.json -e apiTests/zipcode/zipcode.postman_env.json -r cli
```
The argument (-r cli) at the end is to print the test results in the terminal.

## To generate Newman report
Install Newman report:
```bash
npm i -g newman-reporter-htmlextra
```
Execute the tests passing the argument (-r htmlextra) at the end of the run command, as below:
```bash
newman run apiTests/viacep/viacep.postman_collection.json -e apiTests/viacep/viacep.postman_env.json -r htmlextra
```
A folder named newman containing the html report will be generated in the project root.

## To generate Allure report
Install Allure report:
```bash
npm i -g newman-reporter-allure
```
Execute the tests passing the argument (-r allure) at the end of the run command, as below:
```bash
newman run apiTests/viacep/viacep.postman_collection.json -e apiTests/viacep/viacep.postman_env.json -r allure
```
A folder named allure-results containing some files will be generated in the project root. On project root, run allure-commandline to open the report:
```bash
allure serve allure-results
```
A local server will be started and the reporter will be opened in your browser.

# Pipeline
You can use the azure-pipelines.yml localized under .pipelines folder as example to create an Azure pipeline.
