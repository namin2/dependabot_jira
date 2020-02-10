# Dependabot Jira

This workflow creates a Jira issue when a Dependabot pull request is created with a specific label. It will set the summary of the Jira issue to the title of the Dependabot pull request and the description of the issue to the body of the pull request. It accomplishes this by leveraging two Atlassian Github Actions.

- [Jira Create Action v2.0.0](https://github.com/atlassian/gajira-create/tree/v2.0.0)

- [Jira Login Action v2.0.0](https://github.com/atlassian/gajira-login/tree/v2.0.0)

## Setup
1. Copy dependabot_jira.yml into .github/workflows folder in your repository
2. Set environment variables in your repository. Instructions can be found [here](https://help.github.com/en/actions/configuring-and-managing-workflows/creating-and-storing-encrypted-secrets#creating-encrypted-secrets)
    - Variables for login
      - `JIRA_BASE_URL` - Example: `https://example.atlassian.net`
      - `JIRA_API_TOKEN` - [Token Generation Instuctions](https://confluence.atlassian.com/cloud/api-tokens-938839638.html)
      - `JIRA_USER_EMAIL`
    - Variables for issue creation
      - `JIRA_PROJECT_KEY` - Example: `JIRA`
      - `JIRA_ISSUE_TYPE` - Example: `Story`
## Configuration
Currently the default label is `dependencies` but this can be changed to use the [default label](https://Dependabot.com/docs/config-file/#default_labels) used in the repository
