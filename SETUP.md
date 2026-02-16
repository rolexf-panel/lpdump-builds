# Setup Instructions

## 📋 Prerequisites

- GitHub account
- Git installed

## 🚀 Setup (3 Steps)

### 1. Create Repository

Buat repository baru di GitHub atau gunakan yang sudah ada:

```bash
# Option A: Via GitHub CLI
gh repo create lpdump-builds --public --clone

# Option B: Manual
# - Buka https://github.com/new
# - Nama: lpdump-builds (atau nama lain)
# - Visibility: Public atau Private
# - Create repository
```

### 2. Push Files

```bash
# Clone repository (jika belum)
git clone https://github.com/YOUR_USERNAME/lpdump-builds.git
cd lpdump-builds

# Extract dan copy isi ZIP ke repository
# (atau langsung extract ZIP ke direktori ini)

# Commit dan push
git add .
git commit -m "Initial commit: Setup build workflow"
git push origin main
```

### 3. Configure GitHub Actions

**PENTING**: Set permissions untuk GitHub Actions

1. Buka: `https://github.com/YOUR_USERNAME/lpdump-builds/settings/actions`
2. Scroll ke **Workflow permissions**
3. Pilih: ☑️ **"Read and write permissions"**
4. Centang: ☑️ **"Allow GitHub Actions to create and approve pull requests"**
5. Klik **Save**

## ✅ Verify Setup

Check GitHub Actions sudah enabled:

1. Buka tab **Actions** di repository
2. Jika ada banner "Workflows aren't being run", klik **"I understand, enable them"**

## 🎯 Create First Build

### Option A: Via Tag (Recommended)

```bash
git tag v35.0.2
git push origin v35.0.2
```

Build otomatis akan start dan hasil akan muncul di Releases.

### Option B: Via GitHub UI

1. Buka tab **Actions**
2. Pilih workflow **"Build and Release Android Tools"**
3. Klik **"Run workflow"** (kanan atas)
4. Isi:
   - Branch: `main`
   - Version tag: `v35.0.2`
   - Create GitHub Release: ✅
5. Klik **"Run workflow"**

## 📥 Monitor Build

- Build time: ~5-8 menit
- Progress: Tab Actions → klik workflow run yang sedang berjalan
- Logs: Expand steps untuk lihat detail

## 🎉 Done!

Setelah build selesai, binary akan tersedia di:
`https://github.com/YOUR_USERNAME/lpdump-builds/releases`

## 🆘 Troubleshooting

### "Resource not accessible by integration"
→ Set "Read and write permissions" di Settings → Actions

### "ref does not exist"
→ Tag belum di-push: `git push origin v35.0.2`

### Build failed: "Version not found"
→ Check versi tersedia: https://github.com/nmeum/android-tools/releases

### Workflow tidak muncul di Actions tab
→ Enable Actions di Settings → Actions → General
