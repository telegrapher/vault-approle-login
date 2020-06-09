# vault-approle-login
Utility to perform **AppRole authentication** in Hashicorp Vault.

This small CLI utility performs an AppRole login and returns the Vault token to be later used.

It is only one API call, as explained in Vault's [documentation](https://www.vaultproject.io/docs/auth/approle.html#via-the-api), but it is worth having an specialized CLI tool to be able to:
- Perform retries and good error management.
- Use parameters to personalize the API call if needed.
- Show extra information in STDERR.
- Safely use environment variables without showing credentials in any shell history.

## Usage
This tool has been created to retrieve a Vault token using approle login. This is very useful, for example, in combination with [envconsul](https://github.com/hashicorp/envconsul)
```
export VAULT_ROLE_ID="MY_ROLE_ID"
export VAULT_SECRET_ID="MY_SECRET_ID"
export VAULT_TOKEN=$(vault-approle-login)
envconsul -secret="victoria/secrets" another-command
```
