# ADR-001: AKS vs App Service for Container Hosting

**Date:** 2026-03-13
**Status:** Accepted

## Context
We need to host eShopOnWeb as containers. Two primary options considered:
AKS (managed Kubernetes) or Azure App Service (PaaS).

## Decision
Use AKS.

## Reasons
- Full Kubernetes control: namespaces, RBAC, network policies, HPA
- Enables GitOps with ArgoCD — not possible with App Service
- Multi-environment isolation via namespaces (dev/staging/prod)

## Tradeoffs
- Higher operational complexity than App Service
- Higher cost due to node VMs
- More configuration required (ingress, RBAC, namespaces)

## When App Service is correct
Simple stateless apps, small teams, no Kubernetes expertise needed.
