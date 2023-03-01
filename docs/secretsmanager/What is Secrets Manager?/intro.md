# What is AWS Secrets Manager?

## Features of AWS Secrets Manager

### Programmatically retrieve encrypted secret values at runtime

### Store different types of secrets

### Encrypt your secret data

**How does Secrets Manager encrypt the protected text of a secret?**

Secrets Manager encrypts the protected text of a secret by using [AWS Key Management Service(AWS KMS)](https://docs.aws.amazon.com/kms/latest/developerguide/).

**What does Secrets Manager associate every secret with?**

Secrets Manager associates every secret with a KMS key.

**What kind of keys can be associated?**

It can be either AWS managed key for Secrets Manager for the account (`aws/secretsmanager`), or a customer managed key you create in AWS KMS.

**What does Secrets Manager do when it encrypts a new version of the protected secret data?**

Whenever Secrets Manager encrypt a new version of the protected secret data, Secrets Manager requests AWS KMS to generate a new data key from the KMS key.

**What Secrets Manager uses the data key for?**

Secrets Manager uses this data key for [envelope encryption](https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#enveloping)

**What does Secrets Manager do when it needs secret decryption?**

Whenever the secret needs decryption, Secrets Manager requests AWS KMS to decrypt the data key, which Secrets Manager then uses to decrypt the protected secret data.

**How does Secrets Manager store the data key?**

Secrets Manager never stores the data key in unencrypted form, and always disposes the data key immediately after use.

**How does Secrets Manager accept requests from hosts by default?**

Secrets Manager, by default, only accepts requests from hosts using open standard Transport Layer Security (TLS) and Perfect Forward Secrecy.

**When does Secrets Manager ensures encryption of you secret?**

Secrets Manager ensures encryption of your secret while in transit between AWS and the computers you use to retrieve the secret.

