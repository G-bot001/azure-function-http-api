# Serverless HTTP API with Azure Functions

A simple serverless HTTP API built with *Azure Functions and Node.js.* The project demonstrates how to create, run, and deploy an HTTP-triggered function to Microsoft Azure.

# About the Project

This project is a small serverless application that exposes an HTTP endpoint using Azure Functions. When the endpoint is accessed, the function processes the request and returns a simple response.

The project was developed locally using Azure Functions Core Tools and Azurite, then deployed to Azure using the *Flex Consumption* hosting model.

## Technologies Used

* JavaScript (Node.js) — application runtime and function code
* Azure Functions — serverless compute platform
* Azure Functions Core Tools — local development and deployment
* Azure Storage — storage used by the Function App
* Azurite — local Azure Storage emulator
* Azure Flex Consumption — hosting model for the deployed Function App
* Application Insights — application monitoring
* Git & GitHub — version control and project hosting

## How It Works

The application uses an HTTP-triggered Azure Function called `greatTrigger`.

When a request is sent to the function's HTTP endpoint:

1. The request reaches the Azure Function.
2. The `greatTrigger` function is executed.
3. The function processes the request.
4. It returns a response to the client.

The function can be run locally during development using Azure Functions Core Tools and can also be accessed through its deployed Azure endpoint.

### Example Response

Hello, Great!

## Live API

The function has been deployed to Microsoft Azure and is publicly accessible through the following HTTP endpoint:

*Endpoint:* `https://functionapp55.azurewebsites.net/api/greattrigger`

A successful request returns:

Hello, Great!

## Running Locally

### Prerequisites

Before running the project locally, install:

* [Node.js](https://nodejs.org/)
* [Azure Functions Core Tools](https://learn.microsoft.com/azure/azure-functions/functions-run-local)
* [Azurite](https://learn.microsoft.com/azure/storage/common/storage-use-azurite)

### Setup

Clone the repository:

```bash
git clone https://github.com/G-bot001/azure-function-http-api.git
cd azure-function-http-api
```

Install the project dependencies:

```bash
npm install
```

Start Azurite to provide local Azure Storage services, then start the Azure Functions host:

```bash
func start
```

The function should then be available locally at:

http://localhost:7071/api/greatTrigger

Send a request to the endpoint to test the function.

### Local Response

A successful request returns:

"Hello, Great!"

## Project Structure

```text
azure-function-http-api/
│
├── src/
│   ├── functions/
│   │   └── greatTrigger.js
│   └── index.js
│
├── .funcignore
├── .gitignore
├── host.json
├── package.json
├── package-lock.json
└── README.md
```

### Key Files

| File / Directory                | Purpose                                                                 |
| ------------------------------- | ----------------------------------------------------------------------- |
| `src/functions/greatTrigger.js` | Contains the HTTP-triggered Azure   Function                              |
| `src/index.js`                  | Entry point for the application                                         
| `host.json`                     | Contains configuration settings for the Azure Functions host            
| `package.json`                  | Defines the Node.js project and its dependencies                        
| `package-lock.json`             | Records the exact dependency versions installed                         
| `.funcignore`                   | Specifies files that should be excluded when deploying the Function App 
| `.gitignore`                    | Specifies files that Git should not track                               
| `README.md`                     | Project documentation                                                   






