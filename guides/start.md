---
description: The only page you'll need to read.
---

# Getting Started

## Onboarding

First of all, signup on the platform by going [here](https://app.envsecrets.com). It is recommended you onboard with your Github account.

Once your account is created, we will automatically create a "default" organisation for you to get started quickly.

## Setup CLI

Step 1: Download the CLI

{% content-ref url="../cli/install-and-upgrade.md" %}
[install-and-upgrade.md](../cli/install-and-upgrade.md)
{% endcontent-ref %}

Step 2: Login to your CLI. If you signed-up using Oauth/social providers like Github, just click on your avatar in the header and use the "change password" option to manually set a new account password for yourself.

```sh
envsecrets login
```

Step 3: Change directory to your project root: `cd my-project`

Step 4: Intialize envsecrets in your project root.

```sh
envsecrets init
```

## Set Your First Secret

Step 1: Set your first secret.

```sh
envsecrets set DB_PASSWORD=password
```

Step 2: To check whether your key-value pair has been set properly or not, simply fetch latest version of secrets for this environment.

```sh
envsecrets export
```

Step 3: Inject your secrets in the shell and natively access them in your process.

```sh
envsecrets run -- npm run dev
```

For more information regarding other commands of the CLI, you can always use the `--help` flag.

## Add Your First Integration

As an example, we will add the Github Actions integration to your organisation.

1. After logging in to your dashboard, choose your preferred organisation from the header.
2. Go to "integrations" tab on left-top corner.
3. Choose the "Github Actions" integration from the catalog.
4. Once you complete the app authentication flow with Github and give relevant permissions to our app for your repositories, it will route you back to the platform and notify regarding integration status.

## Enable Your First Event

1. Choose any project in your organisation. You can create a new one from the dashboard if you don't already have any projects.
2. Choose your preferred environment in that project. For example, the "dev" environment.
3. Use the "new event" option on the events tab in your environment's route to choose the Github actions integration.
4. After you choose your preferred integration, it will take some time to fetch the available entities for that integration. In this case, it will fetch your github repositories.
5. Choose your preferred Github repository with which you want to sync this environment's secrets.
6. Once the event is created, wait for 15 seconds and go to your Github repository's settings page. Check the actions secrets section. Your `envsecrets` variables should now be available natively in your repository's actions pipelines. You can directly use them in your Github workflow pipelines with Github's standard syntax of `{{secrets.DB_PASSWORD}}`.
7. Everytime you will update your variables, either with `envsecrets set` or `envsecrets delete`, it will automatically update the relevant values in your repository's actions secrets.

## ProTip!

If you want your variables to not be encrypted, and made available in your Github repository's "variables" and not "secrets", simply set your values in the CLI by disabling the `--encrypt` flag.

```sh
envsecrets set PORT=5000 --encrypt=false
```

Enjoy!
