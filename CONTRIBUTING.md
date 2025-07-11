# Contributing to Lab Management System

We love your input! We want to make contributing to this project as easy and transparent as possible, whether it's:

- Reporting a bug
- Discussing the current state of the code
- Submitting a fix
- Proposing new features
- Becoming a maintainer

## Development Process

We use GitHub to host code, to track issues and feature requests, as well as accept pull requests.

### Pull Requests

1. Fork the repo and create your branch from `main`
2. If you've added code that should be tested, add tests
3. If you've changed APIs, update the documentation
4. Ensure the test suite passes
5. Make sure your code lints
6. Issue that pull request!

### Development Setup

1. **Clone your fork**
   ```bash
   git clone https://github.com/yourusername/lab-management-system.git
   cd lab-management-system
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment**
   ```bash
   cp .env.example .env
   # Fill in your environment variables
   ```

4. **Start development server**
   ```bash
   npm run dev
   ```

### Code Style

- Use TypeScript for all new code
- Follow the existing code style and patterns
- Use meaningful variable and function names
- Comment complex logic
- Keep functions small and focused

### Commit Messages

We follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:

- `feat:` for new features
- `fix:` for bug fixes
- `docs:` for documentation changes
- `style:` for formatting changes
- `refactor:` for code refactoring
- `test:` for test changes
- `chore:` for maintenance tasks

Examples:
```
feat: add bulk delete functionality for lab logs
fix: resolve issue with authentication redirect
docs: update installation instructions
```

### Branch Naming

- Feature branches: `feature/description`
- Bug fixes: `fix/description`
- Documentation: `docs/description`
- Refactoring: `refactor/description`

## Testing

### Running Tests

```bash
# Run all tests
npm test

# Run tests in watch mode
npm run test:watch

# Run tests with coverage
npm run test:coverage
```

### Writing Tests

- Write unit tests for utility functions
- Write integration tests for API endpoints
- Write component tests for React components
- Use descriptive test names
- Group related tests with `describe` blocks

## Code Review Process

1. **Automated Checks**: All PRs must pass CI/CD checks
2. **Code Review**: At least one maintainer must review
3. **Testing**: Manual testing of new features
4. **Documentation**: Update docs if needed

### Review Checklist

- [ ] Code follows project style guidelines
- [ ] Tests are included and passing
- [ ] Documentation is updated
- [ ] Breaking changes are noted
- [ ] Security considerations are addressed

## Issue Reporting

### Bug Reports

Use the bug report template and include:

- **Environment**: OS, browser, Node.js version
- **Steps to reproduce**: Clear, numbered steps
- **Expected behavior**: What should happen
- **Actual behavior**: What actually happens
- **Screenshots**: If applicable
- **Error messages**: Full error output

### Feature Requests

Use the feature request template and include:

- **Problem**: What problem does this solve?
- **Solution**: Describe your proposed solution
- **Alternatives**: Alternative solutions considered
- **Additional context**: Screenshots, mockups, etc.

## Development Guidelines

### Frontend Development

- Use React functional components with hooks
- Implement proper error boundaries
- Follow accessibility best practices
- Use TypeScript for type safety
- Implement responsive design
- Optimize for performance

### Backend Development

- Use Express.js with TypeScript
- Implement proper error handling
- Use Drizzle ORM for database operations
- Validate all inputs
- Follow RESTful API conventions
- Document API endpoints

### Database Changes

- Use Drizzle migrations for schema changes
- Test migrations thoroughly
- Consider backward compatibility
- Document breaking changes

### Security

- Validate all user inputs
- Use parameterized queries
- Implement proper authentication
- Follow OWASP guidelines
- Regular security audits

## Documentation

### Code Documentation

- Document all public APIs
- Use JSDoc for function documentation
- Include examples in documentation
- Keep documentation up to date

### README Updates

- Update installation instructions
- Add new features to feature list
- Update screenshots if UI changes
- Keep dependencies list current

## Community

### Code of Conduct

- Be respectful and inclusive
- Help others learn and grow
- Focus on constructive feedback
- Celebrate contributions

### Getting Help

- Check existing issues first
- Use GitHub Discussions for questions
- Provide context and examples
- Be patient and helpful

## Recognition

Contributors are recognized in:

- GitHub contributors list
- Release notes
- Documentation credits
- Social media mentions

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

## Questions?

Don't hesitate to reach out:

- Create an issue for bugs or features
- Use GitHub Discussions for questions
- Contact maintainers directly for sensitive issues

Thank you for contributing! 🎉