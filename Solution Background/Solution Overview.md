# Solution Overview
## Purpose 

The following chapters provide a architectural overview of the solution.The [C4 Model](https://c4model.com/) is used to give an overview about the new architecture of the ticketing system. 

## Solution goals

The proposed design provides a simple approach to create a new reliable and flexible solution for the SysOps Squads trouble ticket system.
The new system should deliver a better user experience and resolve the issues which are outlined in the [Problem Background](../Problem+Background/System+Analysis.md') in a timely manner.

## Principals

In order to be able to drive conversations and architectural choices, it seemed important to define some principals and so the presented architecture has designed with the following in mind:

- **Simple** and **pragmatic**. The problems of the current system are impactful for the business and it is important to fix them in a timely manner.
- **Priority** to fixing current situation.
- **Flexibility** for future improvement. It also seemed appropriate to decouple some of the responsibility without replacing them will keeping future options open.

## Context
The system doesn't have a lot of interfaces. It provides the users the needed information with taylored interfaces and rely on 3rd party services for sending notifications to increase efficency and user experience for all the stakeholders.  
The users can be seen as four different roles which interact with the system: 
1. The customer 
1. The Expert 
1. The Administrator
1. The Manager


![System Context](./resources/SystemContext.png)

## Conceptional Model

![Containe Model](./resources/Containers.png)

## Ticket Workflow Alteration

It is difficult to to adapt the process without the input of the Business. It will be interesting to run a co-creation workshop where the process could be altered to ensure tickets are not lost or properly assigned. 

Although here is a proposal a process that embbed a feedback mechanism from the expert when a ticket is assigned to them. It is important to mention here as well that having experts maintaining their own skill set in the system instead of the manager would help keeping them up to date and improve on the assignation algorithm.

![Ticket Workflow](./resources/alternative-ticket-workflow.png?raw=true)




## Component Decomposition 

![Payment service](./resources/PaymentService.png?raw=true)
![Shared services](./resources/SharedService.png?raw=true)
![Ticket lifecycle service](./resources/TicketLifecycleService.png?raw=true)
![Ticket creation services](./resources/TicketCreationService.png?raw=true)
