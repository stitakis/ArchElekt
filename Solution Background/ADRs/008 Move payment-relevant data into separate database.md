# 8. Move payment-relevant data into separate database

Date: 2021-04-30

## Status

Proposed

## Context

Payment information is in the same database as the rest which increases the chance of credit card information being stolen.

## Decision

Move payment-related information into separate database and restrict access to this db only to the billing functionality.

## Consequences

Increases security
