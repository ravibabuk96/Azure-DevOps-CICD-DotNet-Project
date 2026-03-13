# ADR-004: Namespace-Per-Environment vs Cluster-Per-Environment

**Date:** 2026-03-13
**Status:** Accepted

## Context
Three environments needed: dev, staging, prod. Decision: one cluster
with namespaces, or a separate cluster per environment.

## Decision
Use namespace-per-environment within a single AKS cluster.

## Reasons
- Cost: one cluster vs three — significant saving for a lab project
- Sufficient isolation via RBAC, NetworkPolicies, ResourceQuotas
- Simpler management: one kubeconfig, one monitoring workspace
- Mirrors common practice at SMEs and startups

## Tradeoffs
- Noisy neighbour risk (mitigated with ResourceQuotas)
- Cluster failure affects all environments
- Not suitable for strict compliance requirements

## When cluster-per-environment is correct
Regulated industries (PCI-DSS, HIPAA), strict blast radius requirements,
or different geographic regions per environment.
