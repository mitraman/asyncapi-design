## Async Thoughts

### Producers and Conumsers
All the APIs I can think of always have both producers and consumers:
RPC style: consumers make procedure requests, producers fulfill requests
CRUD: consumers make crud requests, producers fulfil requests
Query: consumers make queries, producers answer queries
Event: consumers consume events, producers create events

In the client-server models, there is often a single organizatin that designs, owns and produces the interface. But, there may be multiple consumers. For example, in the case of an RPC API, a single team might design the interface and "produce" it by engineering, implementing and producing response results. This isn't allways the case (e.g. an API spec that is implemented by multiple parties in differeng ways), but the general case for client-server web/network APIs is an n:1 relationship between consumers and producers.

In the event-driven model, the norm is more likely to be an n:n relationship, in which the intent is for multiple parties to be able to consume event based messages. But, also for multiple parties to be able to produce events. In this way, the scope of the personas involved needs to change. 

It also leads to some interesting consequences for arch. design. If my consumers and producers are broadly similar in their domain knowledge, business knowledge and prefereed tooling/languges I can design event messages and infrastructure with consistently good usability and experience. But if they are different enoough, I'll need to introduce a level of abstractioon. 

Take these scenarios:
1. A fintech that is producing an event stream of data changes for banking clients to consume
2. A microservice that needs to listen for private customer information changes to maintain a synchronized data model
3. A government funded pensions controller that wants to regulate query models between pension providers

In each of these scenarios, the event design and event model needs to reflect the boundaires that the consumers and providers reside in. In fact, there is proably a version of Lou Vannick's APIIQ model that applies to this space. Taking it further it feels like there is a law or design property here that relates to bounded contexts and context mapping - when the producers and consumers can't share a common boundary, they can't share a common message model either. There is no ubiquitous language for them.

### Aspects of an event driven design

These are the properties of a design that come to my mind:
1. Producers
2. Consumers
3. Message 
4. Distribution Locations (equivalent of URL -> channels/topics/etc)
5. Workflow/choregraphy (how to denote what step comes next. Can be manifested in links, code, tooling, etc)
6. Runtime Discovery (how to bind to locations and events at runtime)

### Rumors of Loose coupling are unfounded

* explore why people think event-driven is loose-coupled. Explore why this kind of loose-clupling isn't that useful when related to breaking changes, cost of writing code and cost of maintaining systems

