# GitHub Action for ZEIT

This Action wraps the [Now CLI](https://github.com/zeit/now-cli) to enable common Now commands.

## Usage

```yml
name: Deploy on Now
on: [push]
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@master
      - name: deploy
        uses: actions/zeit-now@master
        env:
          ZEIT_TOKEN: ${{ secrets.ZEIT_TOKEN }}
      - name: alias
        uses: actions/zeit-now@master
        env:
          ZEIT_TOKEN: ${{ secrets.ZEIT_TOKEN }}
        with:
          args: alias
```

For more examples, visit: [actions/example-zeit-now](https://github.com/actions/example-zeit-now).

### Secrets

- `ZEIT_TOKEN` - **Required**. The token to use for authentication with the ZEIT Now API ([more info](https://zeit.co/blog/introducing-api-tokens-management))

## License

The Dockerfile and associated scripts and documentation in this project are released under the [MIT License](LICENSE).

Container images built with this project include third party materials. See [THIRD_PARTY_NOTICE.md](THIRD_PARTY_NOTICE.md) for details.
