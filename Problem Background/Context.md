# Sysops Squad
Penultimate Electronicsis a large electronics giant that has numerous retail stores throughout the country. When customers buy computers, TV’s, stereos, and other electronic equipment, they can choose to purchase a support plan. Customer-facing technology experts (the “Sysops Squad”) will then come to the customers residence (or work office) to fix problems with the electronic device.

## A Bad Situation...
Things have not been good with the Sysops Squad lately. The current trouble ticket system is a large monolithic application that was developed many years ago. Customers are complaining that consultants are never showing up due to lost tickets, and often times the wrong consultant shows up to fix something they know nothing about. Customers and call-center staff have been complaining that the system is not always available for web-based or call-based problem ticket entry. Change is difficult and risky in this large monolith -whenever a change is made, it takes too long and something else usually breaks. Due to reliability issues, the monolithic system frequently “freezes up” or crashes -they think it’s mostly due a spike in usage and the number of customers using the system. If something isn’t done soon, PenultimateElectronics will be forced to abandon this very lucrative business line and fire all of the experts (including you, the architect).

Current process in the monolithic system:

Sysops squad experts are added and maintained in the system through an administrator, who enters in their locale, availability, and skills.
Customers who have purchased the support plan can enter a problem ticket using the sysops squad website. Customer registration for the support service is part of the system. The system bills the customer on an annual basis when their support period ends by charging their registered credit card.

Once a trouble ticket is entered in the system, the system then determines which sysops squad expert would be the best fit for the job based on skills, current location, service area, and availability (free or currently on a job).
The sysops squad expert is then notified via a text message that they have a new ticket. Once this happens an email or SMS text message is sent to the customer (based on their profile preference) that the expert is on their way.
The sysops squad expert then uses a custom mobile application on their phone to access the ticketing system to retrieve the ticket information and location. The sysops squad expert can also access a knowledge base through the mobile app to find out what things have been done in the past to fix the problem.
Once the sysops squad expert fixes the problem, they mark the ticket as “complete”. The sysops squad expert can then add information about the problem and fix to the knowledge base.
After the system receives notification that the ticket is complete, the system send an email to the customer with a link to a survey which the customer then fills out
