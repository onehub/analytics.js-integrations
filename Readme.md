
# analytics.js-integrations [![Build Status](https://travis-ci.org/segmentio/analytics.js-integrations.png)](https://travis-ci.org/segmentio/analytics.js-integrations)

This repository houses all of the integrations that get built into [Analytics.js](https://github.com/segmentio/analytics.js).

All new integrations are added by pull requests, just read the [contribution docs](/Contributing.md) to get started and submit your own! If you ever need any help, feel free to email [friends@segment.io](mailto:friends@segment.io).


## Developing

This repository relies on a couple dependencies that help make our lives easier while developing. They are:

  - [`analytics.js-integration`](https://github.com/segmentio/analytics.js-integration), which is a factory for creating `Integration` constructors, that helps us share lots of the common logic in one place.

  - [`analytics.js-integration-tester`](https://github.com/segmentio/analytics.js-integration-tester), which is a testing helper that wraps an integration and simplifies lots of the testing logic. It's similar to how [`supertest`](https://github.com/visionmedia/supertest) works for [Superagent](https://github.com/visionmedia/superagent).

To get started with development, you need to be running node 0.11.x, an easy way to get it is

    $ npm install -g n
    $ n 0.11

Make sure you have `~/.netrc` setup like:

```text
machine api.github.com
  user <user>
  password <token>
```

  [Here's how you can create a token](https://help.github.com/articles/creating-an-access-token-for-command-line-use).

Then clone the repository and then inside of it run:

    $ make

That will downloaded all of the dependencies needed, and build the test-ready files. Then, edit as you please, adding new integrations or editing the logic of an existing integration. When you are ready to test run:

    $ make test

That will automatically lint all of the Javascript, and run the entire test suite for each integration. For convenience, you can also limit the tests to just the integration you're working with like so:

    $ make test integration=kissmetrics

And if you'd like you debug in the browser, run:

    $ make test-browser
    $ make test-browser integration=customerio

Once your tests pass, you are ready to submit a pull request!

