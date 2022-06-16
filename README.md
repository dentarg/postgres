# postgres

`dentarg/postgres` is an [composite run steps action] that starts PostgreSQL in the GitHub Actions VM and creates a user and a database. You can then connect to the database using the address found in environment variable `POSTGRES_URL`.

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: dentarg/postgres@v1
    - run: <your test command>
      env:
        DATABASE_URL: "${{ env.POSTGRES_URL }}" # or use POSTGRES_URL directly
```

[composite run steps action]: https://docs.github.com/en/free-pro-team@latest/actions/creating-actions/creating-a-composite-run-steps-action

See the [GitHub Actions Virtual Environments](https://github.com/actions/virtual-environments/#available-environments) repo to understand what version of PostgreSQL will be used.
