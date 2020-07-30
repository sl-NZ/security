
# Scenario: SecureWorld 
The team are super keen on removing secrets and configuration values from code and moving these into secure encrpyted methods that are passed at deploy time.

You've been asked to move some secerts that are currently in code to be passed by the pipeline during the deploy job.

## Pre-requisites
* GitHub account. If you don't have one it's free to set one up
* Your favourite text editor

## Getting Started
1. Clone this repo into a free public Github repo
2. Create a branch off `master`. Call it `security`
3. Commit your changes against the `security` branch 
4. The initial commit into github will dynamically create [CI/CD actions workflow](https://docs.github.com/en/actions) using `.github/workflows/dotnet-core.yml`

# Requirements
1. After the artifact is created we are keen to pass values just before final deploy to  `appSettings.Json` file that the app will consume.
2. Update the `dotnet-core.yml` workflow to add two steps before the `pretend_deploy` step:
    - One: Substitute a value for the key `DisplaySecretInfo` in  `appsettings.json` file using Github Secrets
    - Two: Output the contents of the appSettings.Json to stdout

3. Once you're done send us a link to your repo

## Tips
* Checkout [Github Secrets](https://docs.github.com/en/actions/configuring-and-managing-workflows/creating-and-storing-encrypted-secrets)
* We like some of [these principles](https://12factor.net/config) of configuration management being kept out of the artifact 
* DotNet Core Apps hold Secrets and configration in `appsettings.json` files.