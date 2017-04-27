# Building Cryptographically Secure Web Application Systems

https://craft-conf.com/speaker/FrankWang

- Scary cause complex math leads to implementation bugs,
  and it's hard to manage secrets
- You need to understand the app's setting, and the types of threats
- Accept the performance hit and prepare for having to change
- We're focusing on web apps ran on untrusted servers in the talk
- Untrusted cloud providers and mobile users are recent changes
  - The mobiles have weaker performance which is relevant for us
- Basic crypto is encryption and signature,
  but there's advanced crypto too where you can process the data
  while it's in its encrypted state

## Sieve

- Scene: user's FitBit storer data on FitBit server,
  which wants to share subsets of the data with 3rd parties.
- Naive approach is to use one key to encrypt data at rest,
  but then third parties have access to everything when they get it.
- If you encrypt every record with a different key, that's just too much.
- Sieve is a platform for subset encryption
  that hides key management, is reasonably fast
- You add tags to the records, like `type=run`, and `year=2013`.
- You can create keys for stuff like `year<2013 and type=run`.
- The system assumes the storage provider is a passive adversary,
  and that the data users handle data properly.
- So this sieve thing is public key encryption, but has three functions:
  - decryption key generation takes a policy and the private key,
    to generate a key
  - the other two are encrypt/decrypt of course
  - Note how the attributes/policies are stored in cleartext
- Revocation is a challenge, and ABE is slower than AES
  (since the latter is symmetric)
- In hybrid encryption, ABE is only running on smaller blocks of data
  which hold symmetric keys for decryption, which is a lot faster than
  just running ABE on the large raw dataset.
- For revocation you need to re-encrypt both the small and large data blocks
  from the above described hybrid process.
- Key homomorphism allows you to re-encrypt in place,
  i.e. without needing to first decrypt. It's smart math stuff.
- Revocation takes less than a second, and so does most functions.
- Less than 250 lines of code in real world.

## Splinter

- Scene: user does searches on webservices, which leak sensitive info
  - Travel sites can charge more for often searched routes
  - Data can be sold to 3rd parties
- Naive way to solve this is having the dataset locally on client side
  and not even hitting the server with queries
- For this design you have multiple providers who don't collude against you
- The user splits the query into multiple subqueries,
  and different providers get each part
- The user combines the subresults on the client side
- We assume the data on providers is in cleartext,
  and the providers are again passive adversaries,
  so they try to understand queries but don't tamper
- Response times below 1.5 seconds for million record datasets
- Function Secret Sharing is the name of dividing queries like this
- Splinter works with SQL queries,
  where it tries to keep the WHERE predicate safe
  - Equality, interval, and disjoint OR conditions are supported
- Start with `SELECT count(*) WHERE route = 5` in a flight database
  - `f(x) = 1 if x == 5 else 0` is split into two by converting route IDs
    in a way that the two provider's route IDs for the same row
    sum to 0 if it's not a match, and 1 if it is the correct route ID.
    The user then gets the two sums of all route IDs,
    and adding the two results gets you the actual count. Awesome!
- `SELECT min(price) WHERE route = 5` creates intermediate tables
  for the min price of all routes, apply the same magic as above,
  and you can calculate the min price on the client side
  from seemingly random data.
- Case studies: 
  - Used X1 instances for all of these
  - Yelp clone with Yelp like filtering,
  - flight search,
  - routing on a map.
  - Top 10 cheapest flights has 30-40 ms response times,
    but more complex stuff like routing can take up to 1.5 seconds.
  - Most queries have constant complexity, some have log(N).

## Q&A

### Why not just use incognito mode?

It still leaks data about what the group of users as a whole do.

### Where is Sieve used now?

Two projects, one is a fitness app, not open source yet.

### How are segmented queries anonimized?

They're not. They can know who's queries,
but not what they're querying.
