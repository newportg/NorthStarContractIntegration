# 6, Runtime View

## Overview

This shows the general flow of how the system will function.

![image](http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/newportg/NorthStarContractIntegration/master/plantuml/RuntimeView.puml)

1. The user creates or updates a contact
1. Hub saves the contact.
1. Hub transforms the contact into a agreed schema.
1. Hub publishes the contact onto the service bus.
1. Filter service receives a contact.
   1. Validate contact
   1. If it is a N* record
      1. Send to N*  
      1. N* returns ID
   1. Publish Contact to service bus.
1. Hub will update contact in Hub database.

