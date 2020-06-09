# vault-approle-login
Utility to perform an Approle login in Hashicorp Vault

This small CLI utility performs an Approle login and returns the Vault token to be later used.

It is only one API call, as explained in https://www.vaultproject.io/docs/auth/approle.html#via-the-api, but it is worth having an specialized CLI tool to be able to:
- Perform retries and good error management.
- Use parameters to personalize the API call if needed.
- Show extra information in STDERR.
