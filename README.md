# Serverless HTTP API with Azure Functions

A simple serverless HTTP API built with **JavaScript, Node.js, and Azure Functions**. This project demonstrates how to develop, run, test, and deploy an HTTP-triggered function on Microsoft Azure.

## About the Project

This project exposes an HTTP endpoint through an Azure Function named `greatTrigger`. When a client sends a request to the function, it returns a simple text response.

The application was developed locally using Azure Functions Core Tools and Azurite, then successfully deployed to Microsoft Azure using the Flex Consumption hosting model.

The Azure resources have since been removed to avoid unnecessary ongoing costs. The source code remains available in this repository.

## Technologies Used

* **JavaScript (Node.js):** Application runtime and function code
* **Azure Functions:** Serverless compute platform
* **Azure Functions Core Tools:** Local development and deployment tools
* **Azure Storage:** Storage services used by the Functions runtime
* **Azurite:** Local Azure Storage emulator
* **Azure Flex Consumption:** Hosting model used for the original deployment
* **Application Insights:** Monitoring service used during deployment
* **Git and GitHub:** Version control and source code hosting

## Architecture

The application follows a simple request-response flow:

Client
  |
  | HTTP Request
  v
Azure Functions Host
  |
  v
greatTrigger Function
  |
  | HTTP Response
  v
Client

During local development, Azure Functions Core Tools runs the Functions host, while Azurite provides local Azure Storage services.

## How It Works

1. A client sends an HTTP request to the `greatTrigger` endpoint.
2. The Azure Functions host routes the request to the function.
3. The function executes its JavaScript code.
4. The function returns a text response to the client.

### Example Request

GET /api/greatTrigger HTTP/1.1
Host: localhost:7071

### Example Response

Hello, Great!

The example above represents the function's local endpoint. The hosted Azure endpoint is no longer active because the Azure resources have been removed.

## Running Locally

### Prerequisites

Install the following tools:

* [Node.js](https://nodejs.org/)
* [Azure Functions Core Tools](https://learn.microsoft.com/azure/azure-functions/functions-run-local)
* [Azurite](https://learn.microsoft.com/azure/storage/common/storage-use-azurite)

### Setup

Clone the repository:

git clone https://github.com/G-bot001/azure-function-http-api.git
cd azure-function-http-api

Install the dependencies:

npm install

Ensure the local Azure Functions settings are configured in `local.settings.json`, including the appropriate storage connection and worker runtime settings for this project. This file is intentionally excluded from Git because local settings may contain sensitive configuration.

Start Azurite in a separate terminal. Then, from the project directory, start the Functions host:

func start

When the host starts successfully, test the function at:

`http://localhost:7071/api/greatTrigger`

You can open the URL in a browser or send a GET request using a tool such as `curl`:

curl http://localhost:7071/api/greatTrigger

Expected response:

Hello, Great!

### Troubleshooting

* If the Functions host cannot connect to local storage, check that Azurite is running and that `AzureWebJobsStorage` is configured correctly.
* If port `7071` is already in use, stop the other process or configure a different local port.
* If the function does not load, check the terminal output and verify that the dependencies are installed.

## Project Structure

azure-function-http-api/
├── src/
│   ├── functions/
│   │   └── greatTrigger.js
│   └── index.js
├── .funcignore
├── .gitignore
├── host.json
├── package.json
├── package-lock.json
└── README.md

### Key Files

| File or Directory               | Purpose                                             |
| ------------------------------- | --------------------------------------------------- |
| `src/functions/greatTrigger.js` | Contains the HTTP-triggered function                |
| `src/index.js`                  | Entry point for function registration               |
| `host.json`                     | Configures the Azure Functions host                 |
| `package.json`                  | Defines project metadata, scripts, and dependencies |
| `package-lock.json`             | Records the resolved dependency versions            |
| `.funcignore`                   | Specifies files excluded from deployment            |
| `.gitignore`                    | Specifies files Git should ignore                   |
| `README.md`                     | Documents the project and setup process             |

## Azure Deployment

The application was successfully deployed to Microsoft Azure using the Flex Consumption hosting model. During the deployment, the HTTP-triggered function was publicly accessible and returned `Hello, Great!`.

The Azure resources have since been deleted to avoid unnecessary ongoing resource usage and costs. Consequently, there is currently no live hosted endpoint.

The project can be deployed again by provisioning the required Azure resources and following the appropriate deployment steps.

## What I Learned

Through this project, I gained practical experience with:

* Building an HTTP-triggered serverless function using Node.js
* Running Azure Functions locally with Azure Functions Core Tools
* Using Azurite to emulate Azure Storage during development
* Configuring a local development environment
* Deploying a function to Azure
* Troubleshooting runtime and deployment issues
* Tracking source code and changes with Git and GitHub
* Documenting a project for other developers

## Future Improvements

Planned improvements include:

* Adding automated tests
* Implementing continuous integration and deployment with GitHub Actions
* Provisioning Azure resources using Terraform
* Improving logging, monitoring, and error handling
* Extending the API to process input and return structured JSON responses

## Author

**David Olagunju**

GitHub: [G-bot001](https://github.com/G-bot001)