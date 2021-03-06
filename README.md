# audit-log-service

> Simple logging service for sammler.

[![CircleCI](https://img.shields.io/circleci/project/github/sammler/audit-log-service.svg)](https://circleci.com/gh/sammler/audit-log-service)

## Purpose
_audit-log-service_ is a very simple logging service, which just acts as a temporary solution to get some logging up and running.

It logs to MongoDB and exposes some endpoints to create and to retrieve logs.

The solution was primarily created, because the [ELK-stack](https://github.com/deviantony/docker-elk) just felt to heavy (> 1.5 GB RAM needed) for _sammler_.

## Configuration
_audit-log-service_ can be configured by the following environment variables:

**General:**

- `PORT` - The port to run the REST API (defaults to `3004`).

**MongoDB:**

- `MONGODB_DEBUG` - Whether to use the Mongoose debug mode or not, defaults to `false`.
- `MONGODB_HOST` - MongoDB host, defaults to `localhost`.
- `MONGODB_PORT` - MongoDB port, defaults to `27017`. 
- `MONGODB_DATABASE` - MongoDB database, defaults to `sammlerio`.

**NATS-STREAMING:**

- `NATS_STREAMING_HOST`
- `NATS_STREAMING_PORT`

## Features
The functionality of _audit-log-service_ is documented in a swagger file, available at [http://localhost:3004/api-docs](http://localhost:3004/api-docs) when running the image.

Alternatively api-docs is also available [here](./docs/api-docs.md).

## Development
Run 

```sh
$ npm run dc-dev-up
```

Which will spin up a MongoDB instance at port 27018 (to prevent conflicts with the default port).

Then run the tests:

```
$ npm run test
```

## Author
**Stefan Walther**

* [twitter](http://twitter.com/waltherstefan)  
* [github.com/stefanwalther](http://github.com/stefanwalther) 
* [LinkedIn](https://www.linkedin.com/in/stefanwalther/) 

## License
MIT

