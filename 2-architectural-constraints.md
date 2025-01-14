# 2, Architectural Constraints

## Architectural Goals

Integration Goals for Hub with NorthStar services:

* Standardise Data Integration, Reporting, and Export:
  * Ensure uniform approaches for data handling and reporting.
* Utilise Current Patterns for Gathering Usage Information:
  * Adopt existing methods to collect and analyze usage data.


## Architectural Principles

The proposed pattern architecture aligns to our current Group Technology Principles as follows:

| # | Principle                                                            | Description                                                                                                                                                                                               | RAG   |
| - | -------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----- |
| 1 | Cloud-First and Microsoft-Considered Strategy                        | This service, like all services defined are written to take advantages of cloud-first design, and are only cloud vendor specific where they need to be.                                                   | Green |
| 2 | Design in a modular way and think of re-use                          | The service integration pattern follows previously defined services, and shares many components.                                                                                                          | Green |
| 3 | High Cohesion and Low Coupling – Favour Asynchronous Communication​  | This service utilises a service-bus architecture, decoupling it from specific client applications, enabling it to be used by all.                                                                         | Green |
| 4 | Software Should be Verifiable                                        | This service has been designed with the view that all components will be highly testable, and fully meet the requirements of a CI/CD strategy.                                                            | Green |
| 5 | Think Global, Build Local                                            | This service has been specified to be location agnostic.                                                                                                                                                  | Green |
| 6 | Configuration over Customisation                                     | Any cloud service must facilitate run-time behaviour (configuration) changes via a self-serve administrator portal. This SAD includes the resources to enable this capability by default                  | Green |
| 7 | Build with Privacy-as-Default with a risk-based approach to security | The pattern architecture will mandate a standards-based approach to resource authentication (Managed Identity), user authorisation (role-based access control) and both user and system activity auditing | Green |

## Architecture Constraints

* Access to the service will follow current approved security and access rules.
  * Managed Identity to provide resource access.
  * User Identity optional, as calling systems will have already authenticated the user.
    * If User Identity is passed then it should be validated.
  * User Identity to satisfy audit.

## Technical Constraints

|                                | Constraint Background and / or motivation | Software and programming constraints                                                                        |
| ------------------------------ | ----------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| _Code Constraints_             |                                           |                                                                                                             |
| TC1                            | Implementation in C#                      | The application will be written/maintained in the current version of C#                                     |
| TC2                            | .Net Framework                            | The application will use the current LTS version of .Net                                                    |
| TC3                            | This Party Libraries                      | Any third party library needs to be approved by Knight Frank, and have the appropriate Open Source license. |
| _Operating System Constraints_ |                                           |                                                                                                             |
| TC4                            | Cloud Provider                            | The application will be deployed to the Microsoft Azure Cloud                                               |
| TC5                            | OS Development                            | The application developed for the windows platform                                                          |
