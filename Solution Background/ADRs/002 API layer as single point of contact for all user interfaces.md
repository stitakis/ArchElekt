# 2. API layer as single point of contact for all user interfaces

Date: 2021-04-28

## Status

Accepted

## Context

Usage spikes might lead to unavailability to interact with the user interface, system freezes and the perception of ticket lost.

## Decision

Add an API layer as single point of contact of Mobile App and Website to allow decomposition of the monolith and provide services at runtime.

## Consequences

Having an additional layer will add more complexity. On the other hand a unifing API layer might simplyfy attaching roles to certain endpoints and therby improve security. Having an API layer builds an abstraction layer towards the downstream services which will increases flexibility and allow decomposition of responsibilities over time.
