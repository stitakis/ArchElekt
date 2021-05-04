# 7. Move login-relevant data and functionality into separate authentication service

Date: 2021-04-30

## Status

Proposed

## Context

Usernames and passwords are in the same database as the rest which increases the chance of passwords being stolen.

## Decision

Move usernames and passwords into separate database (e.g. with higher security measures) and also create a separate authentication service for providing the login functionality. Alternatively use an external authentication provider.

## Consequences

Increases security, reliability and availability of login, but also increase of complexity (usernames and customers in database need to be kept in sync). Using external authentication providers might bring the benefit of supporting additional login possibilities, e.g. social login, etc.
