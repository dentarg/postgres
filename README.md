# postgres

`dentarg/postgres` is an [composite run steps action] that starts PostgreSQL in the GitHub Action VM and creates a user and a database. You can then connect to the database over the "local socket" using the address found in environment variable `POSTGRES_URL`.

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
