# Release Process

How releases are created and published.

---

## 📦 Version Numbering

We follow [Semantic Versioning](https://semver.org/):

- **Major (X.0.0):** Breaking changes
- **Minor (1.X.0):** New features, backwards compatible
- **Patch (1.0.X):** Bug fixes, backwards compatible

Example: `2.3.1`

---

## 🔄 Release Cycle

- **Major releases:** Annually
- **Minor releases:** Quarterly
- **Patch releases:** As needed

---

## 📝 Release Checklist

### 1. Pre-Release (Week Before)

- [ ] All planned features merged
- [ ] All tests passing
- [ ] Documentation updated
- [ ] CHANGELOG.md updated
- [ ] Version numbers bumped

### 2. Release Candidate

- [ ] Create RC branch: `release/v2.3.0-rc1`
- [ ] Tag RC: `v2.3.0-rc1`
- [ ] Deploy to test PyPI
- [ ] Community testing (1 week)

### 3. Final Release

- [ ] Address RC feedback
- [ ] Create release branch: `release/v2.3.0`
- [ ] Tag release: `v2.3.0`
- [ ] Deploy to PyPI
- [ ] Create GitHub release with notes
- [ ] Announce on blog/social media

### 4. Post-Release

- [ ] Merge release branch to main
- [ ] Update documentation site
- [ ] Close milestone on GitHub
- [ ] Plan next release

---

## 🏷️ Creating a Release (Maintainers)

```bash
# Update version
bumpversion minor  # or major/patch

# Create tag
git tag -a v2.3.0 -m "Release v2.3.0"
git push origin v2.3.0

# Build and publish
python -m build
twine upload dist/*
```

---

## 📰 Release Notes Template

```markdown
# OpenLIFU v2.3.0

## New Features
- Added support for multi-target planning
- Improved calibration workflow

## Bug Fixes
- Fixed race condition in serial communication
- Corrected coordinate transformation error

## Breaking Changes
- Renamed `plan()` to `create_plan()`
- Removed deprecated `old_api()` function

## Upgrade Guide
See [UPGRADING.md](UPGRADING.md) for migration instructions.

## Contributors
Thanks to @user1, @user2, @user3 for contributions!
```

---

## 🚀 Automated Releases

Releases are partially automated via GitHub Actions:
- Tests run on tag push
- Packages built automatically
- PyPI upload (with approval)

---

**Questions?** Contact release team via [discussions](https://github.com/OpenwaterHealth/openwater-commons/discussions).
