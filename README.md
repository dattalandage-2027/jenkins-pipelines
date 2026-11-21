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

## Included pipelines

- `pipelines/food-backend.Jenkinsfile` — installs with Bun, type-checks, and runs backend tests with an in-memory database.
- `pipelines/food-frontend.Jenkinsfile` — installs with Bun, type-checks, runs Vitest coverage, and builds the Vite application.

Both application repositories also contain a root `Jenkinsfile` so Jenkins Multibranch Pipeline jobs can discover them directly.
