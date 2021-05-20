---
# System unavailable, freezes up or crashes

Customers and call-center staff complained that the system **"freezes-up"** or worst is not **available**.

Transcript:
Also <ROL> Hum.. That's sounds pretty bad and probably adds to the customer frustration.
There is a few reasons for that though, let's break that down.

Characteristics: Reliability, Availability

12s
---

📈 Usage Spike caused by customers

Transcript:
The team mentioned customer usage spikes as the route cause of the performance problems.
Might be although we don't know as we don't have any evidences.

Characteristics: Elasticity

12s

---

📝 Reporting

Transcript:
Another piece that could be the cause of those performance issues is the Reporting.
Depending on the kind of reports, this can add a lot of pressure to the system, 
and especially when resources are shared with other core functionalities like in a monolithic architecture. 

13s

___

# Decision
 
Add monitoring

<span style="font-size: 80px">🧐</span>

ARDs: [12](https://github.com/stitakis/ArchElekt/blob/main/Solution%20Background/ADRs/012%20Improve%20observability%20and%20introduce%20a%20monitoring%20tool.md)

Transcript:
Anyway, those are wild guesses.
We actually don't know for sure.
So the right way to look at those problems should probably to invest in monitoring and do some proper analysis.

Characteristics: Observability

12s

---

More complains?

Transcript: so far the team reported availability and reliability problems, are more complains? 

5s

---

🛠 System is hard to change

Transcript:
Team reported: "Whenever a change is made, it takes too long and something else usually breaks".
This is probably due to the strong coupling between components that emerged over time from the monolithic system.

Characteristics: Maintainability

12s

---

# Solution

Split the monolith

Transcript:
divide and conquer strategy will help us to improve code maintainability and address the availability problems     

7s

---

we decided to go for a service-based architecture style. 

![](../resources/service-based-architecure-shape.png)

Transcript: 
When splitting a monolith there are some architecture style option to pick from.
We choosed the service-based architecture.
Benefit, all services shared the same database instance.
Now we can quickly introduce services.
And we don't even need to invest effort in splitting the database. 

16s

--- 

# Decision

Add an API Gateway as single point of contact 

![](../resources/monolith-shape.png) -> ![](../resources/monolith-with-api-gateway-shape.png)

ADRs: [2](https://github.com/stitakis/ArchElekt/blob/main/Solution%20Background/ADRs/002%20API%20layer%20as%20single%20point%20of%20contact%20for%20all%20user%20interfaces.md)

Transcript: 
Before to start splitting the monolith, we need to do a strategic change in the architecture
An API Gateway will decouple the fronted from the backend.
And allow the decomposition of the monolith in services while increasing flexibility and testability

16s

--- 

how we continue?
 
Transcript: which service should we split first?

2s

--- 
# Decision

Segregate reporting into a separate service

![](../resources/monolith-plus-reporting-services-api-gateway-shape.png) -> ![](../resources/service-based-arch-shape.png)

ADRs: [4](https://github.com/stitakis/ArchElekt/blob/main/Solution%20Background/ADRs/004%20Segregate%20reporting%20into%20a%20separate%20container.md)

Transcript:
By allocating reporting in its own service, spikes in resource consumption will not impact other functionality.   
This will avoid that the whole system freezes.

10s

---

what else could improve code maintainability and availability?

---

# Decision

Split the website in Customer Website and Employee Website

![](../resources/service-based-arch-shape.png) -> ![](../resources/service-based-arch-shape-with-2-websites.png) 

ADRs: [11](https://github.com/stitakis/ArchElekt/blob/main/Solution%20Background/ADRs/011%20Improve%20Website%20availability%20and%20customer%20satisfaction%20by%20splitting%20the%20website%20in%20Customer%20Website%20and%20Employee%20Website.md)

Transcript:
Customers and Employees will have a dedicated website.
This will allow the team to work independently on each one.   

6s

---

can we decouple more the monolith?

Transcript:
let see if we found some more quick wins

2s

---

# Decision

Segregate authentication and payment each to a separated service with dedicated database

![](../resources/service-based-arch-shape.png) -> ![](../resources/sba-plus-auth-service.png) -> ![](../resources/sba-plus-auth-service-plus-payment-service.png) 

ADRs: [7](https://github.com/stitakis/ArchElekt/blob/main/Solution%20Background/ADRs/007%20Move%20login-relevant%20data%20and%20functionality%20into%20separate%20authentication%20service.md)
ADRs: [8](https://github.com/stitakis/ArchElekt/blob/main/Solution%20Background/ADRs/008%20Move%20payment-relevant%20data%20into%20separate%20database.md)
 
Transcript:
More flexibility is gained by splitting authentication and payment service.
Sensitive data is now allocated in its own database.
This will increase security by reducing the chance of passwords or credit card number being stolen.

10s
---
