# azure-devops-demo
A demonstration using @cyberark Conjur's Azure DevOps Pipelines integration

## Setup

* Download Conjur Azure DevOps Extension from Azure Marketplace
* Install the extension to an Azure DevOps organization
* Search for installed extension in Project Settings > Pipelines > Service connection > Create service connection

     <img src="https://github.com/Nirupma-Verma/AzurePipeline/blob/main/images/service-connection.png" width="300" height="300">

* Add the Conjur details in Service Connection 

     <img src="https://github.com/Nirupma-Verma/AzurePipeline/blob/main/images/setupSC.png" width="400" height="500">

* In Pipeline > Task > Search with Batch Secret Retrieval > Select the Service Connection and provide path of secrets.yml file

     <img src="https://github.com/Nirupma-Verma/AzurePipeline/blob/main/images/pipelineTask.png" width="500" height="500">

* Once the task added, under steps in azure-pipeline.yml 

```yaml
steps:
- task: secretBatchRetrievalConnector@0
  displayName: ConjurIntegeration
  inputs:
    ConjurService: 'ConjurSConnection'
    secretsyml: './secrets.yml'
```

## How it works

The Conjur Service Connection contains all the connection and secret information needed to securely retrieve a secret just-in-time from Conjur.  The secret value is then presented to the running pipeline as an environment variable defined within the service connection.  You may reference that variable from within the pipeline script to utilize the secret.

## License

[MIT](LICENSE)


