# Solution Overview
## Purpose 

The following chapters provide a architectural overview of the solution.The [C4 Model](https://c4model.com/) is used to give an overview about the new architecture of the ticketing system. 

## Solution goals

The proposed design provides a simple approach to create a new reliable and flexible solution for the SysOps Squads trouble ticket system.
Then new approach to resolve the issues which are outlined in the [Problem Background](../Problem+Background/System+Analysis.md')

## Principals

In order to be able to drive conversations and architectural choices, it seemed important to define some principals and so the presented architecture has designed with the following in mind:

- **Simple** and **pragmatic**. The problems of the current system are impactful for the business and it is important to fix them in a timely manner.
- **Priority** to fixing current situation.
- **Flexibility** for future improvement. It also seemed appropriate to decouple some of the responsibility without replacing them will keeping future options open.

## Context
### TODO: Context Diagram



## Ticket Workflow Alteration

It is difficult to to adapt the process without the input of thee Business. It will be interesting to run a co-creation workshop where the process could be altered to ensure tickets are not lost or properly assigned. 

Although here is a proposal a process that embbed a feedback mechanism from the expert when a ticket is assigned to them. It is important to mention here as well that having experts maintaining their own skill set in the system instead of the manager would help keeping them up to date and improve on the assignation algorithm.

![Ticket Workflow](./resources/alternative-ticket-workflow.png?raw=true)