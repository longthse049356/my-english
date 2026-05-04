# Smoke Test Runbook

Run after staging deploy and production deploy.

## Basic App Health

- [ ] App URL opens successfully
- [ ] No obvious console/runtime error on first load
- [ ] Primary route renders
- [ ] Mobile viewport renders acceptably

## MVP Flow Smoke Test

- [ ] User can reach onboarding or home
- [ ] User can see a daily mission or placeholder state
- [ ] User can start the practice flow or see a clear unavailable state
- [ ] User can complete a happy-path action without crash
- [ ] Error/empty state copy is understandable

## Post-test

- [ ] Record result in release notes
- [ ] If failed, stop release or rollback
