Tools: https://www.narakeet.com/, https://revealjs.com/ 

---

# Sysops Squad

## Context

* Monolithic application
  ![](../Problem%20Background/resources/architecture-components.png)

* Ticket workflow
  ![](../Problem%20Background/resources/ticket-workflow.png)

Notes: 
Not sure we can see anything on those diagrams. We might want to simplify them.
Maybe a step by step walk through would be better for the workflow.

## Quote

If something isn’t done soon, Penultimate Electronics will be forced to **abandon** this very lucrative business line and **fire all of the experts**.

## Problems
* [Wrong expert show up](./WrongExpert_short.md) (Christian)
    - Why? Reasons, assumptions, ...
      * Expert skills are outdated in the system due to the manager maintaining them.
    - Characteristics
    - Solution (ADR1) Updating own profile
    - Tradeoffs
* System unavailable, freezes up or crashes (Vincent)
    - Why? Reasons, assumptions, ...
    - Characteristics: Observability
    - Solution (ADR12) monitoring
    - Tradeoffs
* Hard to change (Sebastian)
    - Why? Reasons, assumptions, ...
    - Characteristics: Maintainability, Reliability, Availability
    - Solution (ADR2, ADR4, ADR11, maybe mention ADR7 & ADR8), Service based architecture, make workflow responsibility explicit, API gateway
    - Tradeoffs
* Ticket loss - Workflow (Together)
    - Why? Reasons, assumptions, ...
      * Ticket disappeared from db (data loss). Could happen during the workflow while moving data from a component to another.
      * No expert with the right skills is available (e.g. holidays).
      * SMS to the expert is lost. SMS is a one way communication channel. Acknowledgment feature exist in the protocol although that is unreliable.
      * Push of the ticket to the expert mobile app seems an unreliable solution and prone to errors.
    - Characteristics
    - Solution (ADR3, ADR5, ADR6, ADR9 - ~~10~~)
    - Tradeoffs
* Security (Bonus) Steffen
    - Danger of putting all your eggs in the same basket
    - ADR7 & ADR8

# [Finish Line](./FinishLine.md)

## Principals
* Simple and pragmatic
* Priority to fixing current situation
* Flexibility for future improvement
* Security

## Overall System
![](../Solution%20Background/resources/Containers.png)
