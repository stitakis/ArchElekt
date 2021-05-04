# 10. Introduce workflow engine as alternative to ADR 9

Date: 2021-05-04

## Status

Proposal

## Context

Sometimes the system breaks after changes or is unavailable to customers and other users. Also, there is assumptions from the technical team that some performance issues are due to usage spikes.

## Decision

Introducing better oberservability and a monitoring solution would counter assumptions and help the technical team to respond quickly to failure, allowing for investigation of performance bottle necks and effective route cause analysis.

## Consequences

Introducing and maintaining a monitoring system usually takes time from development but the benefit of reacting fast to failure and identifying performance issues clearly outweigh the cost. It will also enable more informed future architecture decisions by adressing the right problems.
