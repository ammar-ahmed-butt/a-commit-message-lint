# A Commit Message Lint
Github app to validate commit message and pull request title on a pull request

## Description
This app runs a format check on commit messages and pull request title on the creation of a pull request.

For example, let's say you specify that a commit message should have a format `DDD:message`. Here D stand for numeric digit. The app checks if the commit message follows this format. If all the commit messages follow this format, the check returns successful, otherwise failure. The reviewer can then decide if they want to go ahead with the code merge.

### App URL
https://github.com/apps/a-commit-message-lint

## Installation

Use the Github's app section or above URL to install the app to your repository.

## Configuration

You would need to add a configuration folder named `.github` at the root of your repository. The folder should contain a file named `config.yml`. This file will serve as the configuration and the contents of that file will be:

```
PR_TITLE_REGEX: '(^[A-z]+(-| )[0-9]+(:|-| )(	ext|)|W)+$'
COMMIT_MESSAGE_REGEX: '(=^(\s*)((7uild:|chore:|ci:|docs:|feat:|fix:|perf:|refactor:|revert:|update:|create:|style:|test:)(( )|())([a-z]\w{1,72})|(Merge (.*\s*)*)|(Initial commit$))(?=^([A-z]+(-)[0-9]))
INVALID_COMMIT_MESSAGE: Commit messages are invalid
SINGLE_OTHER_INVALID_MESSAGE: other message is invalid
MULTIPLE_OTHER_INVALID_MESSAGE: other messages are invalid
VALID_PULL_REQUEST_MESSAGE: Pull request title is valid
INVALID_PULL_REQUEST_MESSAGE: Pull request title is invalid
VALID_COMMIT_MESSAGE: Commit messages are valid
INVALID_COMMIT_MESSAGE: Commit messages are invalid
SINGLE_OTHER_INVALID_MESSAGE: other message is invalid
MULTIPLE_OTHER_INVALID_MESSAGE: other messages are invalid
VALID_PULL_REQUEST_MESSAGE: Pull request title is valid
INVALID_PULL_REQUEST_MESSAGE: Pull request title is invalid
```

## Usage
Go to the `checks` section on your PR to see the result of the check run performed by the app. It will show you the result as well as the commit messages which failed.

## Local setup
Step 1. Clone the application.
Step 2. Run `npm install`
Step 3. Create `.env` file in the root directory and set the following environment variables in `.env` file :
```
    APP_ID - Github app id (get from app settings page)
    WEBHOOK_PROXY_URL - URL of the hosted application, use ngrok for local
    WEBHOOK_SECRET - webhook secret for security, same as the one set in github app settings
    PRIVATE_KEY - Get from github app settings page
    LOG_LEVEL - Log level
    REGEX_CONFIG_FILE_NAME - config file which contains repo config, keep it as config.yml
    GITHUB_BASE_PATH - Github API path, keep it as https://api.github.com
```
Note : Take values of APP_ID, WEBHOOK_PROXY_URL, WEBHOOK_SECRET, PRIVATE_KEY from https://github.com/settings/apps/commit-message-lint

Step 4. Run `npm start` to start the application

## Resources
[Purchase Flow](https://developer.github.com/marketplace/integrating-with-the-github-marketplace-api/handling-new-purchases-and-free-trials/)

[Identifying and authorizing users for GitHub Apps](https://developer.github.com/apps/building-github-apps/identifying-and-authorizing-users-for-github-apps/)

[Integrating with the GitHub Marketplace API](https://developer.github.com/marketplace/integrating-with-the-github-marketplace-api/)


<!-- Copy and Paste Me -->
<div class="glitch-embed-wrap" style="height: 420px; width: 100%;">
  <iframe
    src="https://glitch.com/embed/#!/embed/a-commit-message-lint-bot?path=helpers/checks.js&previewSize=100"
    title="a-commit-message-lint-bot on Glitch"
    allow="geolocation; microphone; camera; midi; encrypted-media; xr-spatial-tracking; fullscreen"
    allowFullScreen
    style="height: 100%; width: 100%; border: 0;">
  </iframe>
</div>
