# mudman-template

A comprehensive GitHub repository template with automated CI/CD workflows, security scanning, and best practices for modern software development.

## 🎯 About This Template

This template repository provides a complete foundation for new projects with:
- **Automated dependency updates** via Dependabot
- **Security scanning** with CodeQL
- **Code quality checks** with Super-Linter
- **Dependency review** for pull requests
- **Ready-to-use issue and PR templates**
- **Community health files** (CODE_OF_CONDUCT, SECURITY, CONTRIBUTING)

## 🚀 Getting Started

### Using This Template

1. Click the "**Use this template**" button at the top of this repository
2. Choose a name for your new repository
3. Select whether it should be public or private
4. Click "**Create repository from template**"

### After Creating Your Repository

Once you've created a new repository from this template, follow these steps to customize it:

#### 1. Update Repository Settings

- [ ] Go to **Settings → General**
  - Update the repository description
  - Add relevant topics/tags
  - Configure default branch name if needed

- [ ] Go to **Settings → Code security and analysis**
  - Enable **Dependabot alerts**
  - Enable **Dependabot security updates**
  - Enable **Secret scanning**
  - Enable **Push protection** (recommended)

- [ ] Go to **Settings → Branches**
  - Add branch protection rules for `main` branch:
    - Require pull request reviews
    - Require status checks to pass
    - Require conversation resolution
    - Enable "Do not allow bypassing the above settings"

#### 2. Customize Configuration Files

Update the following files with your project-specific information:

- [ ] **README.md**: Replace this content with your project documentation
- [ ] **LICENSE**: Choose an appropriate license for your project
- [ ] **CONTRIBUTING.md**: Update contribution guidelines
- [ ] **CODE_OF_CONDUCT.md**: Review and customize if needed
- [ ] **SECURITY.md**: Update security policy with your contact information
- [ ] **.github/dependabot.yml**: Adjust package ecosystems based on your tech stack
- [ ] **.github/workflows/*.yml**: Review and customize workflows as needed

#### 3. Update Workflow Configurations

The template includes several GitHub Actions workflows located in `.github/workflows/`:

- **super-linter.yml**: Code quality and linting
  - Customize `languages` and linting rules in the workflow
  - Add/remove linters based on your tech stack

- **codeql-analysis.yml**: Security analysis
  - Update the `languages` array to match your project
  - Add custom CodeQL queries if needed

- **dependency-review.yml**: Dependency security review
  - Adjust `fail-on-severity` level as needed
  - Configure allowed/denied licenses

#### 4. Add Project-Specific Content

- [ ] Add your application code
- [ ] Add tests and test configuration
- [ ] Add build configuration (package.json, requirements.txt, etc.)
- [ ] Update issue templates for your use case
- [ ] Add any additional GitHub Actions workflows
- [ ] Configure repository secrets (Settings → Secrets and variables → Actions)

#### 5. Clean Up Template Artifacts

- [ ] Remove this "Getting Started" section from README.md
- [ ] Delete any template files you don't need
- [ ] Update all TODOs and placeholder text

## 📋 Included Workflows

This template leverages reusable workflows from [mudman-reusable](https://github.com/mudman1986/mudman-reusable):

### Super-Linter
Automated code quality and style checking for multiple languages.
- **Trigger**: Push and pull requests to main/develop branches
- **Configuration**: `.github/workflows/super-linter.yml`

### CodeQL Analysis
Advanced security analysis to identify vulnerabilities.
- **Trigger**: Push, pull requests, and weekly schedule (Mondays)
- **Configuration**: `.github/workflows/codeql-analysis.yml`

### Dependency Review
Reviews dependency changes in pull requests for security issues.
- **Trigger**: Pull requests only
- **Configuration**: `.github/workflows/dependency-review.yml`

### Dependabot
Automatically creates pull requests to update dependencies.
- **Schedule**: Weekly updates
- **Configuration**: `.github/dependabot.yml`
- **Supports**: npm, pip, GitHub Actions, Docker

## 🛠️ Customization Options

### Adding More Workflows

You can add additional workflows from the [mudman-reusable](https://github.com/mudman1986/mudman-reusable) repository:

- **Test Suite**: Automated testing workflow
- **Docker Build**: Build and push Docker images
- **Release Automation**: Automated releases with changelogs

Example:
```yaml
jobs:
  test:
    uses: mudman1986/mudman-reusable/.github/workflows/reusable-test-suite.yml@main
    with:
      node-version: '20'
      test-command: npm test
```

### Customizing Dependabot

Edit `.github/dependabot.yml` to:
- Change update frequency (daily, weekly, monthly)
- Add/remove package ecosystems
- Configure reviewers and labels
- Set version update strategies

### Configuring Branch Protection

Recommended branch protection rules:
1. Require pull request reviews (at least 1 approval)
2. Require status checks:
   - Super-Linter
   - CodeQL Analysis
   - Any project-specific tests
3. Require conversation resolution
4. Restrict who can push to matching branches

## 📚 Documentation Structure

This template includes the following documentation files:

- **README.md**: Project overview and getting started (this file)
- **CONTRIBUTING.md**: Guidelines for contributing
- **CODE_OF_CONDUCT.md**: Community code of conduct
- **SECURITY.md**: Security policy and vulnerability reporting
- **LICENSE**: Project license

## 🔒 Security Features

- **Dependabot**: Automated dependency updates
- **CodeQL**: Continuous security scanning
- **Dependency Review**: PR-based dependency analysis
- **Secret Scanning**: Prevents accidental secret commits (if enabled)
- **Security Policy**: Clear vulnerability reporting process

## 🤝 Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for details on how to contribute to this project.

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📧 Support

For questions or issues:
1. Check existing [Issues](../../issues)
2. Create a new issue if needed
3. Refer to the [Security Policy](SECURITY.md) for security concerns

## 🔗 Related Resources

- [mudman-reusable workflows](https://github.com/mudman1986/mudman-reusable) - Reusable GitHub Actions
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Dependabot Documentation](https://docs.github.com/en/code-security/dependabot)
- [CodeQL Documentation](https://codeql.github.com/docs/)

---

**Note**: This is a template repository. After creating a new repository from this template, customize it according to your project's needs by following the "Getting Started" section above.