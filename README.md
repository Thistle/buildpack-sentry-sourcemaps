# buildpack-sentry-sourcemaps

Heroku buildpack to upload sourcemaps to Sentry using `sentry-cli`.
Note from Michael: this buildpack is not being used on Thistle apps. The main issue I encountered when using this method of giving release info to Sentry is that it doesn't run on promotion to production. Since we have a two-part prod pipeline, the release finalization should be sent on promotion.

## Usage

Define the following configuration variables within Herkou app. See [Heroku Documentaiton](https://devcenter.heroku.com/articles/config-vars) for more informaiton.

- `SENTRY_AUTH_TOKEN`: the Sentry API authentication token
- `SENTRY_ORG`: the Sentry organization the project lives under
- `SENTRY_PROJECT`: the Sentry project the source maps belong too

## Getting Sentry Auth Token

You can get it on the [API page][]. The token needs the `project:write` scope to be able to upload. The token value would be saved as the `SENTRY_AUTH_TOKEN` configuration variables.

## License

MIT.


[Heroku buildpack]: https://devcenter.heroku.com/articles/buildpacks
[Sentry]: https://sentry.io/
[docs]: https://docs.sentry.io/clients/javascript/sourcemaps/
[API page]: https://sentry.io/api/
