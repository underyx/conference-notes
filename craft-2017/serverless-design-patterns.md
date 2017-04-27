# Serverless Design Patterns with AWS Lambda: Big Data with Little Effort

https://craft-conf.com/speaker/TimWagner

Speaker is lead of Lambda and API Gateway at AWS

## Serverless in general

- Development design stops being driven by the infrastructure boundaries
- Obviously you don't have as much of a maintenance overhead anymore
  - Administering virtual services,
  - sizing workloads,
  - managing fault tolerance,
  - running periodc jobs is especially difficult.
- "No server is easier to manage than no server."
- Event driven, so you don't pay when idle.
- Continuous scaling, on the millisecond level
- COmpute options have two axes: size of unit (VM to function)
  and responsibility (you to fully the provider)
- Function as s Service is available on different responsibility levels,
  serverless is on the 'provider' end.
- You need an event source (request, change infra state, cron, even Alexa)
  which triggers your code
- Whoa, it supports Python 3.6, didn't know that
- Processes, threads, `/tmp` are all available
- Monitoring and logging included
- The app has to be fully stateless
- Flask has Chalice as a framework, express.js also has one
- SAM the squirrel is the mascot

## Event Sources

- Three patterns, first is sync, like Alexa, which waits for the response
- Async exists too, like S3 events, which just launch tasks to run *soon*
- Stream pull sources, missed the explanation for these

## Building Blocks

- Bunch of things like AWS's logging and storage services
- Step Functions gives you serverless for infra
- X-Ray lets you diagnose/debug function runs

## Use Cases

- Commonly used for web apps, and their backends
- Big data processing is a big one, also media/log processing
- Chatbots brought up specifically. Alexa mention for like the 10th time.
- Square-Enix process images, up to 6000 per minute,
  their processing time went from hours to 10+ seconds
- PhotoVogue also uses it to process images, got 10x faster
- Thomson Reuters does 4000 rq/s in social media (?) stream processing,
  and their dev time was a lot less than they expected

## Lifecycle

- The stateless limitation forces you to write nice 12 factor microservices
- CloudFormation understands the so-called SAM (Serverless Application Model)
  specification which describes serverless apps,
  and was made by AWS into an open Apache spec
- AWS CodePipeline handles everything:
  - commit can be hooked, it can go to CodeCommit (or GitHub)
  - CodeBuild builds and tests,
  - and deploy to production can happen automatically
- A new release is AWS CodeStar,
  which is a dashboard for insight into all of this
  - It also has useful project templates
- Showed a demo which included creation and hosting of the repo
  - Was named `craftconf-demo-`, so I guess
    a nice coNvention is to add dashes if your names was taken
- For big data, rite map and reduce functions to eun in sequence

## Demos 

- Demos for S3 and Kinesis
- Will generate & process 20 million entries
- The demo has a few functions bunched together, should normally be separate
- Demo went exactly as you would assume if you spend 5 minutes with Lambda
- A function wrote to S3, the S3 write triggered another function
  to consolidate the written records
- There was a reduce job as well with 200 serial function calls
- All the demos were covered by the free tier

## Q&A

### When not to use it?

Obviously, existing monoliths.
Or if you need Windows, GPUs, and special stuff like that.

### But it's coupled to provider!

The code architecture impact makes the units easy to move anyway.

### Suggested granularity?

One piece of functionality per function.
