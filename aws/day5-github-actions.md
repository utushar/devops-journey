# ⚙️ Day 5 – GitHub Actions CI Setup

**Date:** 10 July 2025  
**Goal:** Run CI pipeline when code is pushed to GitHub

---

## ✅ What I Did

1. Created `.github/workflows/main.yml`
2. Configured it to:
   - Trigger on push to `main`
   - Set up Python
   - Install Flask
   - Print success message
3. Committed and pushed
4. Verified in GitHub Actions tab ✅

---

## 🔧 Sample Workflow

```yaml
on:
  push:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-python@v4
        with:
          python-version: '3.11'
      - run: pip install flask
      - run: echo "✅ Success"
