# Code Review Process

How code reviews work in Openwater projects.

---

## 🎯 Review Goals

- Maintain code quality
- Share knowledge
- Catch bugs early
- Ensure consistency

---

## 👥 Who Reviews

- **Core contributors:** Can approve PRs
- **Community members:** Can comment and suggest
- **Automated checks:** CI/CD runs tests

---

## 📝 Review Checklist

### Code Quality
- [ ] Code is clear and readable
- [ ] Follows project style guide
- [ ] No unnecessary complexity
- [ ] Error handling is appropriate

### Testing
- [ ] Tests cover new functionality
- [ ] Existing tests still pass
- [ ] Edge cases considered

### Documentation
- [ ] Code comments for complex logic
- [ ] README updated if needed
- [ ] API docs updated

### Security
- [ ] No sensitive data exposed
- [ ] Input validation present
- [ ] Dependencies are safe

---

## 💬 Giving Feedback

**Be kind and constructive:**
- ✅ "Consider using X here for better performance"
- ❌ "This code is terrible"

**Be specific:**
- ✅ "Line 42: This could cause a race condition"
- ❌ "Something looks wrong"

**Explain why:**
- ✅ "Let's use list comprehension here - it's more Pythonic and faster"
- ❌ "Change this"

---

## 🔄 Responding to Reviews

- **Address all comments:** Even if you disagree, discuss
- **Ask questions:** If feedback is unclear
- **Push updates:** Make changes and push to same branch
- **Mark resolved:** Use GitHub's "resolve conversation"

---

## ⏱️ Review Timeline

- **First review:** Within 2-3 business days
- **Follow-up reviews:** Within 1-2 days
- **Urgent fixes:** Same day

---

## ✅ Approval Process

1. **Automated checks pass** (CI/CD)
2. **At least 1 approval** from core contributor
3. **All conversations resolved**
4. **No outstanding change requests**

Then → **Merge!** 🎉

---

**Questions?** Ask in [discussions](https://github.com/OpenwaterHealth/openwater-commons/discussions).
