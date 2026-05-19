# A Guide to Writing Better Git Commits

## Why Commits Matter

A commit message is not just a formality — it is a record of what changed in the project.

Good commit messages help the team:
- Understand changes quickly
- Debug issues faster
- Review pull requests easily
- Track project history clearly
- Collaborate efficiently
- Revert changes safely when needed

Bad commit messages create confusion after a few days or months.

### Bad Examples
```bash
git commit -m "fixes"
git commit -m "changes"
git commit -m "updated"
git commit -m "misc"
git commit -m "final fix"
```

These messages do not explain:
- What changed
- Why it changed
- Which module was affected

---

## Bad vs Good Examples

### ❌ Bad Commit Messages
```bash
git commit -m "fix"
git commit -m "changes"
git commit -m "done"
git commit -m "updated code"
```

### ✅ Good Commit Messages
```bash
git commit -m "fix(auth): handle expired JWT token"
git commit -m "feat(chat): add typing indicator"
git commit -m "docs(readme): update setup instructions"
git commit -m "refactor(api): separate controller logic"
```

Good commit messages are:
- Clear
- Short
- Meaningful
- Easy to understand later

---

## Conventional Commit Format

We will follow the **Conventional Commits** format.

### Format
```bash
<type>(optional-scope): <description>
```

### Example
```bash
feat(auth): add forgot password flow
```

### Breakdown

| Part | Meaning |
|---|---|
| feat | Type of change |
| auth | Module/feature affected |
| add forgot password flow | Description of the change |

---

## Types Table

| Type | Purpose | Example |
|---|---|---|
| feat | New feature | feat(auth): add login API |
| fix | Bug fix | fix(cart): prevent duplicate items |
| docs | Documentation changes | docs(readme): update setup guide |
| refactor | Code improvement without changing behavior | refactor(user): simplify validation |
| style | UI/formatting changes | style(button): improve spacing |
| test | Add or update tests | test(auth): add login tests |
| chore | Maintenance/dependency updates | chore(deps): update express version |
| perf | Performance improvements | perf(feed): optimize query speed |

---

## Real Project Examples

### Frontend Examples
```bash
feat(reels): add infinite scrolling
fix(ui): correct navbar alignment on mobile
style(profile): improve card spacing
refactor(feed): move API logic to custom hook
```

### Backend Examples
```bash
feat(auth): add refresh token support
fix(payment): handle webhook retry failure
refactor(user): optimize MongoDB aggregation
chore(server): update environment variables
```

### Database Examples
```bash
refactor(db): add indexes for faster queries
fix(schema): correct user validation rules
```

---

## Best Practices

### 1. Keep Messages Short and Clear

✅ Good
```bash
fix(chat): prevent duplicate messages
```

❌ Bad
```bash
fixed issue where duplicate messages were coming in chat multiple times
```

---

### 2. Use Lowercase

✅ Good
```bash
feat(auth): add login api
```

❌ Bad
```bash
Feat(Auth): Added Login API
```

---

### 3. One Commit = One Purpose

❌ Bad
```bash
feat: add login and fix navbar and update README
```

✅ Good
```bash
feat(auth): add login page
fix(ui): correct navbar responsiveness
docs(readme): update setup guide
```

---

### 4. Commit Frequently

Do not keep large uncommitted changes for many days.

Small commits are:
- Easier to review
- Easier to debug
- Easier to revert

---

### 5. Write Meaningful Descriptions

Ask yourself:

> “If I see this commit after 6 months, will I understand what changed?”

If the answer is no, improve the commit message.

---

## Team Guidelines

### Daily Pushes

- Push your code daily to your own branch
- Do not keep code only on your local machine

### Example Branch Names
```bash
feature/zain-auth
feature/chat-module
feature/payment-ui
```

---

### Pull Development Branch Daily

Every team member should pull the latest changes from the `development` branch daily.

Even if there are no visible updates, always sync your branch.

### Example
```bash
git checkout development
git pull origin development
```

Then update your branch:
```bash
git checkout your-branch
git merge development
```

This helps:
- Avoid merge conflicts
- Keep everyone updated
- Reduce integration issues

---

### Before Raising a Pull Request (PR)

Before creating a PR:
- Test your code properly
- Ensure there are no unnecessary files
- Resolve conflicts if any
- Ask once before raising the PR

This helps maintain proper review flow and avoids confusion.

---

## Final Reminder

Good commit messages are a small effort today that save a lot of time in the future.

A clean Git history makes the project:
- Easier to maintain
- Easier to debug
- Easier to scale
- More professional for the entire team

> Write commits for your future self and your teammates.
