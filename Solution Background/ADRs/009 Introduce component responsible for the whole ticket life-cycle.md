# 9. Introduce component responsible for the whole ticket life-cycle

Date: 2021-04-30

## Status

Proposed

## Context

Ticket loss, difficult to make changes to the system. Assumption: there is no central entity driving the ticket life-cycle. The system rather reacts on events with direct actions.

## Decision

We want to introduce a ticket life-cycle component that represents and also drives the whole life-cycle of a ticket. This component will be responsible for pulling tickets from the persistent ticket queue until exhausted or new ticket are added as mentioned in the [ADR 3](./003%20Segregate%20ticket%20creation%20into%20a%20separate%20container.md) and orchestrating the life-cycle of the ticket:
- assignment to expert
- awaiting acceptance or rejection of the expert assignation
- retries of assignments
- timeouts when not responding to assigned tickets
- escalation to manger
- triggering notifications
- requesting for survey

## Consequences

- Ticket life-cycle component is the single source of truth and manages all phases of the ticket workflow. By isolating and making this explicit we hope to lower complexity and increase maintainability.
- Allows an easy way of implementing more complex processes like the escalation, if ticket assignment was rejected by expert (see [ADR 5](./005%20Expert%20needs%20to%20actively%20accept%20or%20reject%20an%20assigned%20ticket.md)).
- Improves elasticity by consuming the persistent ticket queue.
- Parallelisation might introduce issues of tickets assigned to multiple experts.
