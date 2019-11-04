# convox/circleci-orb

CircleCI Orb for deploying to Convox.

## Description

The Convox Orb allows CircleCI users to easily deploy their application to AWS ECS, and soon AWS EKS, via Convox, with a single command, as part of their CircleCI workflow.

__NOTE__: In order to make use of the Convox Orb you must first have a Convox account at the Basic level or above and a CircleCI account.

## Usage

https://docs.convox.com/external-services/circleci

As an example if you have a Convox rack named “production” and a Convox app named “example” you can deploy with the following config.yml:

```
version: 2.1
orbs:
  convox: convox/orb@1.4.1
workflows:
  deploy:
    jobs:
      - deploy
jobs:
  deploy:
    executor: convox/cli
    steps:
      - checkout
      - run: make test
      - convox/deploy:
          rack: production
          app: example
```

## See Also

https://circleci.com/orbs/registry/orb/convox/orb

## License

MIT
