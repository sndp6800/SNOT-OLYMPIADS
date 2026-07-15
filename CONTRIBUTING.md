# Contributing to SNOT-OLYMPIADS

Thank you for your interest in contributing to SNOT-OLYMPIADS! This document provides guidelines and instructions for contributing.

---

## 📋 Table of Contents

1. [Code of Conduct](#code-of-conduct)
2. [Getting Started](#getting-started)
3. [Development Workflow](#development-workflow)
4. [Code Style Guide](#code-style-guide)
5. [Commit Guidelines](#commit-guidelines)
6. [Pull Request Process](#pull-request-process)
7. [Testing Requirements](#testing-requirements)
8. [Documentation](#documentation)

---

## 🤝 Code of Conduct

All contributors are expected to:
- Be respectful and inclusive
- Provide constructive feedback
- Focus on the code, not the person
- Help foster a welcoming community

---

## 🚀 Getting Started

### Setup Development Environment

```bash
# Clone your fork
git clone https://github.com/YOUR_USERNAME/SNOT-OLYMPIADS.git
cd SNOT-OLYMPIADS

# Add upstream remote
git remote add upstream https://github.com/sndp6800/SNOT-OLYMPIADS.git

# Install dependencies
npm install

# Setup Git hooks
npm run prepare

# Create feature branch
git checkout -b feature/your-feature-name
```

### Prerequisites
- Node.js 18+
- PostgreSQL 14+
- Git
- Code editor (VS Code recommended)

---

## 🔄 Development Workflow

### 1. Create a Feature Branch

```bash
git checkout -b feature/feature-description
```

**Branch Naming Convention**:
- `feature/description` - New features
- `fix/description` - Bug fixes
- `docs/description` - Documentation
- `refactor/description` - Code refactoring
- `test/description` - Test improvements

### 2. Make Changes

- Write clean, well-documented code
- Follow the code style guide
- Keep commits atomic and logical
- Update tests accordingly

### 3. Keep Branch Updated

```bash
git fetch upstream
git rebase upstream/main
```

### 4. Push Changes

```bash
git push origin feature/feature-description
```

---

## 🎨 Code Style Guide

### TypeScript

```typescript
// ✅ DO: Use clear naming
const getUserById = async (userId: string): Promise<User> => {
  return await db.user.findUnique({ where: { id: userId } });
};

// ❌ DON'T: Use vague names or any types
const getU = async (u: any) => {
  return await db.u.findUnique({ where: { id: u } });
};
```

### Naming Conventions

| Type | Convention | Example |
|------|-----------|---------|
| Variables | camelCase | `const userEmail` |
| Constants | UPPER_SNAKE_CASE | `const API_TIMEOUT = 5000` |
| Classes | PascalCase | `class UserService` |
| Files | kebab-case | `user-service.ts` |
| Directories | kebab-case | `src/api/routes` |

### Formatting

- Line length: 100 characters (soft limit)
- Indentation: 2 spaces
- Semicolons: Required
- Quotes: Single quotes for strings
- Trailing commas: Yes

### ESLint & Prettier

```bash
# Format code
npm run format

# Lint code
npm run lint

# Fix linting issues
npm run lint:fix
```

---

## 📝 Commit Guidelines

Follow [Conventional Commits](https://www.conventionalcommits.org/) specification:

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Commit Types

- **feat**: A new feature
- **fix**: A bug fix
- **docs**: Documentation only changes
- **style**: Changes that don't affect code meaning (formatting, etc.)
- **refactor**: Code change that neither fixes a bug nor adds a feature
- **test**: Adding missing tests or correcting existing tests
- **chore**: Changes to build process, dependencies, etc.
- **perf**: Code change that improves performance

### Commit Message Examples

```bash
# Feature
git commit -m "feat(auth): add two-factor authentication"

# Bug fix
git commit -m "fix(dashboard): resolve chart rendering issue"

# Documentation
git commit -m "docs(readme): update installation instructions"

# With body
git commit -m "feat(api): implement user search endpoint

Add comprehensive search functionality to user API.
Supports filtering by name, email, and status.

Closes #123"
```

---

## 🔄 Pull Request Process

### Before Submitting

1. **Update from upstream**:
   ```bash
   git fetch upstream
   git rebase upstream/main
   ```

2. **Run tests**:
   ```bash
   npm run test
   npm run test:coverage
   ```

3. **Lint code**:
   ```bash
   npm run lint:fix
   npm run format
   ```

4. **Build project**:
   ```bash
   npm run build
   ```

### PR Description Template

```markdown
## Description
Brief description of changes.

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Breaking change
- [ ] Documentation update

## Related Issues
Closes #(issue number)

## Testing Done
Describe testing performed.

## Screenshots (if applicable)
Add screenshots for UI changes.

## Checklist
- [ ] Code follows style guidelines
- [ ] Tests added/updated
- [ ] Documentation updated
- [ ] No breaking changes
- [ ] PR title follows convention
```

### Review Process

1. Maintainers review your PR
2. Address any requested changes
3. Push updates to the same branch
4. Rebase and force push if requested
5. PR is merged once approved

---

## 🧪 Testing Requirements

### Test Coverage Minimum
- Unit tests: 80% coverage
- Integration tests: Critical paths
- E2E tests: User workflows

### Writing Tests

```typescript
// Example: Jest test
describe('UserService', () => {
  describe('getUserById', () => {
    it('should return user when found', async () => {
      const userId = 'user-123';
      const mockUser = { id: userId, name: 'John' };
      
      jest.spyOn(db.user, 'findUnique').mockResolvedValue(mockUser);
      
      const result = await userService.getUserById(userId);
      
      expect(result).toEqual(mockUser);
    });

    it('should throw error when user not found', async () => {
      jest.spyOn(db.user, 'findUnique').mockResolvedValue(null);
      
      await expect(userService.getUserById('invalid-id'))
        .rejects.toThrow('User not found');
    });
  });
});
```

### Running Tests

```bash
# Run all tests
npm run test

# Run tests in watch mode
npm run test:watch

# Generate coverage report
npm run test:coverage
```

---

## 📚 Documentation

### Code Comments

```typescript
/**
 * Calculates the average score for a user across all contests.
 * 
 * @param userId - The unique identifier of the user
 * @returns Promise<number> - The average score
 * @throws Error if user not found
 */
const getUserAverageScore = async (userId: string): Promise<number> => {
  // Implementation
};
```

### File Headers

```typescript
/**
 * User Service Module
 * 
 * Handles all user-related operations including authentication,
 * profile management, and user queries.
 * 
 * @module services/userService
 */
```

### Update Documentation

- Update README.md for user-facing changes
- Update relevant docs in `/docs` folder
- Add API documentation for new endpoints
- Update CHANGELOG.md

---

## 🐛 Reporting Issues

### Bug Report Template

```markdown
**Describe the bug**
Clear description of the issue.

**Steps to reproduce**
1. Step 1
2. Step 2
3. ...

**Expected behavior**
What should happen.

**Actual behavior**
What actually happens.

**Environment**
- OS: [e.g., Ubuntu 22.04]
- Node version: [e.g., 18.0.0]
- Browser: [if applicable]

**Screenshots**
[If applicable]
```

---

## 📞 Getting Help

- Check [existing issues](https://github.com/sndp6800/SNOT-OLYMPIADS/issues)
- Read [documentation](./docs)
- Ask in [GitHub Discussions](https://github.com/sndp6800/SNOT-OLYMPIADS/discussions)

---

## 🎉 Thank You!

Your contributions help make SNOT-OLYMPIADS better!
