# Microsoft Foundry hosted-agent lab

Build, deploy, and operate Microsoft Foundry hosted agents through an
instructor-led course and runnable examples.

The existing `rg-foundrydemo` deployment is being retired. The
[root deployment workflow](.github/workflows/deploy-hosted-agent.yml) skips that
resource group before Azure authentication; the course, reusable
[IaC](infra/main.bicep), examples, and documentation publishing remain available.
These source changes do not delete existing resources or retire private azd
environments. A new deployment requires a separately authorized environment.

## Start learning

Use the [GitHub Pages course](https://ericchansen.github.io/foundry-hosted-agents/course/)
for the complete learning path, Modules 0 through 12, failure lab, answer key,
and durable reference material.

The repository contains the lab bench used by the course:

| Path | Purpose |
| --- | --- |
| `docs/` | Canonical course and reference content published to GitHub Pages |
| `src/agent/` | Responses-protocol agent implementation and container image |
| `examples/` | Incremental and interface-specific deployment examples |
| `infra/` | Durable Foundry, ACR, monitoring, connection, and RBAC resources |
| `scripts/` | Prerequisite, image-test, and failure-lab automation |
| `tests/` | Structural and infrastructure validation |

## Work with the repository

Check the local toolchain:

```powershell
.\scripts\check-prerequisites.ps1
```

Build and invoke the image in deterministic local echo mode:

```powershell
.\scripts\test-image.ps1
```

For architecture, requirements, deployment paths, commands, and troubleshooting,
use the [implementation reference](https://ericchansen.github.io/foundry-hosted-agents/implementation-reference/). To configure safe GitHub Actions OIDC releases,
including existing-environment identity bootstrap and direct Responses evidence,
use the [hosted-agent CI/CD guide](https://ericchansen.github.io/foundry-hosted-agents/github-actions-hosted-agent/).
