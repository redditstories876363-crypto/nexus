# Contributing Guidelines

We love contributions! To keep the project maintainable, please follow these steps:

## Development Process

1. **Fork the repo** and create your branch from `main`.
2. **Install Dev Dependencies**:
   ```bash
   pip install -r requirements-dev.txt
   pre-commit install
   ```
3. **Write Tests**: Ensure your feature is covered by unit and integration tests in the `/tests` directory.
4. **Linting**: We use `ruff` and `black`. Run `make lint` before committing.

## Pull Request Rules

- Provide a clear description of the change.
- Update relevant documentation in `/docs`.
- Ensure all CI/CD checks pass.
- Tag a maintainer for review.

## Code of Conduct

Be respectful and professional. We follow the Contributor Covenant Code of Conduct.