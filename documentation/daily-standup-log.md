# Daily Standup Log

---

## Day 1 — $(date +%Y-%m-%d)

**What I completed:**
- Created public GitHub repo with full folder structure
- Set up Azure DevOps project (Scrum process)
- Connected GitHub repo to Azure DevOps
- Created Epic, 4 Features, and 4 PBIs in ADO Boards
- Verified all local tools: Docker, kubectl, Helm, Azure CLI
- Created 4 Azure resource groups with tags
- Wrote 4 ADRs documenting key architecture decisions

**What I learned:**
- ADRs force you to articulate the WHY behind decisions, not just the WHAT
- Resource group separation by component (not just environment) is enterprise practice
- ADO Scrum process uses Product Backlog Item instead of User Story — same concept

**Blockers:** None

**Tomorrow (Day 2):**
- Deploy ACR via Bicep
- Fork eShopOnWeb and study app structure
- Write production-grade multi-stage Dockerfile
- Set up Docker Compose for local development
