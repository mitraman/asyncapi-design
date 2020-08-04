== Straw Man Working Document


Notes on how an article/preso might look (our final output)

* What are the Goals?
  * See READ.ME notes
* What Event-Driven Means (here)
  * set the ground rules for discussion
* Decisions to Make Up Front
  * Technical Assumptions
    * Idempotent
    * Immutable
    * Not "Safe"
  * Event-style to employ
    * Event-Notifications (EN) - notifications only w/ pointers : "byRef"
    * Event-carried state (ECS) - all the data in the payload : "byValue"
    * Event Sourcing (ES) - full-on transaction style 
  * Workflow Choices
    * Orchestrate in code (hard-code the inter-op)
    * Orchestrate in message (ship workflow document around [byVal or byRef])
    * Orchestrate in broker (omnicient choreographer keeps the workflow doc and does co-ordination)
  * Collecting Domain Info
    * DDD, Event-Storming, Miro
    * produce output
      * stories
      * diagrams
      * definitions (AsyncAPI)
    * message modeling?
  * storage decisions?
  * Implementation
    * prototyping
    * code (generate anything?)
  * Deployment
    * big can of worms here!
  * Other things
    * mocking
    * testing
    * monitoring

