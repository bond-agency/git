# git
Bond git-workflow related stuff

## Commits

### Commit template setup

1. Save the [commit template file](https://github.com/bond-agency/git/blob/master/git-commit-template) to your computer
2. Add this to your `~/.gitconfig` file:

```
[commit]
  template = ~/git-commit-template # change according to the template location
```
3. Profit

### Commit example

A good commit looks someting like this:
```
[ref #123] Fixed the carousel

- Added relative position to the carousel container as the current
absolute position breaks the layout
- Fixed the typo in classname

This closes #123
```

## Branching

When developing a project, we are using branching model where the `master` branch is the current production version. Development happens in `development` branch, but no commits should get pushed to there straight away. Instead you should create a new feature branch out of the `development` after you have pulled all of the changes.

The naming convention for the feature branches should be as follows:

`feature/123`
`change/123`
`issue/123`
`bugfix/123`

Where the number `123` poinst to the GitHub issue number. Do not use the hash before the number as it's hard to switch to that branch afterwards. Also remember to keep the feature branch clean and focused only to the current issue in hand.

## Pull requests

When creating a pull request from the feature branch to the `development` branch, remember to write a good descriptions about what you have done.

### Merge `development` <-- `feature`

When merging your feature branch into the development, use GitHubs **Squash and merge** instead of the default *Merge pull request* option. What the squash merge does is it squashes the feature into one single commit and the commit tree in the `development` branch keeps as clean as possible.

After merging the PR you should always delete the feature branch and if the feature still needs development, open a new issue and create a new branch instead of using the old one.

### Merge `master` <-- `development`

When merging the `development` branch into the `master` you should use the **Merge pull request** when merging. This is because both branches are protected and non-disposable and this way the history of both branches is kept linked.
