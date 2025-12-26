# 📋 Konfigurasi GitHub Profile - Quick Setup Guide

## 📌 Overview
Dokumentasi lengkap untuk mengkonfigurasi GitHub profile dengan GitHub Actions workflows yang optimal.

---

## 🚀 Quick Start

### 1. Setup Awal
```bash
# Clone repository
git clone https://github.com/firmanfarelrichardo/firmanfarelrichardo.git
cd firmanfarelrichardo

# Pastikan branch main/master ada
git branch -a
```

### 2. Struktur File Penting
```
.github/
├── workflows/
│   ├── main.yml                  # Main workflow (validation + updates)
│   ├── profile-update.yml        # Weekly stats update
│   ├── readme-validate.yml       # README validation
│   └── [other workflows]
.markdownlint.json               # Markdown linting rules
README.md                        # Profile dokumentasi utama
example1.md                      # Template referensi
```

---

## ⚙️ Konfigurasi GitHub Actions

### Workflow Utama: `main.yml`
**Trigger:** Push ke main/master, PR, Scheduled daily, Manual
**Tasks:**
- ✅ Validate Markdown syntax
- ✅ Check broken links (non-blocking)
- ✅ Update timestamps
- ✅ Auto-commit changes (jika ada)

**Status:** Production-ready, error-tolerant

### Workflow Update: `profile-update.yml`
**Trigger:** Setiap hari Minggu (UTC), Manual
**Tasks:**
- ✅ Update profile statistics log
- ✅ Track last update time
- ✅ Auto-commit ke repository

**Status:** Lightweight, low resource usage

### Workflow Validation: `readme-validate.yml`
**Trigger:** Changes ke README, Example files, PR, Manual
**Tasks:**
- ✅ Markdown syntax check
- ✅ Link validation
- ✅ Quality assurance

**Status:** Strict validation, blocker untuk PR

---

## 🎨 Badge & Links Configuration

### Main Colors Used
- **Primary:** `#6AD3F7` (Cyan/Blue)
- **Secondary:** `#F7DF1E` (Yellow)
- **Accent:** Various shields.io colors

### Customization Points
Untuk personalisasi, edit di `README.md`:

**Username:** Replace `firmanfarelrichardo` dengan username Anda
```markdown
- GitHub URLs
- Badge links (followers, stars)
- Contribution graph
- Profile trophy
```

**Social Links:** Sesuaikan di section "Let's Connect!"
```markdown
- LinkedIn: linkedin.com/in/YOUR_PROFILE
- Twitter: twitter.com/YOUR_HANDLE
- Instagram: instagram.com/YOUR_PROFILE
- Email: your-email@example.com
```

---

## 🔧 Environment Setup

### Requirements
- Node.js 18+ (untuk markdown validation)
- Git configured globally
- GitHub repository dengan main/master branch

### Local Testing
```bash
# Install markdown linter
npm install -g markdownlint-cli

# Validate README
markdownlint README.md

# Check for broken links
npm install -g markdown-link-check
markdown-link-check README.md
```

---

## 📊 Markdown Lint Config

File `.markdownlint.json` mengatur rules:
```json
{
  "default": true,
  "MD003": "consistent",
  "MD007": {"indent": 2},
  "MD013": false,
  "MD033": false
}
```

**Key Rules:**
- ✅ Consistent heading style
- ✅ 2-space indentation
- ✅ No line length limit
- ✅ HTML allowed (untuk styling)

---

## 🚨 Troubleshooting

### Workflow Fails
1. **Markdown validation error**
   - Check syntax di README.md
   - Jalankan `markdownlint README.md` locally
   - Fix issues dan push lagi

2. **Link check fails**
   - Broken links akan di-report tapi non-blocking
   - Update URLs di README jika diperlukan
   - Some dynamic badges may timeout (expected)

3. **Git push fails**
   - Ensure token has `contents: write` permission
   - Check branch protection rules
   - Verify no merge conflicts

### Manual Trigger
Setiap workflow bisa di-trigger manual dari GitHub Actions tab:
1. Go to your repo → Actions
2. Select workflow name
3. Click "Run workflow"
4. Choose branch dan confirm

---

## 📝 File Descriptions

| File | Purpose |
|------|---------|
| `README.md` | Main profile showcase dengan stats & badges |
| `example1.md` | Template referensi styling |
| `example2.md` | Alternatif styling example |
| `.markdownlint.json` | Linting rules |
| `.github/workflows/*.yml` | GitHub Actions automation |

---

## 🎯 Best Practices

✅ **Do's**
- Keep README updated regularly
- Test markdown locally before pushing
- Use consistent formatting
- Update social links when needed
- Monitor workflow runs

❌ **Don'ts**
- Hardcode personal info yang sensitive
- Modify workflow files without testing
- Ignore linting errors
- Leave broken links unaddressed

---

## 📞 Support & References

### Useful Links
- [GitHub Actions Docs](https://docs.github.com/en/actions)
- [Shields.io Badges](https://shields.io)
- [GitHub Readme Stats](https://github.com/anuraghazra/github-readme-stats)
- [Markdown Linter](https://github.com/igorshubovych/markdownlint-cli)

### Badges Services Used
- `img.shields.io` - Badge generation
- `github-readme-stats.vercel.app` - GitHub stats
- `readme-typing-svg.demolab.com` - Typing animation
- `capsule-render.vercel.app` - Header/footer render
- `komarev.com/ghpvc` - Profile view counter

---

## 🔄 Update Schedule

| Task | Frequency | Time (UTC) |
|------|-----------|-----------|
| Main validation | On push + Daily | Every day 00:00 |
| Profile stats | Weekly | Sunday 12:00 |
| Manual trigger | On-demand | N/A |

---

## ✨ Version Info
- **Last Updated:** December 26, 2025
- **Node.js Version:** 18+
- **GitHub Actions:** Latest (v4)
- **Status:** Production Ready ✅

---

<div align="center">
  <b>Made with ❤️ for GitHub Profile Excellence</b>
</div>
