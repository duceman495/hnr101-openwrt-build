# HNR101 ImmortalWrt Cloud Build

Automated GitHub Actions build for **Hisense HNR101** (`qualcommax/ipq807x`) based on [sqliuchang/immortalwrt (`kernel-6.12`)](https://github.com/sqliuchang/immortalwrt/tree/kernel-6.12).

## Included Features
- **Target**: `hisense_hnr101` (`squashfs-factory.bin`, `squashfs-factory.ubi`, `squashfs-sysupgrade.bin`, `initramfs-uImage.itb`)
- **WiFi Calibration**: Pre-populated `/lib/firmware/ath11k/IPQ8074/hw2.0/cal-ahb-c000000.wifi.bin` (131072 bytes, SHA256 `2d9ffc0f895cd808...`)
- **NSS Acceleration**: Full QCA NSS (`NSS_FIRMWARE_VERSION_11_4`, `ATH11K_NSS_SUPPORT`, `ATH11K_NSS_MESH_SUPPORT`, `kmod-qca-nss-drv`, `kmod-qca-nss-ecm`, `kmod-qca-nss-dp`, bridge/vlan/pppoe/qdisc/crypto/mesh)
- **Clashoo**: `clashoo`, `luci-app-clashoo`, `luci-i18n-clashoo-zh-cn` (from `kenzok8/openwrt-clashoo`)
- **QModem & 5G Modem Support**: `qmodem`, `luci-app-qmodem-next` with Generic MHI PCIe + Generic QMI WWAN + MTK T7xx (`kmod-mhi-*`, `kmod-mtk-t7xx`, `kmod-usb-net-*`, `uqmi`, `umbim`)
- **LuCI & Utilities**: `luci-ssl`, Chinese translations (`zh-cn`), `luci-app-ttyd`, `curl`, `htop`, `pciutils`, `usbutils`, `picocom`, `gpiod-tools`

## Layout
- `config/hnr101.config` — Seed `.config` passed through `make defconfig`
- `files/` — Rootfs overlay (`cal-ahb-c000000.wifi.bin`)
- `.github/workflows/build.yml` — GitHub Actions CI build and release workflow
