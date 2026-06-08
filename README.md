# nyawit

GitHub Actions build for **OpenWrt** firmware targeting the **Linksys EA6350v3**
(`ipq40xx` / `arm_cortex-a7_neon-vfpv4`) with the
[Xiaowit/XModem](https://github.com/Xiaowit/XModem) feed and
**`luci-app-XModem-next`**.

## Build

- Runs automatically on push to `main` (when `ea6350v3.config`,
  `feeds.conf.append`, or the workflow changes).
- Or trigger manually via **Actions → Build OpenWrt (EA6350v3 + XModem) → Run workflow**,
  optionally setting the OpenWrt release tag (default `v25.12.4`).

> Note: OpenWrt `25.10.4` does not exist. The release line is `24.10.x` then
> `25.12.x`; this repo defaults to the latest stable `v25.12.4`. Change the
> `version` input to build another tag (e.g. `v24.10.7`).

## Output

Firmware is published as the `openwrt-ea6350v3-XModem` artifact:

- `*-squashfs-factory.bin` — flash from Linksys stock firmware
- `*-squashfs-sysupgrade.bin` — upgrade from an existing OpenWrt install

## Files

- `.github/workflows/build.yml` — build pipeline
- `feeds.conf.append` — XModem feed line
- `ea6350v3.config` — device + package config seed
