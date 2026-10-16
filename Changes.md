# Change history for significant pattern releases

## Variants and single Argo CD (TBD)

- Adopt `global.singleArgoCD: true` and the `variants/` directory layout
  (`main.variant` + `global.vpNewFolderDir`).
- Default variant is `minimal-aap` (AAP 2.7, no automation hub), matching the
  previous single-cluster hub layout.
- Add `aap-with-hub` (ODF + automation hub), `aap-with-ao` (CNPG + Automation
  Orchestrator), and `complete-aap-ao` (hub, Lightspeed, and AO). Named
  `complete-aap-ao` rather than `complete-aap-with-ao` so the GitOps server DNS
  label stays within 63 characters.
- AO variants use the `automation-orchestrator-instance` chart (kept at chart
  version 0.1.0 for now), including ExternalSecret projection and an OpenShift
  ConsoleLink.
- Generate AO Postgres passwords with alphanumeric `postgresPasswordPolicy` so
  URL-encoded special characters do not break Alembic/configparser during AO
  startup.

## Initial Release (TBD)
