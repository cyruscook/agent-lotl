---
name: terraform-provider-analysis
description: Analyse installed Terraform providers to discover available resources and datasources and retrieve their attributes and outputs.
---

# Terraform provider analysis

Use this when you're writing Terraform to ensure you are using the latest available resources and datasources, with the correct arguments, instead of guessing from your memory.

## Inspect the provider schema

In an initialised Terraform deployment:

```sh
terraform providers schema -json | jq ...
```

Don't dump the entire schema into your context. Use `jq` to perform applicable queries. For example, to find all Terraform list resources, you could run:

```sh
terraform providers schema -json | jq '.provider_schemas | to_entries | map({key: (.key | split("/")[-1]), value: (.value.list_resource_schemas // {} | keys)})'
```

Use the schema as the local API contract. Check:
- provider configuration attributes
- resources and data sources
- required, optional, and computed fields
- attribute types, nested blocks, and nesting modes
