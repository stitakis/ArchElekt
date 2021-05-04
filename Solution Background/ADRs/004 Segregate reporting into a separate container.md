# 4. Segregate reporting into a separate container

Date: 2021-04-29

## Status

Accepted

## Context

Usage peaks of the system might lead to user interfaces not beeing responsive, system freezes and the perception of ticket lost. We also asume that reporting operations might cause those peaks in usage and therby are impacting availability and reliability of the system.

## Decision

Segregate reporting into a separate service.

## Consequences

More complexity, but more availability and reliability. Allows to scale resources on demand depending on usage peaks (scalability elasticity) or alternativly wait longer for results.
