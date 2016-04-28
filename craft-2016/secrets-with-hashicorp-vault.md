# Secrets, Certificates, and Identity with Vault

http://beta.craft-conf.com/speaker/MitchellHashimoto

- Secrets are not just passwords etc., but also sensitive info
  - Anything that you wouldn't want to be announced on the evening news
  - Vault can be used to secure this sort of stuff as well
- Certificates are normally a pain to manage, Vault can manage them as well
- The pre-Vault world has a bunch of questions:
  - How does an app get secrets, and how does a human get them?
  - How do you update and revoke secrets? How do you know it's safe to revoke?
  - What's the encryption and storage like?
- Config management secret storage is not a very good solution, since there is
  no access control, auditing, revocation, and key rolling.
  - Key rolling helps contain issues; if you replace encryption keys every week,
    a compromised key will allow the attacker to access one week's worth of data.
    Also, you can revoke only that one key so you have less outage.
- Databases are not a good solution, just think about it, it misses most things
  from above.
- Problems are keys being all over the place, limited information in case of a
  breach, secret management is tedious, and no one know what to do in case of
  emergency.
- Obviously Vault everything above.
- Single source of secrets means that you are able to concentrate on one place
  that you secure really well instead of having to really careful everywhere.
- All Vault communication is encrypted end-to-end with TLS 1.2
- CLI tool looks pretty simple to use, basically like redis `SET` and `GET`
- 'Dynamic secrets' is a pretty important concapt of Vault
  - Clients never have root credentials
  - The clients only have access when they need, they don't have credentials
    otherwise
  - Example: vault creates PostgreSQL users and passwords when an app requests
    DB access and deletes the user after the lease time (let's say 1 hour) ends
  - There's support for AWS, Consul, psql, etc.
  - Where it's supported Vault uses the services' own user expiration features
- You can renew the secret lease by the way, if you still need it.
  - Obviously this is preferable to reconnecting every hour with a new user
  - All of this is awesome for auditing
- The audit log contains all requests and responses, with the secrets hashed
  of course
  - Lots of thought when into securing the audit log as well, and making it
    easy to search if you know what you're looking for
- Access control is role based, denies all access by default
- Authentication is flexible, with different backend supported
- Fancy high availablity stuff included
- The encryption key is never stored, you need to provide it manually every time
  you restart the Vault to let it decrypt the encrypted secrets.
- You can split the master key into separate keys, and you need a quorum of keys
  to get the encryption key, so one operator is unable to do anything on their
  own.
- In practice:
  - You're using an HTTP JSON API or the CLI.
  - Best way is to use the Vault libs
- All of this is open source by the way
- Best practice is to run more Vault servers than you think you need to need
  'unsealing ceremonies' only once a week/month for the servers that die.
- Note: ACTION: Use Vault. Seriously.

