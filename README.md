# Express OpenID Connect

Express.js middleware for OpenID Relying Party (aka OAuth 2.0 Client). Easily add secure and standards-based authentication to Express applications.

This library requires:

- Node v10.13 or higher
- Express v4.17 or higher

**Please Note:** This library is currently in beta status and has not had a complete security review. We **do not** recommend using this library in production yet. As we move towards general availability, please be aware that releases may contain breaking changes. We will be monitoring the Issues queue here for feedback and questions. PRs and comments on existing PRs are welcome!

[![CircleCI](https://img.shields.io/circleci/build/github/auth0/express-openid-connect/master?style=flat-square)](https://circleci.com/gh/auth0/express-openid-connect/tree/master)
[![codecov](https://img.shields.io/codecov/c/github/auth0/express-openid-connect?style=flat-square)](https://codecov.io/gh/auth0/express-openid-connect)
[![NPM version](https://img.shields.io/npm/v/express-openid-connect.svg?style=flat-square)](https://npmjs.org/package/express-openid-connect)

## Table of Contents

- [Documentation](#documentation)
- [Installation](#installation)
- [Getting Started](#getting-started)
- [Contributing](#contributing)
- [Support + Feedback](#support--feedback)
- [Vulnerability Reporting](#vulnerability-reporting)
- [What is Auth0](#what-is-auth0)
- [License](#license)

## Documentation

- Our [Express Quickstart](https://auth0.com/docs/quickstart/webapp/express) is the quickest way to get up and running from scratch.
- Use the [Examples for common configurations](https://github.com/auth0/express-openid-connect/blob/master/EXAMPLES.md) for use cases beyond the basics.
- The [API documentation](https://github.com/auth0/express-openid-connect/blob/master/API.md) details all configuration options, methods, and data that this library provides.
- You can [run the sample application](https://github.com/auth0-samples/auth0-express-webapp-sample/tree/master) to see how this SDK functions without writing your own integration.

## Installation

This library is installed with [npm](https://npmjs.org/package/express-openid-connect):

```
npm i express-openid-connect --save
```

## Getting Started

Follow our [Secure Local Development guide](https://auth0.com/docs/libraries/secure-local-development) to ensure that applications using this library are running over secure channels (HTTPS URLs). Applications using this library without HTTPS may experience "invalid state" errors.

The library needs [the following required configuration keys](https://github.com/auth0/express-openid-connect/blob/master/API.md#required-keys) to request and accept authentication. These can be configured in a `.env` file in the root of your application:

```text
# .env

ISSUER_BASE_URL=https://YOUR_DOMAIN
CLIENT_ID=YOUR_CLIENT_ID
BASE_URL=https://YOUR_APPLICATION_ROOT_URL
APP_SESSION_SECRET=LONG_RANDOM_VALUE
```

... or in the library initialization:

```js
// index.js

const { auth } = require("express-openid-connect");
app.use(
  auth({
    issuerBaseURL: "https://YOUR_DOMAIN",
    baseURL: "https://YOUR_APPLICATION_ROOT_URL",
    clientID: "YOUR_CLIENT_ID",
    appSessionSecret: "LONG_RANDOM_STRING"
  })
);
```

With this basic configuration, your application will require authentication for all routes and store the user identity in an encrypted and signed cookie.

See the [examples](EXAMPLES.md) for route-specific authentication, custom application session handling, requesting and using access tokens for external APIs, and more.

See the [API documentation](API.md) for additional configuration possibilities and provided methods.

## Contributing

We appreciate feedback and contribution to this repo! Before you get started, please see the following:

- [Auth0's general contribution guidelines](https://github.com/auth0/.github/blob/master/CONTRIBUTING.md)
- [Auth0's code of conduct guidelines](https://github.com/auth0/open-source-template/blob/master/CODE-OF-CONDUCT.md)

Contributions can be made to this library through PRs to fix issues, improve documentation or add features. Please fork this repo, create a well-named branch, and submit a PR with a complete template filled out.

Code changes in PRs should be accompanied by tests covering the changed or added functionality. Tests can be run for this library with:

```bash
npm install
npm test
```

When you're ready to push your changes, please run the lint command first:

```bash
npm run lint
```

## Support + Feedback

Please use the [Issues queue](https://github.com/auth0/express-openid-connect/issues) in this repo for questions and feedback.

## Vulnerability Reporting

Please do not report security vulnerabilities on the public GitHub issue tracker. The [Responsible Disclosure Program](https://auth0.com/whitehat) details the procedure for disclosing security issues.

## What is Auth0?

Auth0 helps you to easily:

- implement authentication with multiple identity providers, including social (e.g., Google, Facebook, Microsoft, LinkedIn, GitHub, Twitter, etc), or enterprise (e.g., Windows Azure AD, Google Apps, Active Directory, ADFS, SAML, etc.)
- log in users with username/password databases, passwordless, or multi-factor authentication
- link multiple user accounts together
- generate signed JSON Web Tokens to authorize your API calls and flow the user identity securely
- access demographics and analytics detailing how, when, and where users are logging in
- enrich user profiles from other data sources using customizable JavaScript rules

[Why Auth0?](https://auth0.com/why-auth0)

## License

This project is licensed under the MIT license. See the [LICENSE](LICENSE) file for more info.
