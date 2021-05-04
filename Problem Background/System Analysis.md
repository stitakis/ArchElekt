# System Analysis

| Actors  | Actions |
| ------- | ------- |
| Admin  | <ul><li>add and maintain experts (locale, availability and skills)</li><li>maintain the internal users</li><li>manages all of the billing processing for customers</li><li>maintains static reference data (support products, name-value pairs in the systems, etc...)</li></ul> |
| Customer  | <ul><li>register for the Sysops Squad service</li><li>view billing history and statements</li><li>view support plans based on products purchased</li><li>maintain profile (including credit card and billing information)</li><li>enter a problem ticket via website</li><li>complete a survey</li></ul> |
| Experts  | <ul><li>retrieve ticket information and location from custom mobile app</li><li>browse a knowledge base to find issue history</li><li>mark ticket as complete</li><li>add fix information to the issue/knowledge base</li></ul> |
| Manager  | <ul><li>request reports (financial, expert perf, ticketing)</li><li>keep track of problem ticket operations</li></ul>  |
| System   | <ul><li>send reports to manager (financial, expert perf, ticketing)</li><li>bill customer monthly</li><li>determines which expert would be the best fit for the job (skills, location, service area, availability)</li><li>notify expert by SMS</li><li>notify customer by Email or SMS (based on profile pref) ticket has been assigned</li><li>notify customer by Email or SMS the ticket is complete</li><li>send survey to customer to fill out</li></ul> |

## Ticket Workflow
- Customers who have purchased the support plan enter a problem ticket using the Sysops Squad website.
- Once a problem ticket is entered in the system, the system then determines which Sysops Squad expert would be the best fit for the job based on skills, current location, service area, and availability (free or currently on a job).
- Once assigned, the problem ticket is uploaded to a dedicated custom mobile app on the Sysops Squad expert’s mobile device. The expert is also notified via a text message that they have a new problem ticket.
- The customer is notified through an SMS text message or email (based on their profile preference) that the expert is on their way.
- The expert uses the custom mobile application on their phone to retrieve the ticket information and location. The sysops squad expert can also access a knowledge base through the mobile app to find out what things have been done in the past to fix the problem.
- Once the expert fixes the problem, they mark the ticket as “complete”. The sysops squad expert can then add information about the problem and repair information to the knowledge base.
- After the system receives notification that the ticket is complete, the system send an email to the customer with a link to a survey which the customer then fills out.
- The system receives the completed survey from the customer and records the survey information.

## Identified Problems
1. Wrong expert shows up to appointment
    - Expert skills are outdated in the system due to the manager maintaining them.
2. Tickets lost
    - Ticket disappeared from db (data loss). Could happen during the workflow while moving data from a component to another.
    - No expert with the right skills is available (e.g. holidays).
    - SMS to the expert is lost. SMS is a one way communication channel. Acknowledgment feature exist in the protocol although that is unreliable.
    - Push of the ticket to the expert mobile app seems an unreliable solution and prone to errors.
3. System not always available for web-based (or call-based problem) ticket entry
    - System crashed due after a change of the development team due to the monolithic architecture of the system.
    - Performance issue of the system leading to slow down and timeouts.
4. System freezes up or crashes due reliability issues (maybe due a usage spike)
    - Usage spike seems unlikely as the system is supposed to serve customer of the size of a mid-sized city although better monitoring and observability of the system could help identifying bottle necks.
    - Reporting feature could be the cause of the issue as it might put pressure on the system while customer are trying to add tickets.
5. Changes are difficult and risky, takes too long, something else usually breaks
    - The monolithic architecture is most likely the cause of this as it might have lead to strong coupling. Decomposition and isolation could help.
    - Responsibilities might have been intertwined within component making difficult to update functionalities without regressions.

![Architecture Charateristics](./resources/architecture-characteristics.png?raw=true)
