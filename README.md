# convox/circleci-orb

CircleCI Orb for deploying to Convox.

## Usage

# Sign Up for CircleCI
If you don’t have an account already, [sign up for CircleCI](https://circleci.com/signup/).

# Configure Your CircleCI Project to Build With Convox
 Setup your project in CircleCI by clicking [here](https://circleci.com/docs/2.0/gh-bb-integration/#section=projects).

 After adding your project, login to the Convox console and click on the settings tab in navigation bar which is on the left side.

 Generate a [deploy key](https://docs.convox.com/console/deploy-keys) and copy it to your local clipboard.

 Now in CircleCI, [add an environment variable](https://circleci.com/docs/2.0/env-vars/#setting-an-environment-variable-in-a-project) with the name CONVOX_DEPLOY_KEY and paste your deploy key as the value.

## See Also

https://docs.convox.com/external-services/circleci
https://circleci.com/orbs/registry/orb/convox/orb

## License

MIT
