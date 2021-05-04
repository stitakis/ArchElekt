# 2. API layer as single point of contact for all user interfaces

Date: 2021-04-28

## Status

Accepted

## Context

Usage peaks of the system might lead to not beeing able to interact with the user interface, system freezes and the perception of ticket lost.

## Decision

Add an API layer as single point of contact of Mobile App and Website to allow decomposition of the monolith and provide services at runtime.

## Consequences

More complexity but also more flexibility.
