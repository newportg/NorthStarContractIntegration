# 3, System Scope and Context

## Business Context

An internal user will not notice any change to the use or performance of the hub application. Nor will they know where their contact information is being mastered.

![image](http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/newportg/NorthStarContractIntegration/master/plantuml/BusinessContext.puml)

## Technical Context

![image](http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/newportg/NorthStarContractIntegration/master/plantuml/TechnicalContext.puml)


* The Filter Service runs as a microservice on our cloud platform, and will be accessible via a API Management interface.
* The data passed in this application is sensitive and should not pass outside of our network.
* Passing data between resources will follow our security and encryption guidelines.
* A service bus interface will be used to guarantee delivery of data.

