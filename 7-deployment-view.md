# 7, Deployment View

![image](http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/newportg/NorthStarContractIntegration/master/plantuml/DeploymentView.puml)

## Security

The application is accessed by Internal web applications.

* Internal are within the Knight Frank network.
* Not accessible from the public internet.
* Managed Identity will be used between APIM and the Azure Function Service.
* The Azure Function will validate the MI token.

## Application

* The Application resource group will contain the usual components for a microservice.
* The components will follow our naming convention.

| Component            | Name                  |                                                |
| -------------------- | --------------------  | ---------------------------------------------- |
| Azure Function       | func-nscontact-env-ne |                                                |
| Application Insights | appi-nscontact-env-ne |                                                |
| Storage Account      | stNsContactEnvNe      | Camelcase for readability, should be lowercase |
| Key Vault            | key-nscontact-env-ne  |                                                |

**N.B. Env should be changed to match the deployment environment.**

The Application will be registered in Active Directory (Entra).

## DataStore.

* Hub uses a Sql database as its contact store.
* NorthStar is a Dynamics application.
