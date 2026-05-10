---
name: terraform-module-analysis
description: Analyse external Terraform module dependencies to discover variables and outputs and examine any internal behaviour.
---

# Terraform module analysis

Use this when you're writing Terraform with dependencies on external modules to ensure you are using the latest available variables and outputs, instead of guessing from your memory. Where you're unsure of how the module operates internally, you can figure this out from the source code.

## Inspect the module source code

Terraform modules are commonly unpacked under `.terraform/modules/...`. Read those files directly to understand:
- how the module configures the provider
- which resources and data sources it uses
- how inputs map to provider arguments
- which outputs expose provider-returned fields
