# CLAUDE.md - AI Assistant Configuration

This file provides context and instructions for AI assistants working on the SNOT-OLYMPIADS project.

---

## 📖 Project Context

### Overview
**SNOT-OLYMPIADS** is India's next-generation National Olympiad Platform built with:
- **Frontend**: Next.js 14 + TypeScript + TailwindCSS
- **Backend**: Node.js + Express + PostgreSQL
- **Architecture**: Enterprise-grade, scalable, secure

### Key Objectives
1. Provide seamless olympiad management for students and administrators
2. Implement real-time contest evaluation
3. Ensure enterprise-level security
4. Scale to handle thousands of concurrent users
5. Integrate AI/ML for intelligent features

---

## 🎯 AI Assistant Responsibilities

### Code Generation
- Follow TypeScript strict mode
- Use established design patterns
- Maintain code consistency
- Include proper error handling
- Add JSDoc comments

### Documentation
- Clear, concise explanations
- Code examples where relevant
- Follow existing documentation style
- Link to related documents

### Best Practices
- Suggest security improvements
- Recommend performance optimizations
- Identify potential issues
- Propose testing strategies

---

## 📁 Directory Structure Reference

```
SNOT-OLYMPIADS/
├── frontend/           # Next.js application
│   ├── app/           # App router pages
│   ├── components/    # Reusable components
│   ├── lib/           # Utilities and helpers
│   ├── styles/        # Global styles
│   └── __tests__/     # Component tests
├── backend/           # Express API
│   ├── src/
│   │   ├── routes/    # API endpoints
│   │   ├── services/  # Business logic
│   │   ├── models/    # Data models
│   │   ├── middleware/# Custom middleware
│   │   └── utils/     # Utilities
│   └── __tests__/     # API tests
├── database/          # PostgreSQL
│   ├── migrations/    # Database migrations
│   ├── schemas/       # Schema definitions
│   └── seeds/         # Seed data
├── docs/              # Comprehensive documentation
├── tests/             # Test configurations
└── infrastructure/    # Docker & deployment
```

---

## 🔐 Security Guidelines

### Critical Rules
1. **Never expose secrets** in code or documentation
2. **Validate all inputs** on backend and frontend
3. **Use environment variables** for configuration
4. **Implement CORS** properly
5. **Hash passwords** with bcrypt
6. **Use HTTPS** in production
7. **Sanitize outputs** to prevent XSS
8. **Implement rate limiting** on APIs

### Code Review Checklist
- ✓ No hardcoded credentials
- ✓ Input validation present
- ✓ SQL injection prevention (use parameterized queries)
- ✓ Error messages don't leak sensitive info
- ✓ Authentication/authorization enforced
- ✓ HTTPS only in production

---

## 🏗️ Architecture Principles

### Frontend
- **Component-driven**: Small, reusable components
- **State management**: Redux for complex state
- **Server components**: Use Next.js App Router
- **Type safety**: Strict TypeScript
- **Accessibility**: WCAG 2.1 AA compliant

### Backend
- **RESTful design**: Consistent API patterns
- **Error handling**: Proper HTTP status codes
- **Logging**: Structured logging with context
- **Validation**: Schema validation on all inputs
- **Database**: Prepared statements, migrations

### Database
- **Normalization**: 3NF for data integrity
- **Constraints**: Foreign keys, unique constraints
- **Indexes**: On frequently queried columns
- **Migrations**: Versioned schema changes

---

## 📝 Coding Standards

### TypeScript
```typescript
// ✅ GOOD: Explicit types, clear naming
interface UserCreate {
  email: string;
  firstName: string;
  lastName: string;
}

const createUser = async (data: UserCreate): Promise<User> => {
  validateEmail(data.email);
  return await userService.save(data);
};

// ❌ BAD: Any types, unclear naming
const create = async (d: any): Promise<any> => {
  return await service.save(d);
};
```

### Naming Conventions
- **Functions**: `verb + noun` (e.g., `getUserById`, `createContest`)
- **Constants**: `UPPER_SNAKE_CASE` (e.g., `API_TIMEOUT`, `MAX_RETRIES`)
- **Files**: `kebab-case` (e.g., `user-service.ts`, `contest-routes.ts`)
- **Classes**: `PascalCase` (e.g., `UserService`, `ContestHandler`)
- **React components**: `PascalCase` (e.g., `UserProfile`, `ContestCard`)

### Comments and Documentation
```typescript
/**
 * Calculates contest ranking based on scores and penalties.
 * 
 * @param contestId - The unique contest identifier
 * @param submissions - Array of user submissions
 * @returns Ranked list of users with scores
 * @throws {ContestNotFoundError} If contest doesn't exist
 * 
 * @example
 * const rankings = await calculateRankings('contest-123', submissions);
 */
const calculateRankings = async (
  contestId: string,
  submissions: Submission[]
): Promise<Ranking[]> => {
  // Implementation
};
```

---

## 🧪 Testing Strategy

### Test Levels
1. **Unit Tests**: Individual functions/components
2. **Integration Tests**: Multiple components working together
3. **E2E Tests**: Complete user workflows
4. **Performance Tests**: Load and stress testing

### Coverage Requirements
- **Minimum**: 80% code coverage
- **Critical paths**: 100% coverage
- **UI components**: Visual regression tests

### Test File Location
```
feature/
├── component.tsx
└── __tests__/
    └── component.test.tsx
```

---

## 🚀 Performance Considerations

### Frontend
- Image optimization (Next.js Image component)
- Code splitting and lazy loading
- Caching strategies (SWR, React Query)
- Bundle size monitoring

### Backend
- Database query optimization
- API response caching
- Pagination for large datasets
- Rate limiting and throttling

### Database
- Proper indexing
- Query optimization
- Connection pooling
- Automated backups

---

## 📚 Key Documentation Files

| File | Purpose |
|------|---------|
| [00_PROJECT_CHARTER.md](./docs/00_PROJECT_CHARTER.md) | Vision & objectives |
| [03_FRONTEND_ARCHITECTURE.md](./docs/03_FRONTEND_ARCHITECTURE.md) | Frontend design |
| [04_BACKEND_ARCHITECTURE.md](./docs/04_BACKEND_ARCHITECTURE.md) | Backend design |
| [07_SECURITY_ARCHITECTURE.md](./docs/07_SECURITY_ARCHITECTURE.md) | Security implementation |
| [12_DEVELOPER_GUIDE.md](./docs/12_DEVELOPER_GUIDE.md) | Development guide |

---

## 🛠️ Common Tasks

### Creating a New Feature
1. Check related documentation
2. Plan architecture if needed
3. Write tests first (TDD preferred)
4. Implement feature
5. Update documentation
6. Submit PR with description

### Code Generation
1. Follow established patterns
2. Match file structure conventions
3. Include error handling
4. Add JSDoc comments
5. Write accompanying tests

### Documentation
1. Use Markdown formatting
2. Add code examples
3. Include diagrams if helpful
4. Link to related docs
5. Keep current and accurate

---

## 🚨 Red Flags / Things to Avoid

❌ Don't:
- Use `any` type in TypeScript
- Hardcode configuration values
- Commit secrets or credentials
- Skip error handling
- Ignore TypeScript warnings
- Mix business logic with UI
- Make functions do too much
- Forget to add tests
- Write unclear variable names
- Use deprecated APIs

✅ Do:
- Use strict types
- Environment variables for config
- Keep commits clean
- Handle errors properly
- Respect TypeScript strict mode
- Separate concerns
- Keep functions focused
- Test thoroughly
- Use clear naming
- Stay current with dependencies

---

## 📞 Getting Help

- **Documentation**: See `/docs` folder
- **Issues**: Check GitHub Issues for similar problems
- **Discussions**: Ask in GitHub Discussions
- **Code Examples**: Look at existing implementations

---

**Last Updated**: 2026-07-15
**Version**: 1.0.0
