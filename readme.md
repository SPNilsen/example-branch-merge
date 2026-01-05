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
