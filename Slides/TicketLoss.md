Transcript:
The last problem customers mentioned, and we wanted to address is a pretty annoying.

---

# Ticket Loss

Customers are complaining that consultants are never showing up due to **lost tickets**...

Transcript:
- Of course, we are talking about ticket loss. 
- Customers are complaining that experts are never showing up. 
- That on might be hard to nail down but here are a few trails we followed:

---

Data loss

Transcript:
Ticket might actually just disappear from the system if the communication between components fails for example.

---

Right skills are not available

Transcript:
But also sometime, the right expert might not be available because of vacation or seekness.

---

SMS & pushing ticket to expert is unreliable

Transcript:
- Lastly SMS and pushing ticket information to the expert in general sounds pretty unreliable. 
- It is one way communication channel that lack acknowledgment from the expert to ensure the ticket is taken care of.

---

# Decision

Capture Ticket component and persisting queue

Customer -> Customer Website -> API Gateway -> Ticket Creation -> Persistent Ticket Queue 


ARD3

Characteristics: Reliability

Transcript:
In the current system it is not clear how we ensure tickets are captured.
A Ticket Creation component will make sure we capture and persist them in a persisting queue.
And guarantees that no ticket is being lost.

---

# Decision

Acknowledgement & Escalation

ADR5. Expert needs to actively accept or reject an assigned ticket
ADR6. Handle cases for system not able to assign ticket to an expert

Transcript:
Once we ensured we captured the ticket, we had a look at the ticket workflow. And we decided to add an acknowledgment process from the expert when it gets a ticket. That will help to ensure the right expert to show up but also an escalation process in case the system fail to assign a ticket.

---

# Decision

Component responsible for the whole ticket life-cycle

ADR9. Introduce component responsible for the whole ticket life-cycle

Transcript:
- Although, there is still a piece missing. Something that is explicitly responsible for handling and orchestrating all that logic. 
- That's why we decided to create a new component responsible for the whole ticket life-cycle. 