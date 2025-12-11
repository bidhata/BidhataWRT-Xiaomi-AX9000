# bidhatawrt-boardbin-qcn9074

Custom board-2.bin firmware package for Qualcomm QCN9074 WiFi chipset in OpenWrt.

## Overview

This package provides a vendor-specific `board-2.bin` firmware file for the Qualcomm QCN9074 WiFi chipset. It replaces the default board-2.bin with a custom version for improved compatibility and performance.

## Maintainer

**Krishnendu Paul**
- Email: me@krishnendu.com
- Website: https://krishnendu.com
- GitHub: https://github.com/bidhata/xiaomi_qualcomm_boardbin

## Installation

### 1. Copy Package to OpenWrt Buildroot

Copy this entire package directory to your OpenWrt buildroot:

```bash
cp -r bidhatawrt-boardbin-qcn9074 /path/to/openwrt/package/firmware/
```

### 2. Add Your Vendor board-2.bin File

**IMPORTANT:** Before building, you must replace the placeholder file with your actual vendor-provided `board-2.bin`:

```bash
cd /path/to/openwrt/package/firmware/bidhatawrt-boardbin-qcn9074
# Remove placeholder
rm files/lib/firmware/ath11k/QCN9074/hw1.0/board-2.bin
# Copy your vendor file
cp /path/to/your/vendor/board-2.bin files/lib/firmware/ath11k/QCN9074/hw1.0/
```

### 3. Select Package in menuconfig

```bash
cd /path/to/openwrt
make menuconfig
```

In the menu:
1. Navigate to `Firmware` section
2. Keep existing `ath11k-firmware-*` packages **selected** (do NOT deselect them)
3. Also select `<*> bidhatawrt-boardbin-qcn9074`
4. Save and exit

### 4. Build Firmware

```bash
make package/bidhatawrt-boardbin-qcn9074/compile V=s
# Or build full firmware
make -j$(nproc)
```

## Important Notes

### Do NOT Disable ath11k Packages

**Keep the existing ath11k firmware and driver packages selected!**

Your custom package works alongside the standard ath11k packages. It only replaces the `board-2.bin` file while keeping all other necessary firmware files and drivers intact.

Required packages to keep selected:
- `kmod-ath11k-*` (driver packages)
- `ath11k-firmware-qcn9074` (other firmware files)

### File Installation Path

This package installs the custom board-2.bin to:
```
/lib/firmware/ath11k/QCN9074/hw1.0/board-2.bin
```

This file will override the default board-2.bin provided by the standard ath11k-firmware package.

## Verification

After flashing your compiled firmware to the router:

1. SSH into your router
2. Check the file exists:
   ```bash
   ls -lh /lib/firmware/ath11k/QCN9074/hw1.0/board-2.bin
   ```
3. Verify it's your vendor file by checking the file size or checksum
4. Check dmesg for ath11k firmware loading messages:
   ```bash
   dmesg | grep ath11k
   ```

## Troubleshooting

### WiFi not working after installation

1. Ensure you kept the ath11k driver packages selected
2. Verify your vendor board-2.bin file is compatible with your hardware
3. Check `dmesg` for firmware loading errors

### Package not appearing in menuconfig

1. Update package feeds: `./scripts/feeds update -a && ./scripts/feeds install -a`
2. Verify package is in `package/firmware/bidhatawrt-boardbin-qcn9074/`
3. Ensure Makefile syntax is correct

### Build errors

Run with verbose output to see detailed errors:
```bash
make package/bidhatawrt-boardbin-qcn9074/compile V=s
```

Common issues:
- Missing board-2.bin file in `files/` directory
- Incorrect file permissions (should be readable)

## License

This package is licensed under GPL-2.0. See LICENSE file for details.

## Repository

Full source and documentation available at:
https://github.com/bidhata/xiaomi_qualcomm_boardbin

## Support

For issues and support:
- GitHub Issues: https://github.com/bidhata/xiaomi_qualcomm_boardbin/issues
- Email: me@krishnendu.com
