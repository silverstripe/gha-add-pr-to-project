# GitHub Actions - Add PR to project

Add community-created pull requests to the [Community Contributions project](https://github.com/orgs/silverstripe/projects/4) when they're opened.

## Usage

**.github/workflows/add-pr-to-project.yml**
```yml
name: Add new pull requests to a github project

on:
  pull_request:
    types:
      - opened
      - ready_for_review

permissions: {}

jobs:
  addprtoproject:
    # Only run on the silverstripe account
    if: github.repository_owner == 'silverstripe'
    runs-on: ubuntu-latest
    steps:
      - name: Add PR to github project
        uses: silverstripe/add-pr-to-project@v1
```

This action has no inputs.
