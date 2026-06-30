# Changelog

## v2.1.1

### Bug Fixes
- **Fixed spoofing bypass on Android 14+ native games (Resolves #14)**: Added comprehensive `Build.BOARD` and `Build.HARDWARE` spoofing. Games that check the device board via `__system_property_get` or JNI will now correctly see the profile's SoC platform (e.g., `kalama` / `qcom`) instead of the real device's hardware.
- **Fixed `Build$VERSION` spoofing missing**: The module now properly spoofs `Build$VERSION.SDK_INT` and `Build$VERSION.RELEASE` derived from the profile's fingerprint, preventing mismatch detection.
- **Fixed `Build.DISPLAY` extraction**: The fingerprint parsing logic now extracts the correct display string instead of "release-keys", reducing the risk of anti-tamper detection.
- **Fixed incorrect Game Package Names**: Removed fake and incorrect package variants. BGMI is confirmed to only use `com.pubg.imobile`. PUBG Mobile Lite is now correctly mapped to `com.tencent.iglite`. Free Fire is correctly mapped to `com.dts.freefireth` and the incorrect entry was removed.

