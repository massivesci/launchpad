# 🚀  Launchpad

Launchpad is a starting point for amazing applications.

It provides some simple setting up and configuration, so that you can just start building something!

## Summary

Launchpad uses [Docker](http://www.docker.com) to set up and run a webserver using [NodeJS](https://nodejs.org/en/), the [Feathers](http://feathersjs.com) framework, a [Postgres](http://postgresql.org) database, and [Redis](http://redis.io) caching.

It renders a user interface using [React](https://facebook.github.io/react/) and manages the UI state with [Redux](http://redux.js.org).
Navigation between pages is managed by [react-redux-router](https://github.com/reactjs/react-router-redux).

Browser assets are compiled using [Webpack](https://webpack.js.org).
A [Webpack Dev Server](https://webpack.github.io/docs/webpack-dev-server.html) is provided, with additional support for [Hot Module Replacement](https://webpack.github.io/docs/hot-module-replacement.html) and [React Hot Loader](http://gaearon.github.io/react-hot-loader/).

Launchpad's testing framework is [Mocha](http://mochajs.org), flavored with [Chai](http://chaijs.com) for assertions and expectations.
[Enzyme](http://airbnb.io/enzyme/) is included to make testing React components simple and straightforward.
Basic style and syntax patterns are enforced by [eslint](http://eslint.org), but it's also helpful for catching syntax errors as well.

## First Run

1. Install Docker by visiting [docs.docker.com](docs.docker.com) and installing the Docker application for your operating system.
2. Run `docker-compose up` inside this directory. (Optional: include the `-d` flag to suppress output.)
3. Visit `localhost:3030` from your favorite browser.

## Develop

The Docker setup provides very helpful shortcuts and configuration when running the server.
When developing an application, it is usually faster and more helpful to install software to your host machine.
Usually, you won't need to have Postgres or Redis installed on your host machine.
Just the Node software should be enough to get up and running.

### Install

We suggest using [Yarn](https://yarnpkg.com) to install packages.
It's fast and simple.

1. `npm install -g yarn`
2. `yarn`

This should install the relevant packages to your machine.

**A note on adding dependencies**

When a new dependency is added to the project, the docker containers for Feathers and Packages will need to be rebuilt, in order to install the new packages. For this reason, you may find it easier to run the Feathers and Webpack services from your own host machine, after their packages have been installed. Remember that the addresses Feathers uses for Postgres and Redis will have to be adjusted to use `localhost`, instead of their Docker-provided hosts.

## Testing

Before running tests, ensure that the Postgres and Redis services are running with `docker-compose start postgres redis`. If they are not running, the Feathers application will time out when testing request responses.

Then, simply run `npm test` and all your tests in the `test/` directory will be run.

- To run tests without linting, run `npm run mocha`.
- To run linting without tests, run `npm run lint`.

## Scaffolding

Feathers has a powerful command line interface. Here are a few things it can do:

```
$ npm install -g feathers-cli             # Install Feathers CLI

$ feathers generate service               # Generate a new Service
$ feathers generate hook                  # Generate a new Hook
$ feathers generate model                 # Generate a new Model
$ feathers help                           # Show all commands
```

Licensed under the [MIT license](LICENSE).
