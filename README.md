name: 'TODO: Run <linter-name> with streamcode'
description: 'TODO: 🦅 Run <linter-name> with streamcode on pull requests to improve code review experience.'
author: 'TODO: <your-name>'
inputs:
  github_token:
    description: 'GITHUB_TOKEN'
    default: '${{ github.token }}'
  workdir:
    description: 'Working directory relative to the root directory.'
    default: '.'
  ### Flags for streamcode ###
  level:
    description: 'Report level for streamcode [info,warning,error]'
    default: 'error'
  reporter:
    description: 'Reporter of streamcode command [github-pr-check,github-pr-review].'
    default: 'github-pr-check'
  filter_mode:
    description: |
      Filtering mode for the streamcode command [added,diff_context,file,nofilter].
      Default is added.
    default: 'added'
  fail_on_error:
    description: |
      Exit code for streamcode when errors are found [true,false]
      Default is `false`.
    default: 'false'
  streamcode_flags:
    description: 'Additional streamcode flags'
    default: ''
  ### Flags for <linter-name> ###
  locale:
    description: '-locale flag of misspell. (US/UK)'
    default: ''
runs:
  using: 'docker'
  image: 'Dockerfile'

# Ref: https://khulnasoft-labs.github.io/github-action-brandings/
# TODO: update branding if you want.
branding:
  icon: 'check'
  color: 'blue'
