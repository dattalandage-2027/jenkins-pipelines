# Jenkins Pipelines

Reusable CI/CD pipeline definitions for the food platform repositories.

## Planned scope

- Build, test, lint, and security checks
- Container image build and publication
- Terraform validation and planning
- GitOps image and deployment updates

## Repository conventions

- Shared pipeline logic belongs in reusable libraries.
- Application repositories retain small entry-point Jenkinsfiles.
- Production deployments require reviewed, traceable changes.
- Credentials are managed by Jenkins and must never be committed.

Pipeline and rollback procedures are documented in `devops-engineering-docs`.
