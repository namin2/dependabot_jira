# Dependabot Jira

This workflow creates a Jira issue when a Dependabot pull request is created with a specific label. It will set the summary of the Jira issue to the title of the Dependabot pull request and the description of the issue to the body of the pull request. It accomplishes this by leveraging two Atlassian Github Actions.

- [Jira Create Action v3.0.1](https://github.com/atlassian/gajira-create/tree/v3.0.1)

- [Jira Login Action v3.0.1](https://github.com/atlassian/gajira-login/tree/v3.0.1)

## Setup
1. Copy `dependabot_jira.yml` into `.github/workflows` folder in your repository
2. Set environment variables in your repository. Instructions can be found [here](https://help.github.com/en/actions/configuring-and-managing-workflows/creating-and-storing-encrypted-secrets#creating-encrypted-secrets)
3. IMPORTANT: The Secret for `JIRA_API_TOKEN` must be added as a Dependabot secret, not an Actions secret. (This is very unclear in the documentation)
4. If you so desire, change the lookup context in lines 11-15 to determine whether the values are lookups from Variables or Dependabot Secrets context.

    - Variables for login
      - `JIRA_BASE_URL` - Example: `https://example.atlassian.net`
      - `JIRA_API_TOKEN` - [Token Generation Instructions](https://confluence.atlassian.com/cloud/api-tokens-938839638.html)
      - `JIRA_USER_EMAIL`
    - Variables for issue creation
      - `JIRA_PROJECT` - Example: `JIRA`
      - `JIRA_ISSUE_TYPE` - Example: `Story`
