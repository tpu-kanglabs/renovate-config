# renovate-config

[![CI](https://github.com/tpu-kanglabs/renovate-config/actions/workflows/ci.yaml/badge.svg)](https://github.com/tpu-kanglabs/renovate-config/actions/workflows/ci.yaml)

This repository provides a shared Renovate configuration for our projects.

## Features

- Extends recommended Renovate settings.
- Groups multiple major releases into separate PRs.
- Includes custom configurations for GitHub Actions, Node.js, and Python dependencies.
- Ensures updates are at least 3 days old before PR creation.
- Schedules Renovate to run only on weekdays (Monday to Friday) between 8:00 and 17:00 JST.

## Configuration Files

- **default.json**: Main configuration. Sets base rules, timezone, PR labels, minimum release age, and schedule.
- **actions.json**: Groups updates for common GitHub Actions (artifact and pages related) into separate PRs.
- **node.json**: Node.js configuration. Disables major updates for `@types/node` and applies ESLint rules.
- **python.json**: Python configuration. Groups updates for tools like Ruff, Mypy, nbdev, PyTorch, and disables CUDA updates.

## Usage

To use this configuration, extend it in your project's Renovate config:

```json
{
  "extends": [
    "github>tpu-kanglabs/renovate-config"
  ]
}
```