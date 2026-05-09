CI/CD Pipeline:

Our GitHub Actions pipeline runs on every push and PR to the develop branch. It performs the following "Fail Loudly" checks:

- Linting: Checks for PEP8 compliance using flake8.

- Dependency Audit: Ensures all requirements install correctly.

- Unit Testing: Executes the Django test suite against a live PostgreSQL service container.

Secrets & Environment Management:
- Local Environment
- Copy the template to create your local variables:

Bash
cp .env.example .env

GitHub Secrets
The following secrets must be configured in the GitHub Repository Settings for the CI to pass:

- DJANGO_SECRET_KEY

- CI_DB_PASSWORD

- DB_NAME

- DB_USER

Infrastructure Plan (AWS):
Compute: AWS ECS (Fargate) for serverless container execution.

- Database: Amazon RDS for PostgreSQL.

- Storage: Amazon S3 for media/static files.

- CDN: Amazon CloudFront for low-latency delivery.

Contributing:
Please read CONTRIBUTING.md for details on our code of conduct and the process for submitting pull requests.


DevOps Engineer: Mustapha Yusuf Isma'il