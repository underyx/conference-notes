# Designing fast and scalable Python MicroServices with django

https://2018.pycon.sk/en/speakers/Joshi.html

- Take care of your list of middleware, they can add lots of request processing time
- Use conditional GET, gzip, and cache middleware to improve response times
- Add indices to any column you filter by
- Add persistent connections to DB
  - Apparently Django doesn't have this by default even in 2.0
- Enable connection pooling for DB connections
- Use `prefect_related`, `select_related`
- Use the ORM methods to reveal your intent and let it optimize
  - Such as `.count()` instead of `len()`
