# Simple Autorelease action

[![License](https://img.shields.io/github/license/impresscms-dev/simple-autorelease-action.svg)](LICENSE)
[![GitHub release](https://img.shields.io/github/release/impresscms-dev/simple-autorelease-action.svg)](https://github.com/impresscms-dev/simple-autorelease-action/releases)

GitHub action that can do automatic releases if at least one pull request was merged in specified period of time.

## Usage

To use this action in your project, create workflow in your project similar
to this code (Note: some parts and arguments needs to be altered):
```yaml
name: Automatic releases

on:
  workflow_dispatch:
  schedule:
    - cron: '0 4 * * 1'

jobs:
  auto-release:
    runs-on: ubuntu-latest
    steps:
      - name: Releasing if there is something new...
        uses: impresscms-dev/simple-autorelease-action@v0.1
        with:
          release_branch: main
          github_token: ${{ secrets.GITHUB_TOKEN }}
          default_bump: patch
```

## Arguments

This action supports such arguments (used in `with` keyword):

| Argument                 | Required | Default value  | Description                                                                                        |
|--------------------------|----------|----------------|----------------------------------------------------------------------------------------------------|
| github_token | No       | *github_token* | GitHub token.                                                                                      |
| release_branch  | No       | main           | Branch that will be used for releases                                                              |
| default_bump                   | No       | patch          | How to bump version? Major.Minor.Patch |

## How to contribute?

If you want to add some functionality or fix bugs, you can fork, change and create pull request. If you not sure how this works, try [interactive GitHub tutorial](https://skills.github.com).

If you found any bug or have some questions, use [issues tab](https://github.com/impresscms-dev/simple-autorelease-action/issues) and write there your questions.
