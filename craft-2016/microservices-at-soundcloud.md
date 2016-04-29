# SoundCloud’s Toolbox for Microservices

http://beta.craft-conf.com/speaker/BoraTunca

- Missed the beginning and there seem to have been some important concepts
  mentioned, for instance the 'mothership'.
- Separate APIs are maintained for each client.
- Strangler Pattern - used for migrating away to microservices, when
  gradually switch over to new endpoints, handled in the client.
  - A strangler is inserted for public APIs, which redirects and translates
    old requests to the new microservices
- Backend for frontend (BFF) calls to a few features, the authentication, the
  geo-location, and forwards stuff to the microservices. These are
  separated to avoid e.g. duplicate auth calls made for the same request by
  multiple microservices.
- The auth/geolocation/etc. group is called the critical path.
- The critical path needs to handle failures gracefully and be ready for
  traffic spikes. You always need someone on call to fix it, since these will
  bring down the whole system.
- The BFF's were aggregating microservices initially, then the aggregations
  themselves were moved to their own microservices.
- Split the microservices into layers to prevent making a mess at this point:
  - Foundation layer: images, users, etc., where you have basically no business
    logic, you just have the data access
  - Value Added Layer: profiles, stream, playlists, where you actually have
    business logic, and are accessing foundation layer microservices.
  - Edge Layer: The BFFs
- Humane Registry should be a tool that gives you info about all your
  microservices and is oriented around people, like who is working on it now,
  who worked on it the most, who resolved the latest incident, etc.
  - Don't rely on people to keep it up to date with all this info (Integrate it
    with all your tools.)
  - But do encourage human contribution
- Prometheus is used for monitoring. It's decentralized, scalable, simple to
  operate, has multi-dimensional data, and powerful querying.
- TODO: Check Prometheus.
- Service Level Objectives are defined to help prioritize maintenance vs. new
  feature development.
  - For instance: error rate <0.01% and p99 latency <0.5s. When it's conforming
    to these bounds, it's considered available. The service directory shows the
    availability rate over the past month or so.
- TODO: Check backstage.soundcloud.com for more details.
- Incompatible API changes are caught by integration tests in some cases.
- They have a tool for capturing production traffic, applying it to any target,
  and comparing the responses.
- DNS is used for service discovery.
- There's no dynamic scaling in place, everything is over-provisioned.
- Swagger is under consideration for BFFs.
- The BFFs actually implement some business logic, which is considered
  technical debt.

