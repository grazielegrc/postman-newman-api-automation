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
newman run <your_postman_collection.json>
```

- If you are using environment variable, run:
```bash
newman run <your_postman_collection.json> -e <your_environmentfile.json>
```

# Pipeline
You can use the azure-pipelines.yml localized under .pipelines folder as example to create a Azure pipeline.