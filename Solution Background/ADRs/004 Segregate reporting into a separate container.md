# 4. Segregate reporting into a separate container

Date: 2021-04-29

## Status

Accepted

## Context

The pressure that the reporting operations might apply to the system could also be the cause of the unavailability and unreliability of the system.

## Decision

Segregate reporting into a separate service.

## Consequences

More complexity, but more availability and reliability. Allows to scale resources on demand depending on usage spikes (scalability elasticity) or alternativly wait longer for results.
