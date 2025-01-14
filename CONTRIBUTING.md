# Welcome to the Amibot contributing guide

Thank you for investing your time in contributing to our project! :sparkles:.

In this guide you will get an overview of the contribution workflow from opening an issue, creating a PR, reviewing, and merging the PR.

Use the table of contents icon on the top left corner of this document to get to a specific section of this guide quickly.

## New contributor guide

To get an overview of the project, read the [README](README.md). Here are some resources to help you get started with open source contributions:

- [Finding ways to contribute to open source on GitHub](https://docs.github.com/en/get-started/exploring-projects-on-github/finding-ways-to-contribute-to-open-source-on-github)
- [Set up Git](https://docs.github.com/en/get-started/quickstart/set-up-git)
- [GitHub flow](https://docs.github.com/en/get-started/quickstart/github-flow)
- [Collaborating with pull requests](https://docs.github.com/en/github/collaborating-with-pull-requests)

## Getting started

Check to see what [types of contributions](/contributing/types-of-contributions.md) we accept before making changes. Some of them don't even require writing a single line of code :sparkles:.

### Issues

#### Create a new issue

If you encounter an issue with Amibot, [search if an issue already exists](https://docs.github.com/en/github/searching-for-information-on-github/searching-on-github/searching-issues-and-pull-requests#search-by-the-title-body-or-comments). If a related issue doesn't exist, you can open a new issue using a relevant issue tag.

#### Solve an issue

Scan through our [existing issues](https://github.com/asetalias/amibot/issues) to find one that interests you. You can narrow down the search using `labels` as filters. As a general rule, you should ask to be asigned to the issue you want to work on. However, you can open a PR for an issue even if you're not assigned!

### Make Changes

#### Make changes locally

1. Fork the repository.

- Using Github Web :
  - Directly click on fork and make changes in the local repository on your github account.
 ![image](https://user-images.githubusercontent.com/64458111/193403656-7fad4e89-d7b0-4f3a-be64-64bf3b32c0f1.png)

- Using GitHub Desktop:
  - [Getting started with GitHub Desktop](https://docs.github.com/en/desktop/installing-and-configuring-github-desktop/getting-started-with-github-desktop) will guide you through setting up Desktop.
  - Once Desktop is set up, you can use it to [fork the repo](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/cloning-and-forking-repositories-from-github-desktop)!

- Using the command line:
  - [Fork the repo](https://docs.github.com/en/github/getting-started-with-github/fork-a-repo#fork-an-example-repository) so that you can make your changes without affecting the original project until you're ready to merge them.

### Project setup -- Prerequisites

This describes the setup you need to test and run this application on your local computer.

#### [Node.JS](https://nodejs.org/en/download/)

Amibot needs Node version 18+ -- use [`nvm`](https://github.com/nvm-sh/nvm) for easy setup.

#### WhatsApp Business Cloud API

Amibot uses the [WhatsApp Business Cloud API][wa-business-cloud-api] to send and recieve messages on WhatsApp. Here's how you can get started:

- [Setup a facebook developer account](https://developers.facebook.com/)
- [Get started with WhatsApp Business Cloud API][wa-business-cloud-api]
- Add a test number so you can interact with your local deployment of the bot.
- Setup a webhook for whatsapp events (once you start Amibot and ngrok).

#### [MongoDB](https://www.mongodb.com/)

Amibot uses MongoDB to persist user state. You can either use the hosted MongoDB Atlas (recommended)
or spin up an instance locally.

- [Create a DB on MongoDB Atlas][mongodb-atlas].

#### The `.env` file

Make a `.env` file by copying `.env.sample` and populating the `WHATSAPP_TOKEN`, `VERIFY_TOKEN` (token used for facebook ) and other fields.

#### ngrok

  We need to expose the local web server to the internet so we can set up a WhatsApp webhook for the Amibot instance. [ngrok][ngrok] is an easy-to-use service that lets us do just that!
  Steps to setup:

- Create account on <https://ngrok.com>.
- Install the ngrok CLI.
- Login to your ngrok account: `ngrok config add-authtoken <authtoken>`
- Expose the local Amibot instance with `ngrok http 3000 --region us` (the region is important --
    facebook currently blocks other ngrok regions.
- Use `<ngrok-url>/webhook` as the webhook URL on the Meta developer portal.

### Project Setup -- Starting Amibot

`yarn dev` to start Amibot with live-reload (the bot will restart with each change you make to the code).

### Commit your update

Commit your changes to a new branch once you're happy with them.
See [Conventional Commits][conventional-commits] -- a lightweight convention
for commit messages we recommend for contributions to Amibot.

![image](https://user-images.githubusercontent.com/64458111/193404058-2af44221-77d0-4544-94c1-d48217935e8a.png)

### Pull Request

![image](https://user-images.githubusercontent.com/64458111/193404133-741c5664-5c12-45aa-a904-040957e5ac64.png)

When you're finished with the changes, create a pull request, also known as a PR.

- Fill the "Ready for review" template so that we can review your PR. This template helps reviewers understand your changes as well as the purpose of your pull request.
- Don't forget to [link PR to issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue) if you are solving one.
- Enable the checkbox to [allow maintainer edits](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/allowing-changes-to-a-pull-request-branch-created-from-a-fork) so the branch can be updated for a merge.
Once you submit your PR, a Docs team member will review your proposal. We may ask questions or request for additional information.
- We may ask for changes to be made before a PR can be merged, either using [suggested changes](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/incorporating-feedback-in-your-pull-request) or pull request comments. You can apply suggested changes directly through the UI. You can make any other changes in your fork, then commit them to your branch.
- As you update your PR and apply changes, mark each conversation as [resolved](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/commenting-on-a-pull-request#resolving-conversations).
- If you run into any merge issues, checkout this [git tutorial](https://github.com/skills/resolve-merge-conflicts) to help you resolve merge conflicts and other issues.

### Your PR is ready

Congratulations :tada::tada: The Amity student body thanks you :sparkles:

We'll follow up your PR with reviews and suggestions that might require you to work more on your contributions to get them ready.

Once your PR is merged, your contributions will be publicly visible!

[conventional-commits]: https://www.conventionalcommits.org/en/v1.0.0/
[ngrok]: https://www.conventionalcommits.org/en/v1.0.0/
[mongodb-atlas]: https://www.conventionalcommits.org/en/v1.0.0/
[wa-business-cloud-api]: https://developers.facebook.com/docs/whatsapp/cloud-api/
