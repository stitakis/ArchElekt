Transcript:
Next, let's look at some more complains.

---
# System unavailable, freezes up or crashes

Customers and call-center staff complained that the system **"freezes-up"** or worst is not **available**.

Transcript:
Hum.. That's sounds pretty bad and probably adds to the customer frustration of having an issue in the first place.
There is a few reasons for that though, let's break that down.

Characteristics: Reliability, Availability

---

📈 Usage Spike caused by customers

Transcript:
Also, the team mentioned customer usage spikes as the route cause of the performance problems. Might be although we don't know as we don't have any evidences.

Characteristics: Elasticity

---

📝 Reporting

Transcript:
Another piece though that could be the cause of the performance issues is the Reporting. Depending on the kind of reports, this can add a lot of pressure to the system, and especially when resources are shared with other core functionalities like in a monolithic architecture. 

___

# Decision
 
Add monitoring

<span style="font-size: 80px">🧐</span>

ARDs: 12 (add link)

Transcript:
Anyway, those are wild guesses. We actually don't know for sure. So the right way to look at those problems should probably be to invest in monitoring and do some proper root cause analysis.

Characteristics: Observability

---

so far team reported availability and reliability problems

Are there more?

---

🛠 System is hard to change

Transcript: "Whenever a change is made, it takes too long and something else usually breaks". This is probably due to the strong coupling between components that emerged with time from the monolithic system.

Characteristics: Maintainability

---

# Solution

Split the monolith

Transcript: divide and conquer strategy will help us to improve code maintainability and address the availability problem     

---

When splitting a monolith there are some architecture style option to pick...

... we decided to go service-based architecture 

Transcript: this is pretty cool, now we can quickly introduce services and we don't even need to split the database. 

---

Before to start splitting the monolith, we need to do a strategic change in the architecture

--- 

# Decision

Add an API layer as single point of contact 

ADRs: ADR2

Transcript: to provide an abstraction layer and to allow decomposition of the monolith and provide services. Exactly what we need, this will increase flexibility and testability

--- 

how we continue? Which service should we split first?

--- 
# Decision

Segregate reporting into a separate service

ADRs: ADR4

Transcript: to avoid collateral impact of the resources consumption load that reporting could cause. We will avoid that system freezes. Transcript: excellent, now load caused by report generation will not impact other functionality.  

---

can decouple more the monolith?

Transcript: let see if we found some quick wins

---

# Decision

Improve security by introducing more services

ADRs: ADR7
 
Transcript: by splitting from the monolith the authentication and payment component. Awesome, now the sensible data is isolated and more secure   

___

# Decision

Improve security by introducing more services

ADRs: ADR8

Transcript: each in its own service with its own separated database. Awesome, now the sensible data is isolated and more secure   

---
