# convox/circleci-orb

CircleCI Orb for deploying to Convox.Deploy and manage any app
# Features 

### Easy Configuration
Setup a production ready Kubernetes or ECS cluster in minutes with one click. No fussing with templates or scripts.
### Continuous Delivery
Deploy seamlessly from Github or Gitlab. Automatically test every pull request and deploy every change.
### Infrastructure as Code
GitOps made easy. Configure your entire environment from local development through to staging and production with a single yaml file. No more maintaining and synchronizing massive templates and scripts.
### Local Development
Onboard new team members in minutes instead of days. Need more power for development? Use our cloud native development feature and never melt your laptop down again.
### Zero Downtime Deploys
Lighting fast, rolling deploys including running migrations or any other pre or post deployment scripts, with zero downtime.
### One-Click Rollbacks
No more troubleshooting a bad release in the middle of the night. Quickly rollback to any previous release, including environment changes, with one click.
### Secrets Management
Securely store secrets, passwords, tokens and keys in an encrypted vault isolated per environment.
### Audit Trails
Maintain a full history of all deployments, one-off commands, and configuration changes. Centralize all your logs for a complete view of your applications. Use our log viewer or stream all your logs to a 3rd party service.
### Secure by Default
Fully automated security configuration avoids dangerous mistakes. Role based access control and hardware 2fa protects your applications. Self hosted enterprise options available to meet your PCI and HIPAA compliance needs

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

You will need to set the `CONVOX_PASSWORD` environment variable on your project to your Convox deploy key.

## See Also

https://circleci.com/orbs/registry/orb/convox/orb

## License

MIT
