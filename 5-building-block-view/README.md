# 5, Building Block View

![image](http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/newportg/NorthStarContractIntegration/master/plantuml/BuildingBlockView.puml)


This service has been designed to pass contacts to/from the NorthStar CRM system. Hub will pass all new and updated contacts via this service, this service will then pass a subset onto NorthStar CRM. This subset will slowly increase until NorthStar CRM has consumed all of the active contacts from within hub.
Any contact that is consumed by the NorthStar CRM will be mastered with NorthStar.
The filter service will pass processed contacts back to hub, so its database can be made consistent with NorthStar CRM.


### Contained Building Blocks

| **Name**                 | **Responsibility**                                                                       |
| ------------------------ | ---------------------------------------------------------------------------------------- |
| Azure Function           | Is the interface to all systems. provides both Restful API and Service Bus Interfaces.   |
| Security Component       | Provides all Managed Identity and User Identity/Access controls                          |
| Domain Logic Component   | Provides rules and workflow to satisfy the requirements of this service                  |

### Azure Function

The Azure Function wrapper will interact with the Azure Service Bus interfaces.

## Components

The component libraries should be general and built so they can be copied or included in other projects.

### Security Component

This component will validate the Managed Identity Header. This indicates that the calling application has been authorised to use this service. 

### Domain Logic Component

The domain logic component implements the business requirements of the service. It consists of a workflow and rules. Workflow will not contain rules. The workflow will only ever ask questions of the rules.

### Sequence of Interactions

The sequence diagram below shows the flow of calls to the filter service.

![image](http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/newportg/NorthStarContractIntegration/master/plantuml/InteractionsSeq.puml)

### Flowchart

![image](http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/newportg/NorthStarContractIntegration/master/plantuml/ProcessFlow.puml)


### Component Detail

1. Azure Function Detail
2. Security Component
4. Domain Logic Component
