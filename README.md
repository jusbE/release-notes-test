# release-notes-test

## Installation
```
npm i -g standard-version
```


## Configuration

By default standard-version reads configuration from .versionrc.json which follows schema defined here: https://github.com/conventional-changelog/conventional-changelog-config-spec, pick the current version.

More detailed information about the tool can be found here:
https://github.com/conventional-changelog/standard-version


## Commit messages

Messages should follow next syntax:
\<type>:\<jira-id>/\<description>

example:
feat: KIGCMD-123/new-ds-api

If type is not matching to configured types then message will be just ignored from release notes


## Versioning

Supported release types:
- major - breaking changes, not backward compatible (1.0.0 -> 2.0.0)
- minor - new features (1.0.0 -> 1.1.0)
- patch - fix existing feature (1.0.0 -> 1.0.1)


## Workflow
1. Create new branch from master
2. Commit changes to new branch
3. Create PR
4. a) Squash & merge PR -> only single line will be showing release notes
   b) Merge PR -> all the commits from new branch are shown in release notes
5. run from terminal: ```standard-version --release-as major|minor|patch```
   This will create new commit with modified CHANGELOG.md file and adds new tag with new version. Also updates package.json version number
6. Push commit and new tag if all looks good
