# create-release-action
[![GitHub Workflow Status (CI)](https://img.shields.io/github/actions/workflow/status/lizardbyte/create-release-action/ci.yml.svg?branch=master&label=CI%20build&logo=github&style=for-the-badge)](https://github.com/LizardByte/create-release-action/actions/workflows/ci.yml?query=branch%3Amaster)

A reusable action to create a GitHub release. This action is tailored to the
@LizardByte organization, but can be used by anyone if they follow the same conventions.

This is basically a wrapper around [ncipollo/release-action](https://github.com/ncipollo/release-action), with some
different defaults to make it easier to use within the @LizardByte organization.

## Basic Usage

See [action.yml](action.yml)

```yaml
steps:
  - name: Create Release
    uses: LizardByte/create-release-action@master
    with:
      name: v0.1.0
      tag: v0.1.0
      token: ${{ secrets.GITHUB_TOKEN }}
```

## Inputs

| Name                 | Description                                                                                       | Default         | Required |
|----------------------|---------------------------------------------------------------------------------------------------|-----------------|----------|
| allowUpdates         | An optional flag which indicates if we should update a release if it already exists.              | `true`          | `false`  |
| artifacts            | The artifacts to upload.                                                                          | `*artifacts/*`  | `false`  |
| body                 | The body of the release.                                                                          |                 | `false`  |
| changelog            | Whether to create a changelog file. The changelog will be generated from the GitHub releases API. | `true`          | `false`  |
| changelogBranch      | The branch to store the changelog in.                                                             | `changelog`     | `false`  |
| changelogFile        | The file to store the changelog in.                                                               | `CHANGELOG.md`  | `false`  |
| discussionCategory   | The category for the discussion.                                                                  | `announcements` | `false`  |
| generateReleaseNotes | Indicates if release notes should be automatically generated.                                     | `false`         | `false`  |
| name                 | The version to create.                                                                            |                 | `true`   |
| prerelease           | Whether the release is a prerelease.                                                              | `false`         | `false`  |
| tag                  | The tag to create.                                                                                |                 | `true`   |
| token                | GitHub Token.                                                                                     |                 | `true`   |

## Outputs

| Name      | Description                              |
|-----------|------------------------------------------|
| changelog | The contents of the generated changelog. |

## See Also

This action is meant to be used in conjunction with
[LizardByte/setup-release-action](https://github.com/LizardByte/setup-release-action).
