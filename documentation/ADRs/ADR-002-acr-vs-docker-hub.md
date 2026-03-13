# ADR-002: Azure Container Registry vs Docker Hub

**Date:** 2026-03-13
**Status:** Accepted

## Context
CI pipeline needs a registry to push Docker images to.

## Decision
Use Azure Container Registry (ACR).

## Reasons
- AKS attaches to ACR via managed identity — no credentials needed
- Private by default — images not publicly exposed
- Built-in vulnerability scanning via Defender for Containers
- Stays within Azure trust boundary — no external dependency
- Supports geo-replication for DR

## Tradeoffs
- Cost vs Docker Hub free tier
- Azure-only — not portable to other clouds

## When Docker Hub is correct
Open source projects, public images, non-Azure infrastructure.
