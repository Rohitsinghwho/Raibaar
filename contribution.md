# Contributing Guide

Welcome to the project! Please read this guide before contributing.

---

## Table of Contents

- [Branching Strategy](#branching-strategy)
- [Branch Naming](#branch-naming)
- [Commit Convention](#commit-convention)
- [Pull Request Guidelines](#pull-request-guidelines)
- [Merge Rules](#merge-rules)

---

## Branching Strategy

We follow a **GitFlow-inspired** branching model.

### Core Branches

| Branch | Purpose |
|--------|---------|
| `main` | Production-ready code. Always stable. Tagged with version releases. |
| `develop` | Integration branch. All features merge here first before going to `main`. |

> ⚠️ Never push directly to `main` or `develop`. Always use a Pull Request.

### Supporting Branches

| Branch | Purpose |
|--------|---------|
| `feature/*` | New screens, components, or functionality |
| `fix/*` | Bug fixes during development |
| `hotfix/*` | Urgent fixes directly off `main` (production bugs) |
| `release/*` | Pre-release stabilization, version bumping, changelog |
| `chore/*` | Config changes, dependency updates, CI/CD tweaks |

### Flow

```
feature/* ──┐
fix/*  ─────┼──► develop ──► release/vX.X.X ──► main
chore/* ────┘                                      │
                                                   │
hotfix/* ──────────────────────────────────────────┘
```

---

## Branch Naming

Use lowercase with hyphens. Always prefix with the branch type.

```
feature/onboarding-screen
feature/auth-login
fix/splash-screen-crash
fix/tab-navigation-broken
hotfix/payment-api-broken
release/v1.0.0
chore/update-expo-sdk-52
chore/setup-eslint
```

---

## Commit Convention

We use **Conventional Commits** for clear and consistent commit history.

### Format

```
<type>(<scope>): <short description>
```

### Types

| Type | When to use |
|------|-------------|
| `feat` | A new feature or screen |
| `fix` | A bug fix |
| `chore` | Build process, config, dependency updates |
| `refactor` | Code restructuring without feature changes |
| `style` | Formatting, missing semicolons, etc. |
| `test` | Adding or updating tests |
| `docs` | Documentation changes |
| `perf` | Performance improvements |

### Examples

```
feat(auth): add login screen with email and password
fix(navigation): resolve tab bar not rendering on Android
chore(deps): update expo-router to v3.5.0
docs(readme): update setup instructions
refactor(home): extract header into separate component
```

---

## Pull Request Guidelines

1. **Branch off from the right base:**
   - `feature/*`, `fix/*`, `chore/*` → branch off `develop`
   - `hotfix/*` → branch off `main`

2. **Keep PRs small and focused** — one feature or fix per PR.

3. **Fill out the PR description** with:
   - What changed and why
   - Screenshots (for UI changes)
   - Any related issue numbers

4. **PR title** should follow the commit convention:
   ```
   feat(profile): add user avatar upload
   ```

5. **Request at least one reviewer** before merging.

---

## Merge Rules

| From | Into | Method |
|------|------|--------|
| `feature/*` | `develop` | Squash & Merge |
| `fix/*` | `develop` | Squash & Merge |
| `chore/*` | `develop` | Squash & Merge |
| `release/*` | `main` + `develop` | Merge Commit |
| `hotfix/*` | `main` + `develop` | Merge Commit |

- **Delete branches** after merging.
- **Tag `main`** after every release: `git tag v1.0.0`

---

## Expo-Specific Notes

- Bump `version` in both `app.json` and `package.json` on `release/*` branches.
- Never commit `.env` files — use `app.config.js` with `process.env` for secrets.
- Test on both **iOS and Android** before opening a PR for UI changes.