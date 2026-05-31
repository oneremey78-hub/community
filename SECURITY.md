# Security Policy
jobs:
  deploy-dev:
    uses: octocat/octo-repo/.github/workflows/deployment.yml@main
    with:
      target: dev
    secrets: inherit

  deploy-stage:
    needs: deploy-dev
    uses: octocat/octo-repo/.github/workflows/deployment.yml@main
    with:
      target: stage
    secrets: inherit

  deploy-prod:
    needs: deploy-stage
    uses: octocat/octo-repo/.github/workflows/deployment.yml@main
    with:
      target: prod
    secrets: inherit

## Supported Versions

Use this section to tell people about which versions of your project are
currently being supported with security updates.

| Version | Supported          |
| ------- | ------------------ |
| 5.1.x   | :white_check_mark: |
| 5.0.x   | :x:                |
| 4.0.x   | :white_check_mark: |
| < 4.0   | :x:                |

## Reporting a Vulnerability

Use this section to tell people how to report a vulnerability.

Tell them where to go, how often they can expect to get an update on a
reported vulnerability, what to expect if the vulnerability is accepted or
declined, etc.
