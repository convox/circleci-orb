# convox/circleci-orb

CircleCI Orb for deploying to Convox.

# Usage

## Sign Up for CircleCI
If you don’t have an account already, [sign up for CircleCI](https://circleci.com/signup/).

## Configure Your CircleCI Project to Build With Convox
 Setup your project in CircleCI by clicking [here](https://circleci.com/docs/2.0/gh-bb-integration/#section=projects).

 After adding your project, login to the Convox console and click on the settings tab in navigation bar which is on the left side.

 Generate a [deploy key](https://docs.convox.com/console/deploy-keys) and copy it to your local clipboard.

 Now in CircleCI, [add an environment variable](https://circleci.com/docs/2.0/env-vars/#setting-an-environment-variable-in-a-project) with the name CONVOX_DEPLOY_KEY and paste your deploy key as the value.

 ## Build a CircleCI config.yml Using the Convox Orb
 ## ( Note: You must specify version: 2.1 in your config.yml in order to use Orbs )
The Convox Orb contains a single deploy command and matching job for deploying your app to Convox using CircleCI.

The job is self contained. If you would prefer to use the command you must run the checkout command before using deploy.

The deploy Job/Command accepts the following parameters:
![parameters](assets/image.jpg?raw=true "Parameters")

## Examples
config.yml
----------------------------------------------------
version: 2.1
orbs:
  convox: convox/orb@1.4.1
workflows:
  deploy:
    jobs:
      - convox/deploy:
          rack: production
          app: example

This will build and deploy your app in a single step.

If you would prefer to use the Convox Orb commands directly you need to run the checkout command before deploy:
----------------------------------------------------
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

For Further information: https://docs.convox.com/external-services/circleci

## See Also

https://circleci.com/orbs/registry/orb/convox/orb

## License

MIT
