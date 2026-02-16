# Android Tools Builder

Automated GitHub Actions untuk build lpdump dan Android command-line tools lainnya.

## 🚀 Quick Start

1. Fork atau clone repository ini
2. Enable GitHub Actions di Settings
3. Set permissions: Settings → Actions → "Read and write permissions"
4. Push tag untuk trigger build:
   ```bash
   git tag v35.0.2
   git push origin v35.0.2
   ```

Atau trigger manual dari tab Actions → "Build and Release Android Tools" → Run workflow

## 📦 Download

Setelah build selesai, binary tersedia di [Releases](../../releases).

```bash
# Download dan install
wget https://github.com/YOUR_USERNAME/REPO_NAME/releases/download/v35.0.2/android-tools-linux-x86_64-35.0.2.tar.gz
tar -xzf android-tools-linux-x86_64-35.0.2.tar.gz
sudo cp usr/bin/* /usr/local/bin/
```

## ✨ Tools Included

- **lpdump, lpmake, lpadd, lpunpack, lpflash** - Logical partition tools
- **adb, fastboot** - Android debug tools
- **mkbootimg, unpack_bootimg, avbtool** - Boot image tools
- **simg2img, img2simg** - Image conversion tools
- **mke2fs.android, mkdtboimg** - Other utilities

## 🔧 Requirements

Binary memerlukan dependencies berikut (Ubuntu/Debian):
```bash
sudo apt install libusb-1.0-0 libprotobuf23 libbrotli1 libzstd1 liblz4-1
```

## 📝 Usage

```bash
# Dump super.img metadata
lpdump super.img

# Extract partitions
lpunpack super.img output_dir/

# ADB commands
adb devices
adb shell

# Fastboot commands
fastboot devices
fastboot flash boot boot.img
```

## 🔄 Update Versi

```bash
# Check versi terbaru: https://github.com/nmeum/android-tools/releases
git tag v35.0.3
git push origin v35.0.3
```

## 📄 License

- Workflow & scripts: MIT License
- android-tools: Apache-2.0 License

## 🔗 Links

- **Upstream**: https://github.com/nmeum/android-tools
- **Android Docs**: https://source.android.com
