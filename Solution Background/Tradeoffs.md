# Trade-offs

1. We converted the monolith in service-based architecture style with the aim to sacrifice simplicity for more agility, flexibility and availability.
Different parts of the system can be developed and tested independently.
This will increase development agility and decrease time-to-market.
Additionally, the availability will be increased by the fact that more independent deployment units will be allocated at runtime.
Eventual high load on some parts of the system will not impact the performance of the other parts.
While the database still remain as single-point of contention that can suffer from high load, we believe that this architecture style provides a good balance between benefits and tradeoffs.

1. Around the ticket capture logic few remarkable changes has been introduced.
With the new architecture the ticket capture logic resides in its own deployment unit at runtime.
A kind of command query request segregation pattern that enforces reliability and achieves better performance.
Additionally, the ticket capture publishes new tickets to a persistent queue.
This decouples this part of the flow from the database and achieves even more reliability around this part of the ticket workflow.
While these measures increase the overall complexity we believe it outweighs its cost and expect that no new ticket will be lost.

3. We introduced a ticket lifecycle component to manage the different stages of a ticket.
Additional functionality means increase in effort and cost on maintenance. However, we believe that this workflow like implementation will improve the overall ticket assignment implementation and ticket management.
The former architecture didn't provide a solid concept for managing the ticket lifecycle.
We believe this measure combined with others decision mentioned above and in the ADRs will contribute to avoid any lost of ticket.

4. To improve security we split from the database the login and payment to its own database accordingly.
The goal of this measure was to reduce the risk of data breach at the cost of increased complexity.
   
5. Overall, it will be difficult to parallelize the ticket processing as by nature, there is a limitation due to the assignation of ticket to experts. It is a trade-off we can accept as the volume of tickets should not be that high, and the speed of treating them is not time critical.  
