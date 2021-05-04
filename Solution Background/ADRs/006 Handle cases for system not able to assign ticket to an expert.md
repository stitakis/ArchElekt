# 6. Handle cases for system not able to assign ticket to an expert

Date: 2021-04-29

## Status

Accepted

## Context

If system doesn't find an expert with matching skillset, the right location, etc., it is not able to assign a ticket → ticket stays in the system forever → perception of ticket loss

## Decision

System notifies a manager that and also why the system couldn't assign the ticket. The manager could then take action on this ticket.

## Consequences

Closing potential gaps in a ticket's lifecycle and therby increasing the percieved reliability of the system.
