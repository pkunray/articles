
[microservices: Decomposing Applications for Deployability and Scalability](https://www.infoq.com/articles/microservices-intro/)

Author: Chris Richardson

## Notes

### Pros and Cons of MS

``` mermaid

mindmap
Microservices
    Benefits
        easy to understand
        start fast, spead up deployments - small code base
        keep developers productive - IDE fast
        independently deployment
        reduce communication effort when deploying
        make continuous deployment feasible
        deploy on different machines according to CPU or memory intensive
        easier to scale development by small teams
        improves fault isolation
        easy to rewrite
        good for new technology trial
    Drawbacks
        additional complexity of creating a distributed system
          inter-process communication mechanism
          not well supported by IDE
          automated tests more difficult
        introduces significant operational complexity
          a high-level of automation is needed
        deployment complexity
          a rollout plan that orders service deployments is needed
        difficult to decide when to adopt MS
    Key Design Issues
        Communication with clients
          API Gateway
            optimize communication performance by reducing API calls on Internet
            encapsulates the details of the microservices
        Inter-service communication mechanisms
          Synchronous HTTP
            cons
              client and the server must be simultaneously available
              need a service discovery mechanism - hide ip & port
            pros
              request/reply style of communication is easy
          Asynchronous messaging
            pros
              decouples message producers from message consumers
              service discovery mechanism is not needed
            cons
              need a message broker, more complex
              request/reply-style communication is not a natural fit - cannot fullfill all communication cases
          Handling update requests
            Distributed transactions
            Event-driven asynchronous updates - prefered
              improves availability
              but trades data consistency, applys to eventually consistant data tolerate cases
              compensating transactions to perform logical rollbacks is needed
    How To Refactoring A Monolith To MS
      implement new functionality as a standalone service - with glue code
      dentify a component of the monolith to turn into a cohesive, standalone service
         constantly changing component
         components having conflicting resource requirements
         presentation tier
```
