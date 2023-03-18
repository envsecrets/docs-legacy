---
description: >-
  We use the industry standard Hashicorp Vault to perform encryption and store
  keys.
---

# Encryption & Keys

## Important Division

1. Every new organization on the platform gets its own encryption key in the **transit secrets engine** of our hosted Vault instance.
2. Encrypted values are then stored separately in a regular postgres instance so that they can be queried by the users.

## Why Vault?

1. Using an industry standard and well-trusted secrets engine gives our users higher trust in the overall robustness of how their secrets are stored, queried and mutated.
2. Having Vault allows us to provide its in-built capabilities out of the box to our users. For example, on-demand rotation of encryption keys.

## Key Storage

1. All encryption keys are stored in vault's in-built dedicated storage.
2. For safety, everytime you create a new organisation, we also email it's encryption key to you in an attachment. In case, our back-end ever goes down, you should still be able to decrypt your secrets using the key already available with you.
