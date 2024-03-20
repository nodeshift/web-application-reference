
# Web Application Reference

## Overview

The goal of the Web Application Reference is to present
the `teams` 'opinion' on what components our customers
and internal teams should use when building Web applications
and guidance for how to be successful in production with those components.

The components in this architecture are what we recommend to help internal
and external customers get started based on our experience. Other components may be equally
good, but these are the ones we know best and have the most experience with.

- Where possible the opinion is based on what we've used internally and in our customer engagements.
- The components specified will be our first priority for our contributions to open source projects in the JavaScript ecosystem.
- Due to the above these are the components the `team` is best positioned when working with internal and external customers.
  However, we do not include formal support for these components in any of our support offerings unless specifically identified
  in those offerings.
- The recommended components may change over time as technologies and approaches change.

### The team

The `team` consists of engineers from across groups within IBM and Red Hat who:

- are actively engaged in the JavaScript/Node.js community
- have large Web applciation deployments
- provide consulting advice and/or development related to building Web applications for customers
- develop/deliver JavaScript components

### Key tenets

- Whenever possible components should have been validated at scale within the `team's`
  JavaScript/Node.js deployments or in engagements with our customers.
- We need to consider licensing and other due diligence when mentioning components.
- The Web Application Reference focuses on the front-end, the existing [Node.js Reference
  Architecture](https://github.com/nodeshift/nodejs-reference-architecture)
  is the corresponding reference with a focus on the back-end.

## Components

The reference architecture covers the following components (currently a work in progress with only a subset of sections having recommendations):

- Functional Components
  - Common
  - Back End
    - [Web Framework](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/functional-components/webframework.md)
    - [Template Engines](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/functional-components/template-engines.md)
    - [Message Queuing](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/functional-components/message-queuing.md)
    - [Internationalization](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/functional-components/internationalization.md)
    - [GraphQL](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/functional-components/graphql.md)
    - [Databases](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/functional-components/databases.md)
    - [Authentication and Authorization](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/functional-components/auth.md)
    - [Data Caching](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/functional-components/data-caching.md)
    - [REST API Development](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/functional-components/rest-api-development.md)
    - [Load Balancing, Scaling and Multi-threading](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/functional-components/scaling-multi-threading.md)
    - [Consuming Services](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/functional-components/consuming-services.md)
    - [Node versions/images](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/functional-components/nodejs-versions-images.md)
    - [Transactions_handling](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/functional-components/transaction-handling.md)
  - Front End
    - Front End Frameworks
    - Web Components
    - Offline
    - Local Storage
    - Authentication/Authorization
    - [Cross Platform](docs/front-end/cross-platform.md)
    - Polyfills
    - State management
    - Graphics, Visualization, Charts
    - 3D modeling
    - Caching
    - Routing
- Development
  - Common Elements
    - [Choosing and vetting dependencies](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/development/dependencies.md)
    - [Static Assets](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/functional-components/static-assets.md)
    - [Protecting Code](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/development/protecting-code.md)
    - Code Quality
      - [Code Consistency](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/development/code-consistency.md)
      - [Testing](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/development/testing.md)
      - [Code Coverage](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/development/code-coverage.md)
      - [TypeScript](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/development/typescript.md)
    - [Cross Origin Communication](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/development/cross-origin.md)
    - [CI/CD](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/development/ci-cd.md)
    - Npm
      - [Npm Proxy / Internal Registries](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/development/npm-proxy.md)
      - [Npm Publishing](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/development/npm-publishing.md)
      - [Package Development](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/development/npm-package-development.md)
    - [Secure Development Process](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/development/secure-development-process.md)
  - Backend Development
    - [Typical Development Workflows](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/development/dev-flows.md)
    - [Kubernetes-based Development Environment](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/development/kubernetes-dev-environment.md)
    - [Building good containers](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/development/building-good-containers.md)
    - [Accessibility](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/development/accessibility.md)
    - [Serverless](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/development/serverless.md)
  - Front-end Development
    - Typical Development Workflows
    - Build tools
    - Back end communication
    - Styles
    - Accessibility
    - Project layout
    - Rendering
    - Performance
    - Security
- Operations
  - Common
  - Back-end
    - Monitoring
      - [Logging](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/operations/logging.md)
      - [Metrics Collection](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/operations/metrics.md)
      - [Health Checks](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/operations/healthchecks.md)
      - [Distributed Tracing](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/operations/distributed-tracing.md)
    - [Problem Determination](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/operations/problem-determination.md)
    - [Failure Handling](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/operations/failurehandling.md)
  - Front-end
    - Monitoring
      - Logging
      - Metrics Collection
      - Health Checks
      - Distributed Tracing
    - Problem Determination
    - Failure Handling
    - Deployment
    - Externalizing Environment variables

## Contributing

To Contribute to this project, please see the [Contributing Guide](./CONTRIBUTING.md).

## Contributors

- David Sint - Senior Technical Consultant - IBM
