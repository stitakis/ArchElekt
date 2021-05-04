# Assumptions

1. **Load**: The system will have maximum of 50 concurrent users. The customers, which subscribed the service have no relation to each other and huge spike usage of the service is unlikely.
2. **Mobile Connection**: On the premisses where the experts perform their work mobile Internet connection is available on at least a 3G standard.
3. **Localization - Translation**: The users are located in one Region. No worldwide operation necessary. The application don't need to be distributed or translated.
4. **Root cause outages**: The outages the team think of doesn't come from a spike of usage, as there are not a lot of users and there are no "events" which are related to multiple users. Instead, the outages come from the reporting feature when a manager triggers the creation of a report.
5. **Admin fails to maintain expert skills**: The admin doesn't perform well on maintaining the skills. On the one hand the skills are outdated and sometimes assigned to the wrong person.
6. **No own IT infrastructure**: SysOps squad doesn't own any IT infrastructure and there are no preferred suppliers.
7. **Notification of Technician is not time critical**: The technicians has most of the time full backlog and plan their work for the next 2 to 3 upcoming workdays. The notification of a new assignment is not time critical. 