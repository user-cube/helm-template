# helm-template
Template for repositories using helmchart.

## Pre-commit Hooks

This repository uses [pre-commit](https://pre-commit.com/) to ensure code quality and consistency for YAML, Helm, and Kubernetes manifests.

### Tool Installation

Before using pre-commit hooks, make sure you have the following tools installed:
```bash
# Install pre-commit
pip install pre-commit
# or
brew install pre-commit

# Install Helm (if not already installed)
brew install helm 
# or follow instructions at https://helm.sh/docs/intro/install/

# Install prettier (for YAML formatting, if you want to run it manually)
npm install -g prettier

# Install yamllint (for YAML linting, if you want to run it manually)
pip install yamllint

# Install kubeconform (for Kubernetes manifest validation)
brew install kubeconform
# or download from https://github.com/yannh/kubeconform#installation

# Install chart-testing
brew install chart-testing
# or download from https://github.com/helm/chart-testing
```

## Setup pre-commit 

1. Install pre-commit (if you don't have it):
   ```bash
   pip install pre-commit
   # or
   brew install pre-commit
   ```
2. Install the hooks:
   ```bash
   pre-commit install
   ```
   This will automatically run the configured hooks on staged files during `git commit`.

## Tests

### Setup

Install test framework tool:

```bash
helm plugin install https://github.com/helm-unittest/helm-unittest
```

### Execute tests

Execute the following command:

```bash
helm unittest src -f '../tests/**/*.yaml' -f '../tests/**/*.yml'
```

## Docs

## Setup

```bash
brew install helm-docs
```

## Generate docs

```bash
helm-docs src
```
