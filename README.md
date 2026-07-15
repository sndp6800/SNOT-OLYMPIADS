# SNOT-OLYMPIADS 🏆

**India's Next Generation National Olympiad Platform**

Built with **Next.js**, **TypeScript**, **PostgreSQL** & **Enterprise Architecture**

---

## 🎯 Project Overview

SNOT-OLYMPIADS is a comprehensive digital platform designed to revolutionize India's National Olympiad ecosystem. It provides a scalable, secure, and intuitive system for managing olympiad competitions, student participation, and real-time evaluation.

### Key Features
- 🎓 Multi-level olympiad management
- 👥 Student registration & profile management
- 📊 Real-time contest management
- 🔐 Enterprise-grade security
- 🤖 AI-powered problem analysis
- 📈 Advanced analytics & reporting
- 🌐 Seamless integration capabilities

---

## 📋 Table of Contents

- [Getting Started](#getting-started)
- [Project Structure](#project-structure)
- [Technology Stack](#technology-stack)
- [Development Guidelines](#development-guidelines)
- [Contributing](#contributing)
- [Documentation](#documentation)

---

## 🚀 Getting Started

### Prerequisites
- Node.js 18+ / npm 9+
- PostgreSQL 14+
- Docker & Docker Compose (optional)
- Git

### Installation

```bash
# Clone repository
git clone https://github.com/sndp6800/SNOT-OLYMPIADS.git
cd SNOT-OLYMPIADS

# Install dependencies
npm install

# Setup environment
cp .env.example .env.local

# Setup database
npm run db:migrate

# Start development server
npm run dev
```

### Environment Setup

Refer to [Environment Configuration Guide](./docs/12_DEVELOPER_GUIDE.md#environment-setup) for detailed setup instructions.

---

## 📁 Project Structure

```
SNOT-OLYMPIADS/
├── frontend/              # Next.js frontend application
├── backend/               # Node.js/Express backend services
├── database/              # PostgreSQL schemas & migrations
├── infrastructure/        # Infrastructure as Code (Terraform/Docker)
├── scripts/               # Utility & automation scripts
├── tests/                 # Test suites & configurations
├── docs/                  # Comprehensive documentation
├── .github/               # GitHub workflows & templates
└── [config files]         # Root configuration files
```

See [Architecture Documentation](./docs/03_FRONTEND_ARCHITECTURE.md) for detailed breakdown.

---

## 🛠️ Technology Stack

### Frontend
- **Framework**: Next.js 14+
- **Language**: TypeScript
- **Styling**: TailwindCSS + Shadcn/ui
- **State Management**: Redux Toolkit
- **Testing**: Jest + React Testing Library

### Backend
- **Runtime**: Node.js
- **Framework**: Express.js
- **Database**: PostgreSQL 14+
- **ORM**: Prisma
- **Authentication**: JWT + OAuth2
- **API**: REST + GraphQL (optional)
- **Testing**: Jest + Supertest

### Infrastructure
- **Containerization**: Docker
- **Orchestration**: Docker Compose / Kubernetes
- **CI/CD**: GitHub Actions
- **Monitoring**: ELK Stack / Datadog
- **Deployment**: AWS / Google Cloud / Self-hosted

---

## 📚 Development Guidelines

### Code Style
- Follow [TypeScript Best Practices](./docs/12_DEVELOPER_GUIDE.md)
- ESLint + Prettier enforced
- Strict mode enabled
- No `any` types without justification

### Commit Convention

```
<type>(<scope>): <subject>

<body>
<footer>
```

Types: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`

Example:
```
feat(auth): implement JWT token refresh mechanism

Add automatic token refresh on expiry.
Implement refresh token rotation for security.

Closes #123
```

### Branch Naming
- Feature: `feature/description`
- Bugfix: `fix/description`
- Hotfix: `hotfix/description`
- Documentation: `docs/description`

---

## 🤝 Contributing

We welcome contributions! Please read [CONTRIBUTING.md](./CONTRIBUTING.md) for detailed guidelines.

### Quick Start for Contributors
1. Fork the repository
2. Create your feature branch: `git checkout -b feature/amazing-feature`
3. Commit changes: `git commit -m 'feat: add amazing feature'`
4. Push to branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

---

## 📖 Documentation

Comprehensive documentation available in `/docs`:

| Document | Purpose |
|----------|---------|
| [00_PROJECT_CHARTER.md](./docs/00_PROJECT_CHARTER.md) | Vision, scope, and objectives |
| [01_DESIGN_BIBLE.md](./docs/01_DESIGN_BIBLE.md) | Design principles & UI/UX standards |
| [02_COMPONENT_LIBRARY.md](./docs/02_COMPONENT_LIBRARY.md) | Reusable component catalog |
| [03_FRONTEND_ARCHITECTURE.md](./docs/03_FRONTEND_ARCHITECTURE.md) | Frontend system design |
| [04_BACKEND_ARCHITECTURE.md](./docs/04_BACKEND_ARCHITECTURE.md) | Backend system design |
| [05_DATABASE_ARCHITECTURE.md](./docs/05_DATABASE_ARCHITECTURE.md) | Database schema & models |
| [06_API_SPECIFICATION.md](./docs/06_API_SPECIFICATION.md) | REST & GraphQL APIs |
| [07_SECURITY_ARCHITECTURE.md](./docs/07_SECURITY_ARCHITECTURE.md) | Security implementation |
| [08_AI_ARCHITECTURE.md](./docs/08_AI_ARCHITECTURE.md) | AI/ML integration |
| [09_BRAINSTORM_ARENA.md](./docs/09_BRAINSTORM_ARENA.md) | Future ideas & innovations |
| [10_QA_TESTING.md](./docs/10_QA_TESTING.md) | Testing strategy & procedures |
| [11_DEPLOYMENT.md](./docs/11_DEPLOYMENT.md) | Deployment & DevOps guide |
| [12_DEVELOPER_GUIDE.md](./docs/12_DEVELOPER_GUIDE.md) | Development best practices |

---

## 🔐 Security

- Security policy: [SECURITY.md](./docs/07_SECURITY_ARCHITECTURE.md)
- Report vulnerabilities: [security@snot-olympiads.dev](mailto:security@snot-olympiads.dev)
- See [Security Architecture](./docs/07_SECURITY_ARCHITECTURE.md) for details

---

## 📞 Support & Community

- **Issues**: [GitHub Issues](https://github.com/sndp6800/SNOT-OLYMPIADS/issues)
- **Discussions**: [GitHub Discussions](https://github.com/sndp6800/SNOT-OLYMPIADS/discussions)
- **Email**: support@snot-olympiads.dev

---

## 📜 License

This project is licensed under the MIT License - see [LICENSE](./LICENSE) file for details.

---

## 🙏 Acknowledgments

Built with passion for India's next generation olympiad champions.

---

**Last Updated**: July 2026
**Status**: 🟢 Active Development
