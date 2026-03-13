# ADR-003: Bicep vs ARM Templates

**Date:** $(date +%Y-%m-%d)
**Status:** Accepted

## Context
Azure infrastructure needs to be defined and deployed as code.

## Decision
Use Bicep as primary IaC. Terraform as secondary.

## Reasons
- Bicep is Azure-native, compiles to ARM — no state file required
- 60-70% less code than equivalent ARM JSON
- what-if command shows planned changes before applying
- First-class VS Code support with type checking and intellisense
- Microsoft's recommended path forward from ARM

## Tradeoffs
- Azure-only — not portable to multi-cloud
- Smaller ecosystem than Terraform

## Why Terraform as secondary
Same infrastructure mirrored in both tools demonstrates multi-tool competency.
