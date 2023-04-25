# azure-devops-demo
A demonstration using @cyberark Conjur's Azure DevOps Pipelines integration

## Setup

* Download Conjur Azure DevOps Extension from Azure Marketplace
* Install the extension to an Azure DevOps organization
* Search for installed extension in Project Settings > Pipelines > Service connection > Create service connection

![image](https://github.com/Nirupma-Verma/AzurePipeline/blob/main/images/service-connection.png?raw=true)

* Add the Conjur details in Service Connection 

![image](https://github.com/Nirupma-Verma/AzurePipeline/blob/main/images/setupSC.png?raw=true)

* In Pipeline > Task > Search with Batch Secret Retrieval > Select the Service Connection and provide path of secrets.yml file

![image](https://github.com/Nirupma-Verma/AzurePipeline/blob/main/images/pipelineTask.png?raw=true)

## How it works

The Conjur Service Connection contains all the connection and secret information needed to securely retrieve a secret just-in-time from Conjur.  The secret value is then presented to the running pipeline as an environment variable defined within the service connection.  You may reference that variable from within the pipeline script to utilize the secret.

## License

[MIT](LICENSE)


