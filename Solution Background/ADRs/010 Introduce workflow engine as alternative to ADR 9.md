# 10. Introduce workflow engine as alternative to ADR 9

Date: 2021-04-30

## Status

Declined

## Context

Ticket loss, difficult to make changes to the system. Assumption: there is no central entity driving the ticket life-cycle. The system rather reacts on events with direct actions.

## Decision

Represent the full life-cycle of a ticket from ticket creation by a customer or manager till the issue is fixed and the survey is done by a workflow driven by a workflow engine. Pick an existing workflow engine consisting of the following parts:
- ticket creation
- ticket queue
- scheduler
- execution based on modeled workflows
- adapters for facing external services

Those parts are used the following way:
- The customer or manager fills a form in the user interface, which will be send to the ticket creation...
- ... which validates the input, creates a new ticket and puts it into the ticket queue.
- The scheduler decides when to pick up the ticket, e.g. whenever there is time and resources for doing so.
- When a ticket is picked up it will be executed by the execution. Execution is executing a workflow with inputs given to ticket creation.
- While executing the workflow the engine might use the adapters to request or trigger external services.

All the edge cases like an expert rejecting an assigned ticket, timeouts when not responding to assigned tickets, retries of assignments, escalation to manger, triggering notifications, etc. are represented in this workflow. Triggering events to the outside, e.g. sending notifications, happens via the adapters, which are adapting and reusing existing functionality from the existing monolith. The workflow engine replaces those parts of the monolith that are currently reacting on events regarding tickets.

Further requirements/technical details of the workflow engine:
- persistance: a ticket needs to be persisted at all time, which includes any kind of state change when an oder is executed
- the parts of the workflow engine (at least execution) can potentially run as multiple instances
- parallelism: tickets can run in parallel even on the same instance
- suspension: tickets that are waiting for something can be put to sleep to free up resources
- monitoring possibilities

## Consequences

- The modeled ticket workflow is the single source of truth and makes the whole ticket lifecycle visible. This reduces the complexity of implementation and thereby increases the maintainability.
- Allows an easy way of implementing more complex processes like the escalation, if ticket assignment was rejected by expert (see ADR above).
- Increases stability of the overall ticket lifecycle by using existing workflow engine solution
- Elasticity is less an issue since a scheduler is in place to shape the load on the execution part.
- Scalability is assured through the possibility of using multiple instances for execution. Also one ticket has no dependencies towards other tickets which makes it easy to assign a ticket to random instances.
- Reliability and availability of ticket creation improves since creating an ticket is a rather simple operation.
- Monitoring possibilities allows insights on the ticket workflow to identify gaps/bottle necks to further development.
- Using an existing workflow engine creates dependencies to a vendor, might be expensive in licensing and consulting.

## Reason

A workflow engine is usually used for connecting and orchestrating multiple systems as well as helping the creation and modification of processes and given the current assumption this would not be the right fit for a single workflow solution as proposed in [ADR 9](./009%20Introduce%20component%20responsible%20for%20the%20whole%20ticket%20life-cycle.md).
