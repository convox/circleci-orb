# convox/circleci-orb

CircleCI Orb for deploying to Convox.

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

## See Also

[https://circleci.com/orbs/registry/orb/convox/orb](https://circleci.com/orbs/registry/orb/convox/orb)

## License

MIT
