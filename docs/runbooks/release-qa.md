# Release QA Runbook

Use this checklist before production release.

## Pre-release

- [ ] Release scope matches approved stories/work orders
- [ ] RAID has no unresolved Critical issue
- [ ] Regression checklist completed
- [ ] Smoke test staging completed
- [ ] Rollback plan documented
- [ ] Solo PM sign-off recorded

## Regression Checklist

- [ ] App loads on target browser/mobile viewport
- [ ] Auth flow works if included
- [ ] Onboarding flow works if included
- [ ] Daily mission flow works if included
- [ ] Practice/recording flow works if included
- [ ] Feedback/retry flow works if included
- [ ] Delete/retention/privacy controls work if included
- [ ] Error states are acceptable

## Release Notes

- [ ] `CHANGELOG.md` or release notes updated
- [ ] Known limitations documented
