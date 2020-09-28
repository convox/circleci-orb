# convox/circleci-orb

CircleCI Orb for deploying to Convox.

## Description

The Convox Orb allows CircleCI users to easily deploy their application to AWS ECS, and soon AWS EKS, via Convox, with a single command, as part of their CircleCI workflow.

__NOTE__: In order to make use of the Convox Orb you must first have a Convox account at the Basic level or above and a CircleCI account.

## Usage

[https://docs.convox.com/external-services/circleci](https://docs.convox.com/external-services/circleci)

### Usage Examples

#### deploy

Deploy your application to Convox using the jobs from this orb:

```yaml
version: 2.1
orbs:
  convox: convox/orb@1.4.1
workflows:
  deploy:
    jobs:
      - checkout
      - convox/deploy:
          rack: production
          app: example
```

#### test_and_deploy

Customize your workflow using the commands from this orb:

```yaml
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

You will need to set the `CONVOX_PASSWORD` environment variable on your project to your Convox deploy key.

## See Also

[https://circleci.com/orbs/registry/orb/convox/orb](https://circleci.com/orbs/registry/orb/convox/orb)

## License

MIT
