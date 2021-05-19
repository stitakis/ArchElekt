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

🛠 System is hard to change

Transcript:
One of the reason the team mentioned is that the system is hard to change. Leading often to crashes. This is probable due to the strong coupling between components that emerged with time from the monolithic system.

Characteristics: Maintainability

---

📈 Customer Usage Spike

Transcript:
Also, the team mentioned customer usage spikes as the route cause of the performance problems. Might be although we don't know as we don't have any evidences.

Characteristics: Elasticity

---

📝 Reporting

Transcript:
Another piece though that could be the cause of the performance issues is the Reporting. Depending on the kind of reports, this can add a lot of pressure to the system, and especially when resources are shared with other core functionalities like in a monolithic architecture. 

---

## Monitoring

<span style="font-size: 80px">🧐</span>

ARDs: 12

Transcript:
Anyway, those are wild guesses. We actually don't know for sure. So the right way to look at those problems should probably be to invest in monitoring and do some proper root cause analysis.

Characteristics: Observability

---

# Split the monolith

Transcript:
Although we did not actually stop there and brought also some answers to those problems.
