# Claude Code Project Guidelines

This document outlines coding standards, best practices, and guidelines for the Claude Code project. All contributions should adhere to these principles.

## Core Principles

### 1. User-Centric Design
- Prioritize user experience and clarity in all changes
- Keep the terminal interface clean and intuitive
- Provide clear, helpful error messages
- Document all commands and options thoroughly

### 2. Code Quality
- Write clear, readable code that requires minimal comments
- Use descriptive variable and function names
- Avoid over-engineering; keep solutions simple and focused
- Remove unused code and dependencies
- Use TypeScript for type safety and better IDE support

### 3. Testing
- Include tests for new functionality
- Ensure tests are meaningful and test actual behavior
- Run the full test suite before committing
- Document test coverage for critical paths

### 4. Security
- Never commit sensitive information (.env, credentials, keys)
- Validate all user input at system boundaries
- Be mindful of command injection vulnerabilities
- Review code for OWASP top 10 vulnerabilities
- Keep dependencies up to date and audit for vulnerabilities

### 5. Documentation
- Document public APIs and commands
- Provide clear README files for plugins and features
- Update CHANGELOG when adding features or fixes
- Include usage examples in documentation
- Keep documentation in sync with implementation

## Git Practices

### Commit Messages
- Use clear, descriptive commit messages that explain the "why"
- Start with a prefix: `fix:`, `feat:`, `docs:`, `test:`, `chore:`, `refactor:`
- Keep messages concise (first line under 72 characters)
- Reference issue/PR numbers when applicable
- Example: `fix(security): Remove overly broad gh api permission from dedupe command (#16549)`

### Branching
- Create feature branches from `main`
- Use descriptive branch names (e.g., `feature/add-plugin-search`, `fix/auth-token-issue`)
- Keep branches focused on single features or fixes
- Delete branches after merging

### Pull Requests
- Keep PRs focused and reasonably sized
- Include description of changes and motivation
- Link related issues
- Ensure CI/CD checks pass before merging
- Request review from relevant maintainers

## Code Standards

### TypeScript/JavaScript
- Use TypeScript for new code
- Enable strict TypeScript checking
- Use const/let appropriately, prefer const
- Avoid any types; use proper typing
- Use async/await over callbacks when appropriate
- Keep functions small and focused

### Error Handling
- Handle errors explicitly
- Provide useful error messages to users
- Log errors appropriately for debugging
- Don't swallow errors silently

### Naming Conventions
- Use camelCase for variables and functions
- Use PascalCase for classes and types
- Use UPPER_SNAKE_CASE for constants
- Use descriptive names that reflect purpose
- Avoid single-letter variables except in loops

## Plugin Development

### Plugin Structure
- Follow the standard plugin directory structure
- Include comprehensive README.md
- Document all commands, agents, and skills
- Provide usage examples
- Keep plugin focused on specific functionality

### Plugin Guidelines
- Commands should be single, focused operations
- Agents should handle complex, multi-step tasks
- Skills should encapsulate reusable knowledge
- Hooks should be minimal and focused
- Document dependencies and requirements

## Common Patterns

### CLI Output
- Use clear, human-readable output
- Provide progress indication for long operations
- Include helpful next steps or suggestions
- Show error messages in context

### Git Integration
- Use `gh` CLI for GitHub operations
- Handle network failures gracefully
- Provide meaningful error messages for git operations
- Use atomic operations (all-or-nothing commits)

### Hook Configuration
- Document hook requirements clearly
- Validate hook configuration
- Provide helpful error messages
- Make hooks optional where possible

## Review Checklist

When submitting code for review, ensure:
- [ ] Code follows TypeScript best practices
- [ ] No security vulnerabilities introduced
- [ ] No sensitive information committed
- [ ] Tests added/updated and passing
- [ ] Documentation updated
- [ ] Commit messages are clear
- [ ] No console.log() statements for production code
- [ ] Error handling is explicit
- [ ] Code is properly formatted
- [ ] Dependencies are necessary and up to date

## Performance Considerations

- Avoid unnecessary API calls
- Cache computed values when appropriate
- Use streaming for large file operations
- Monitor and minimize memory usage
- Profile code for performance-critical paths

## Accessibility

- Ensure CLI output is readable in all terminal types
- Provide text-based alternatives when using symbols
- Support both colored and non-colored output
- Make commands keyboard-accessible

## Backwards Compatibility

- Consider backwards compatibility for public APIs
- Document breaking changes clearly
- Provide migration guides when needed
- Use feature flags for gradual rollouts

## Resources

- [Claude Code Documentation](https://code.claude.com/docs/en/overview)
- [Official Plugins Documentation](https://docs.claude.com/en/docs/claude-code/plugins)
- [Agent SDK Documentation](https://docs.claude.com/en/api/agent-sdk/overview)
- Project README for setup and architecture information
