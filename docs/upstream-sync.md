# Upstream Sync Strategy with Twenty CRM

This document defines the strategy for maintaining synchronization with the upstream [Twenty CRM](https://github.com/twentyhq/twenty) repository.

## Overview

Outcome CRM is a fork of Twenty CRM, customized for professional services and consulting firms. We benefit from Twenty's active open-source development while adding industry-specific extensions.

## Branch Structure

```
twenty/main (upstream)
    │
    ▼
outcome/main (our main branch)
    │
    ├── outcome/develop (integration branch)
    │   ├── feature/accounts-tier-enum
    │   ├── feature/psa-module
    │   └── feature/graphrag-integration
    │
    └── outcome/release/v2.x (release branches)
```

| Branch | Purpose |
|--------|---------|
| `outcome/main` | Production-ready code |
| `outcome/develop` | Integration branch for features |
| `outcome/upstream-sync` | Staging for upstream merges |
| `feature/*` | Individual feature development |
| `release/v2.x` | Release preparation |

## Sync Frequency

| Sync Type | Frequency | Trigger |
|-----------|-----------|---------|
| **Minor Updates** | Weekly | Automated check |
| **Major Releases** | Within 1 week of release | Manual review |
| **Security Patches** | Immediate | Automated alerts |
| **Breaking Changes** | As needed | Manual assessment |

## Sync Process

### 1. Automated Upstream Check (Weekly)

```bash
# Add Twenty as upstream remote (one-time)
git remote add upstream https://github.com/twentyhq/twenty.git

# Fetch upstream changes
git fetch upstream

# Create sync branch
git checkout -b outcome/upstream-sync upstream/main
```

### 2. Review Changes

Before merging, review:

1. **Breaking Changes**: Check Twenty's CHANGELOG and release notes
2. **Schema Changes**: Review TypeORM/Prisma migrations
3. **API Changes**: Check for endpoint modifications
4. **UI Changes**: Review component updates

### 3. Merge Strategy

```bash
# Switch to develop
git checkout outcome/develop

# Merge upstream changes
git merge outcome/upstream-sync --no-ff -m "chore: sync with Twenty v0.x.x"

# Resolve conflicts (see Conflict Resolution below)

# Run tests
npm test

# Push
git push origin outcome/develop
```

## Conflict Resolution

### Priority Order

1. **Outcome-specific files** → Keep ours
2. **Schema extensions** → Merge carefully
3. **UI customizations** → Keep ours, apply upstream fixes
4. **Core library updates** → Prefer upstream

### Protected Files (Always Keep Ours)

```
# Outcome-specific files - never accept upstream changes
VISION.md
docs/roadmap.md
docs/upstream-sync.md

# Schema extensions
packages/twenty-server/src/engine/core-modules/outcome-*/**

# Custom configurations
.env.local
.env.production
```

### Merge-Carefully Files

```
# Extend but don't overwrite
prisma/schema.prisma          # Add our models, keep Twenty's
src/engine/core-modules/**    # Merge module extensions
packages/twenty-front/**      # Merge UI customizations
```

## Code Separation Strategy

### Directory Structure

```
packages/
├── twenty-server/
│   └── src/
│       └── engine/
│           └── core-modules/
│               ├── account/         # Twenty's (extended)
│               ├── contact/         # Twenty's (extended)
│               ├── opportunity/     # Twenty's (extended)
│               └── outcome-*/       # Our additions (protected)
│                   ├── outcome-psa/
│                   ├── outcome-engagement/
│                   └── outcome-ai/
└── twenty-front/
    └── src/
        └── modules/
            ├── accounts/            # Twenty's (extended)
            └── outcome-*/           # Our additions (protected)
```

### Naming Convention

| Type | Prefix | Example |
|------|--------|---------|
| Custom modules | `outcome-` | `outcome-psa`, `outcome-engagement` |
| Extended entities | None (extend in place) | Add fields to Account |
| Custom services | `Outcome` | `OutcomePsaService` |
| Custom components | `Outcome` | `OutcomeStakeholderView` |

## Testing After Sync

1. **Database Migrations**: `npm run db:migrate`
2. **Schema Validation**: `npm run db:validate`
3. **Unit Tests**: `npm test`
4. **Integration Tests**: `npm run test:integration`
5. **E2E Tests**: `npm run test:e2e`
6. **Manual Smoke Test**: Core flows work

## Rollback Plan

If sync introduces issues:

```bash
# Revert the merge commit
git revert -m 1 <merge-commit-hash>

# Push revert
git push origin outcome/develop

# Create issue to investigate
# Re-attempt sync after fixes
```

## Communication

| Event | Action |
|-------|--------|
| Sync Started | Post in #dev-crm Slack |
| Conflicts Found | Tag relevant engineers |
| Sync Complete | Update CHANGELOG |
| Issues Found | Create GitHub issue |

## Contribution Back to Twenty

When we develop features that are generalizable:

1. **Identify**: Features not consulting-specific
2. **Extract**: Separate from Outcome-specific code
3. **Test**: Ensure works without our extensions
4. **PR**: Submit to twentyhq/twenty
5. **Maintain**: Keep in sync until merged

### Candidate Features for Contribution

- [ ] GraphRAG integration patterns
- [ ] Stage gating validation framework
- [ ] Audit logging enhancements
- [ ] Dashboard widget framework

## Version Alignment

| Twenty Version | Outcome Version | Status |
|----------------|-----------------|--------|
| v0.30.x | v2.0.x | 🟢 Current |
| v0.31.x | v2.1.x | 📋 Planned |
| v0.32.x | v2.2.x | 📋 Planned |

---

*Last updated: 2026-01-02*
