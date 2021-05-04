# 3. Segregate ticket creation into a separate container

Date: 2021-04-29

## Status

Accepted

## Context

Usage peaks of the system might lead to not beeing able to enter tickets, system freezes and the perception of ticket lost.

## Decision

Segregate ticket creation into a separate service. Create a persisting ticket queue to decouple the ticket creation flow from the DB.

## Consequences

Storing a new ticket is dependant on the monolith anymore. It is a rather atomic operation on an easy to scale service. This separation will add slight complexity but also more availability and reliability of the action of ticket creation.
