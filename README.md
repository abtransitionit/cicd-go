# cicd-templates

This repository contains a collection of reusable GitHub Actions workflow templates designed to standardize and simplify CI/CD pipelines across multiple repositories.
By centralizing common build, test, and deployment steps, these workflows help ensure consistency, reduce duplication, and streamline maintenance for all projects that use them.


[![Dev CI](https://github.com/abtransitionit/cicd-templates/actions/workflows/ci-dev.yaml/badge.svg?branch=dev)](https://github.com/abtransitionit/cicd-templates/actions/workflows/ci-dev.yaml)
[![Main CI](https://github.com/abtransitionit/cicd-templates/actions/workflows/ci-main.yaml/badge.svg?branch=main)](https://github.com/abtransitionit/cicd-templates/actions/workflows/ci-main.yaml)
[![LICENSE](https://img.shields.io/badge/license-Apache_2.0-blue.svg)](https://choosealicense.com/licenses/apache-2.0/)

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
name: CI for dev branch

on:
  push:
    branches:
      - dev

jobs:
  install-go:
     uses: abtransitionit/cicd-templates/.github/workflows/install-go-toolchain.yaml@main
     with:
        go-version: '1.24'

  checkout-code:
    needs: install-go
    uses: abtransitionit/cicd-templates/.github/workflows/ci_code-checkout.yaml@main

  check-code:
    needs: checkout-code
    uses: abtransitionit/cicd-templates/.github/workflows/ci_code-check.yaml@main

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

