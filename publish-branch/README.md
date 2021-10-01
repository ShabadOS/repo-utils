# Publish Branch Action

Releases the current working directory as a branch on GitHub, using the latest git tag.

Using SemVer, examples of release branches:

- `release/next` - prereleases
- `release/v2.0.0-next.2` - exactly 2.0.0-next.2
- `release/latest` - latest stable
- `release/v1` - all 1.x.x
- `release/v1.1` - all 1.1.x
- `release/v1.1.1` - exactly 1.1.1

If the latest git tag is `v1.5.3`, the following are created/updated:

- `releases/latest`
- `releases/v1`
- `releases/v1.5`
- `releases/v1.5.3`

If the latest git tag is `v1.6.0-next.4` indicating a prerelease, the following are created/updated:

- `releases/next`
- `releases/v1.6.0-next.4`

It can also release to a fixed name branch, by setting the `fixed_branch` input.

## Inputs

### `fixed_branch`

If set, publish to a fixed branch. Useful for `gh-pages` or other systems which look for a specific branch.

### `release_version`

**Required** The version to create release branches for.

### `release_branch_prefix`

**Required** The prefix of any release branches. Default `release`.

### `gitignore`

The contents to append to the existing `.gitignore`. This is useful to exclude patterns that are normally included in the `.gitignore` file, with the `!` negation operator.
