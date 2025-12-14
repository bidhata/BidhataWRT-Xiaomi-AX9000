# 📡 BidhataWrt for Xiaomi AX9000

> Custom board-2.bin firmware package for Qualcomm QCN9074 WiFi chipset in OpenWrt and Fan Working as well

[![License: GPL v2](https://img.shields.io/badge/License-GPL%20v2-blue.svg)](https://www.gnu.org/licenses/old-licenses/gpl-2.0.en.html)
[![OpenWrt](https://img.shields.io/badge/OpenWrt-Compatible-00B5E2?logo=openwrt)](https://openwrt.org/)
[![Platform](https://img.shields.io/badge/Platform-All%20Targets-green)](https://github.com/bidhata/xiaomi_qualcomm_boardbin)

---

## 📖 Overview

BidhataWRT for Xiaomi AX9000 based on ImmortalWRT with vendor board-2.bin file, QCN9074 160 Mhz working, Fan working including monitoring 

---

## 👤 Maintainer

**Krishnendu Paul**

- 📧 Email: [me@krishnendu.com](mailto:me@krishnendu.com)
- 🌐 Website: [krishnendu.com](https://krishnendu.com)
- 💻 GitHub: [@bidhata](https://github.com/bidhata)
- 📦 Repository: [BidhataWRT for AX900](https://github.com/bidhata/BidhataWRT-Xiaomi-AX9000))

---

## 🚀 Quick Start

### Prerequisites

- OpenWrt build environment set up
- Downloaded bidhatawrt-ax9000.tgz

### Installation Steps
```bash
cd /path/to/openwrt/package/firmware/bidhatawrt-boardbin-qcn9074

# Remove placeholder
rm files/lib/firmware/ath11k/QCN9074/hw1.0/board-2.bin

# Copy your vendor file
cp /path/to/your/vendor/board-2.bin files/lib/firmware/ath11k/QCN9074/hw1.0/


#### 4️⃣ Build Firmware

```bas

# Or build complete firmware
make image PROFILE=xiaomi_ax9000 PACKAGES="ath11k-firmware-ipq8074 automount base-files ca-bundle cpufreq dnsmasq-full dropbear firewall4 fstools kmod-ath11k-ahb kmod-gpio-button-hotplug kmod-leds-gpio kmod-nft-offload kmod-phy-aquantia kmod-qca-nss-dp kmod-usb-dwc3 kmod-usb-dwc3-qcom kmod-usb3 libc libgcc libustream-openssl logd losetup mtd netifd nftables ppp ppp-mod-pppoe procd-ujail uboot-envtools uci uclient-fetch urandom-seed urngd wpad-openssl ipq-wifi-xiaomi_ax9000 kmod-ath11k-pci ath11k-firmware-qcn9074 kmod-ath10k-ct ath10k-firmware-qca9887-ct kmod-hwmon-core kmod-thermal kmod-regmap-i2c kmod-i2c-core kmod-regmap-core kmod-hwmon-emc2305 i2c-tools luci-nginx luci-lua-runtime luci-compat luci-app-upnp sed nano luci-app-ksmbd relayd kmod-tcp-bbr luci-theme-argon alpine-fan-control luci-app-alpine-fan-control -luci-app-attendedsysupgrade" FILES="files"

```

---

## ⚠️ Important Notes


## ✅ Activation

After flashing your compiled firmware to the router:

REBOOT once.

---


## 📄 License

This package is licensed under **GNU General Public License v2.0**.

See the [LICENSE](LICENSE) file for full details.

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit issues and pull requests.

### How to Contribute

1. 🍴 Fork the repository
2. 🌿 Create a feature branch (`git checkout -b feature/amazing-feature`)
3. 💾 Commit your changes (`git commit -m 'Add amazing feature'`)
4. 📤 Push to the branch (`git push origin feature/amazing-feature`)
5. 🔀 Open a Pull Request

---

--

## 🔗 Related Links

- [OpenWrt Official Website](https://openwrt.org/)
- [OpenWrt Package Development Guide](https://openwrt.org/docs/guide-developer/packages)
- [QCN9074 Chipset Information](https://www.qualcomm.com/)
- [ath11k Driver Documentation](https://wireless.wiki.kernel.org/en/users/drivers/ath11k)

---

<div align="center">

**Made with ❤️ by [Krishnendu Paul](https://krishnendu.com)**

⭐ Star this repository if you find it helpful!

</div>

