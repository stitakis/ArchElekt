Transcript:
The last problem we wanted to talk about is a pretty annoying one as it might add even more frustration to a already frustrated customer.

---

# Ticket Loss

Customers are complaining that consultants are never showing up due to **lost tickets**...

Transcript:
Of course we are talking about ticket loss. ROL. Like that it might be hard to nail that one down but here are a few trails we followed:

---

Data loss

Transcript:
Ticket might actually just disappear from the system. It could happen during the workflow while moving data around from a component to another for example.
  
--- 

Right skills are not available

Transcript:
But also sometime, the right expert might not be available for the job because of vacation of seekness.

---

SMS & pushing ticket to expert is unreliable

Transcript:
Lastly SMS and pushing information to the expert mobile phone in general sounds pretty unreliable. It is one way communication channel that lack some acknowledgment capability to ensure the ticket is taken care of.

---

# Decision

Capture Ticket component and persisting queue

Customer -> Customer Website -> API Gateway -> Ticket Creation -> Persistent Ticket Queue 


ARD3

Characteristics: Reliability

Transcript:
In the current system it is not clear how do we ensure ticket are capture, so the first change we want to make is to add a Ticket Creation component and a persisting queue to make explicit and ensure tickets are captured. 

---

# Decision

Acknowledgement & Escalation

ADR5. Expert needs to actively accept or reject an assigned ticket
ADR6. Handle cases for system not able to assign ticket to an expert

Transcript:
Once we ensured we captured the ticket, we had a look at the ticket workflow and it felt they were room for improvement. So we decided to add an acknowledgment process from the expert when it gets a ticket. That will help to ensure the right expert to show up but also an escalation process in case the system fail to assign a ticket.

---


<span style="font-size: 80px; margin: 0 auto">♥️</span>

Transcript:
There is still a piece missing though. How do we bring those changes to life? Maybe we are missing a heart, a piece responsible for handling and orchestrating all that logic. Something that make it explicit, so we can care about it.

---

# Decision

Component responsible for the whole ticket life-cycle

ADR9. Introduce component responsible for the whole ticket life-cycle

Transcript:
That's why we decided to create a new component responsible for the whole ticket life-cycle. Ticket Lifecycle component. 