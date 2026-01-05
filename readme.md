# Branching Strategy

- **main**: Production-ready code
- **test**: Pre-production testing environment
- **dev**: Development integration branch
- **feature/**: Feature development branches

## Workflow
1. Create feature branches from dev
2. Merge features into dev
3. Merge dev into test for QA
4. Merge test into main for production release

## Complete Git Workflow Script

### Initial Setup
```bash
git init
git checkout -b main
touch readme.md
git add readme.md
git commit -m "Initial commit: Add readme.md"
git remote add origin <repo-url>
git push -u origin main
```

### Branch Structure Creation
```bash
git checkout -b test
git push -u origin test
git checkout -b dev
git push -u origin dev
```

### Feature Development Cycle
```bash
# Create feature branch
git checkout dev
git checkout -b feature/FED-XX

# Make changes and commit
git add .
git commit -m "feat: Description of feature"
git push -u origin feature/FED-XX

# Merge to dev
git checkout dev
git merge --no-ff feature/FED-XX -m "Merge feature/FED-XX into dev"
git push origin dev

# Merge to test
git checkout test
git merge --no-ff dev -m "Merge dev into test for QA"
git push origin test

# Tag in test
git tag -a v1.0.X -m "Release version 1.0.X"
git push origin v1.0.X

# Merge to main
git checkout main
git merge --no-ff test -m "Merge test into main: Release v1.0.X"
git tag -a v1.0.X-release -m "Production release v1.0.X"
git push origin main
git push origin v1.0.X-release
```

## Version History
- v1.0.0 - Initial release with branching strategy
- v1.0.1 - Added complete Git workflow documentation
