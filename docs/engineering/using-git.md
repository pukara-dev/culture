# Pukara's git guidelines

Git, the industry-standard version control system, plays a pivotal role in Pukara's development workflow. This guide is designed to equip you with essential information and best practices, enabling effective collaboration, seamless change tracking, and efficient project management with Git. Whether you are an experienced developer or new to version control, this comprehensive resource will guide you through our specific utilization of Git within Pukara and demonstrate its seamless integration with our processes, including Jira

We hold certain principles in high regard:

1. Aim, whenever possible, to maintain a 1:1 relationship between Jira issues and pull requests (PRs). Avoiding the completion of multiple tasks within a single PR is considered best practice.
2. We have implemented a Jira-Github integration. We strongly encourage everyone to utilize this feature.

## Commits

A commit is a snapshot of changes made to a Git repository, representing a specific point in the project's history. The following are the rules we follow when committing code to our repositories.

- Write commit messages in English.
- Commits should not group an excessive amount of changes. Ideally, commits should encompass concise functionalities or a small set of changes that accomplish a specific task.
- Avoid the pattern of a single large commit. Instead, it is recommended to break it down into smaller commits.
- When working with a Pull Request that involves multiple Jira tickets, it is a useful practice to link the commit message to your respective Jira issues. For example, you can use the following format: `git commit -m "JRA-123: <commit message>"`.
- The commit subject contains a concise description of the change. It is recommended to use the imperative form in the present tense. For example, use "change" instead of "changed" or "changes". Also, avoid placing a dot (.) at the end of the subject.



???+ tip "From [The seven rules of a great Git commit message](https://cbea.ms/git-commit/#seven-rules)"

    1. Separate subject from body with a blank line
    2. Limit the subject line to 50 characters
    3. Capitalize the subject line
    4. Do not end the subject line with a period
    5. Use the imperative mood in the subject line
    6. Wrap the body at 72 characters
    7. Use the body to explain what and why vs. how

## Branches

### Protected branches

The default "protected" branches we will be handling are `master` (or `main`) and `develop`, which we consider as the **production branch** and the **development branch**, respectively. In these "protected" branches, stable and tested code will be maintained. Although by default, we only consider these two branches as protected, depending on the project or application, there may be more "protected" branches.


### Development branches & Collaborative Work

It is advised not to work directly on a protected branch. Ideally, the work should be done within a branch that originates from the protected branch. Make the changes there, and once they are tested and ready, they can be merged into the protected branch.

Unless otherwise specified in a project, merges from feature branches to protected branches will be done through [Merge Requests in GitLab](https://docs.gitlab.com/ee/user/project/merge_requests/getting_started.html) or [Pull Requests in Github](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests). These requests will then be reviewed and approved.

Development branches should have meaningful, descriptive, and short names. If you are working on a feature described in a Jira task, the branch must be named after the task code:

```sh
$ git checkout -b JRA-123-<branch-name>
```

These development branches are usually discarded after being merged, and ideally, **they should be deleted both locally and in the centralized repository** to maintain a clean working environment. 

Some tips when for working with *development branches* Avoid reusing names of old branches or keeping the repository cluttered with development branches to prevent naming conflicts.

???+ tip "Some tips when for working with *development branches*:"

    1. Avoid reusing names of old branches or keeping the repository cluttered with development branches to prevent naming conflicts.
    2. Avoid using the same branch name for different contents and thus prevent conflicts
    3. Always do a `pull` **before starting work** to have the latest changes available (in case someone else made changes) and avoid conflicts.
    4. Take into account what the rest of the team is working on to avoid working on the same files/code lines if possible, to avoid unnecessary conflicts.


## About PR (Pull Requests)

For every [Pull Request (PR)](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests) or Merge Request (MR), there are minimum expectations (see below). While some repositories have a predefined [PR's template](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/creating-a-pull-request-template-for-your-repository) and checklists, others may not have these due to different customer preferences, and we need to maintain flexibility in such cases.

The minimum requirements are as follows:

1. Include the ticket number in the header of the PR, enclosed in brackets. For example: *[JRA-123] Update Website Content*.
2. Ensure the title is meaningful; provide a concise description.
3. Set a description for the PR. If for some reason there is not much to say, a brief description is fine.

# Gitflow

<TODO>

## Import notes

### Credentials and Sensitive Information

???+ warning
   
    **Never version credentials or sensitive information**. For example: database access credentials, service access credentials, and user information. Style files include: `.env` and `secrets.json`.

Sensitive information must not be versioned; we achieve this by adding them to `.gitignore` and sharing them via email or another method outside of Git. However, it is important to have a version of the configuration files (e.g., `.env.example` or `secrets.example.json`) as examples to understand the required format. These files have the same format as the original files but are either empty or contain placeholders.


## Resources

- [Git Cheat Sheet](https://training.github.com/downloads/github-git-cheat-sheet.pdf)
- [Very good guide to larn Git](https://learngitbranching.js.org/)
- [Learn Git by playing a game](https://ohmygit.org/)
