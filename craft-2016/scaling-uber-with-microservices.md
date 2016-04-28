# What I Wish I Knew Before Scaling Uber to 1,000 Services

http://beta.craft-conf.com/speaker/MattRanney

- Uber naturally switched to using microservices since this was how they could
  give new hires work.
- Abandon microservices! Make them immutable, changes risk breaking it. Freeze
  it and keep it supplied with infrastructure.
- Uber history time!
  - Wow, Uber started out with outsourced PHP development.
  - Dispatch is in node.js, core API is in Python, both moving to Go
  - Maps and data are Python and Java, metrics use Go
- Microservices allowed for this diversity, to use the best tool for each job,
  and it makes language changes easy
  - They do make the system way more complicated though
  - …especially important when stuff breaks
- Microservices allow you to build around problems instead of fixing them.
  - This is actually normally a bad thing.
  - Politics suddenly come into play. Weird!
- Microservices make it too easy to keep biases and make uninformed technical
  decisions.
- It also gets harder to share code, and harder to switch teams since
  everything is so different.
- The culture gets fragmented if you're using different languages and stuff.
- For RPC it won't be long until you'll need a schema and HTTP/REST will get
  complicated.
- Other than the network IO, all the serialization, validation, metrics, etc.
  add a lot of overhead to microservices.
- Having lots of repos sounds great in theory, having one repo works way
  better if you are trying to see everything at the same point in time.
  Monorepos get *huuuuge* though. And you need to decide between these early.
  - Presenter has 7k repos.
- You often still need to look at your microservice in the whole system's
  context.
- Flamegraph are awesome.
- TODO: Check flamegraph tools for Python.
- You should have a standard set of metrics for all your services.
- TODO: Check out `cpustat`.
- Even if you don't spend engineer time on getting good performance, you need
  to measure it, in all cases.
- If you have bad p99 response times on your microservices, the more you
  add the worse your overall performance gets
  - You need tooling for tracing this. Otherwise you wouldn't notice some
    issues like not having bulk requests and making hundreds to the same
    service instead.
  - It's really hard to keep the context across languages.
- You need consistent, structured, machine-readable logs.
  - Again, mutliple languages make this difficult.
  - Logging is surprisingly expensive, can amplify issues.
  - Teams need to know how much of the infrastructure they are consuming with
    all those logs.
  - TODO: Check Uber's logging libraries.
- Have simple performance requirements/default SLAs, something like 99p
  response should be <5s.
- Synthetic load should be on production basically all the time, so all system
  needs to be able to handle test traffic, to not skew metrics and BI.
- People don't like chaos monkey
- Migration is also really difficult, cause you keep having to support old
  stuff.
  - Mandates are bad, people are not going to want to switch anything. Do it
    for them or make sure that people love your change.
- 'Company > Team > Self' is what you should follow to avoid unnecessary
  politics.
- 'Everything is a tradeoff.'
