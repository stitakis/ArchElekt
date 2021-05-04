# 5. Expert needs to actively accept or reject an assigned ticket

Date: 2021-04-29

## Status

Accepted

## Context

The system has not assigned the expert with the right expertise (maybe skills not being up to date), the expert does not have time (vacation for example) or is missing the notification message. This leads to the wrong expert or no expert showing up, which again leads to the perception of ticket loss.

## Decision

To mitigate the perception of ticket lost

- the expert's mobile app pulls assigned ticket in addition to the ticket assignment engine pushing the tickets to the expert mobile app
- expert needs to open the ticket and actively accept or reject it
- possible reactions on rejected tickets or tickets that have not been accepted after a defined amount of time: system can try to reassign the ticket to another expert or notify a manager to take action on this ticket

## Consequences

Tickets can not get lost due to missing reaction from an expert. There is a well-defined process for keeping a ticket "alive" including ecalation, if assignment doesn't work in time. This increases the complexity of the assignment process.
