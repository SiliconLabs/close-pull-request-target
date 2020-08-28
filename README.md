# :no_entry_sign: Close Pull Request Target

A GitHub action to automatically close a pull request, even if the pull request is from a forked repository

This is a fork of [superbrothers/close-pull-request](https://github.com/superbrothers/close-pull-request) intended for use within other Silicon Labs repositories. For users wishing to use Github actions to close pull requests, it is recommended to use [superbrothers/close-pull-request](https://github.com/superbrothers/close-pull-request)

## Usage

This Action subscribes to `pull_request_target` events. When receiving a `pull_request_target` event, this action closes the pull request triggered by the event immediately.

```yaml
name: Close Pull Request

on:
  pull_request_target:
    types: [opened]

jobs:
  run:
    runs-on: ubuntu-latest
    steps:
    - uses: superbrothers/close-pull-request@v2
      with:
        # Optional. Post a issue comment just before closing a pull request.
        comment: "We do not accept PRs. If you have any questions, please feel free to contact us."
      env:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

## Inputs

- `comment` - *Optional*. Post an issue comment just before closing a pull request.

## LICENSE

This software is released under the MIT License.
