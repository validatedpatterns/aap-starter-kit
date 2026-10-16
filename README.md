# Ansible Automation Platform Starter Kit

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![AWS](https://img.shields.io/endpoint?url=https%3A%2F%2Fstorage.googleapis.com%2Fhcp-results%2Faegitops-aws-ci.json)](https://storage.googleapis.com/hcp-results/aegitops-aws-ci.json)

## Start Here

This is a Validated Pattern for installing and using Ansible Automation Platform
on OpenShift. It uses a Config as Code (CaC)/GitOps approach to loading AAP
configuration.

The concepts in this pattern were developed for and derived from the Ansible
Edge GitOps Validated Pattern. If you've followed a link to this repository but
are not sure what it contains or how to use it, head over to
[Ansible Edge GitOps](https://validatedpatterns.io/patterns/ansible-edge-gitops/)
for additional context and installation instructions.

## Variants

Set `main.variant` in `values-global.yaml` before `./pattern.sh make install`.
Variant values live under `variants/<name>/values-<name>.yaml`.

| Variant | Description |
| --- | --- |
| `minimal-aap` (default) | AAP 2.7 with controller and minimal CaC. Automation hub and Lightspeed disabled. |
| `aap-with-hub` | `minimal-aap` plus OpenShift Data Foundations and automation hub. |
| `aap-with-ao` | `minimal-aap` plus CloudNativePG (`vp-cloudnative-pg-cluster`) and Automation Orchestrator. |
| `complete-aap-ao` | Automation hub, Lightspeed, and Automation Orchestrator (includes ODF and CNPG). |

Automation hub variants need RWX storage from the Validated Patterns ODF chart.
AO variants install the CloudNativePG operator from certified-operators; Red Hat
does not support CloudNativePG for Automation Orchestrator databases—use an
externally supported PostgreSQL 15 when that matters for your environment.

Related charts:

- [ansible-automation-platform-instance](https://github.com/validatedpatterns/aap-instance-chart)
- [openshift-data-foundations](https://github.com/validatedpatterns/openshift-data-foundations-chart)
- [vp-cloudnative-pg-cluster](https://github.com/validatedpatterns/vp-cloudnative-pg-cluster-chart)
- [automation-orchestrator-instance](https://github.com/validatedpatterns/automation-orchestrator-instance-chart)
