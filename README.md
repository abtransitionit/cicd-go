# cicd-go

This repository contains a collection of reusable GitHub Actions workflow templates designed to standardize and simplify CI/CD pipelines across multiple GO repositories. It centralize common build, test, and deployment steps. These workflows help ensure consistency, reduce duplication, and streamline maintenance for all projects that use them.

----


# Features  
This project template includes the following components:  


|Component|Description|
|-|-|
|Licensing|Predefined open-source license (Apache 2.0) for legal compliance.|
|Code of Conduct| Ensures a welcoming and inclusive environment for all contributors.|  
|README|Structured documentation template for clear project onboarding.|  



---

# Getting Started  

## 1. Use it in other repos 
```yaml
name: Dev branch CI

on:
  push:
    branches:
      - dev

jobs:
  install-go:
     uses: abtransitionit/cicd-go/.github/workflows/go-install.yaml@main
     with:
        go-version: '1.24'

  checkout-code:
    needs: install-go
    uses: abtransitionit/cicd-go/.github/workflows/code-checkout.yaml@main

  check-code:
    needs: checkout-code
    uses: abtransitionit/cicd-go/.github/workflows/code-check.yaml@main

```


---

# Contributing  

We welcome contributions! Before participating, please review:  
- **[Code of Conduct](.github/CODE_OF_CONDUCT.md)** – Our community guidelines.  
- **[Contributing Guide](.github/CONTRIBUTING.md)** – How to submit issues, PRs, and more.  


----


# Release History & Changelog  

Track version updates and changes:  
- **📦 Latest Release**: `vX.X.X` ([GitHub Releases](#))  
- **📄 Full Changelog**: See [CHANGELOG.md](CHANGELOG.md) for detailed version history.  

---



# Todo: CI Improvements

## 1. Dependency Caching

* **Current behavior:** The workflow downloads Go modules on every run.
* **Issue:** Re-downloading dependencies for each workflow execution is inefficient.
* **Proposed improvement:** Cache Go module dependencies to significantly speed up subsequent runs.

## 2. Job Permissions

* **Current behavior:** Jobs run using the default `GITHUB_TOKEN`.
* **Issue:** The default token grants more permissions than necessary, potentially creating security risks.
* **Proposed improvement:** Explicitly configure job permissions to limit access to only what is required, for example when creating tags.

