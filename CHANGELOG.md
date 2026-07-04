# Changelog

All notable changes to this integration are documented here.
This project adheres to [Semantic Versioning](https://semver.org/).

## 1.1.1 — 2026-07-04

### Fixed
- **Energy sensor**: use the most recent metering bucket rather than the highest
  value, so the reading stays correct after the unit's power logging is reset.

## 1.1.0 — 2026-07-04

### Added
- ⚡ **Energy sensor (kWh)** on units that meter energy — a cumulative reading
  that plugs straight into the Home Assistant **Energy dashboard**, with counter
  resets handled automatically. Units that only track operating hours are
  unaffected.

## 1.0.1 — 2026-07-04

### Fixed
- **Operating time** sensor now reports **hours** (it was previously shown with
  the wrong scale).

### Added
- `get_power_debug` diagnostic action to read a unit's raw power values — useful
  for figuring out which units actually support energy metering.

## 1.0.0 — 2026-06-15

First stable release. 🎉

### Added
- **Brand icons** shipped with the integration.
- Translations for **all 62** Home Assistant languages.
- Completed the Home Assistant **quality-scale** self-assessment.

## 0.9.1 — 2026-06-15

### Added
- Comprehensive **test suite** (99% coverage), enforced at ≥95% in CI.
- **Quality-scale** work: entity icons, translated error messages, a reconfigure
  flow, and connection-availability handling.
- Strict type-checking (`mypy --strict`) across the integration.

### Fixed
- `set_schedule` now raises a clear validation error on invalid input.
- Provisioning helper: confirms the unit is a DPLUG model first and masks the
  Wi-Fi password.

## 0.8.2 — 2026-06-15

### Fixed
- Config flow: fixed an error in the save-token step.

## 0.8.1 — 2026-06-15

### Added
- The `provision.py` Wi-Fi setup helper is attached to each release for direct
  download.

### Changed
- Simpler, clearer onboarding wizard (WPS/AP instructions); the helper shows the
  unit's MAC and can fall back to the ARP table.

## 0.8.0 — 2026-06-15

### Added
- New device actions: **power-usage history**, **power logging** (on/off/reset),
  **nickname**, and **region code** (read/set).

## 0.7.0 — 2026-06-15

Initial public release.

### Added
- Local **climate** control — power, HVAC modes, target/current temperature, fan
  speed, swing, and presets — with features gated on the unit's capability code.
- Indoor/outdoor temperature, humidity and diagnostic **sensors**.
- **On-device scheduler** services (create/edit/delete on/off schedules that run
  on the module's own clock, even while Home Assistant is offline).
- Guided **config flow** with WPS/token onboarding and DHCP discovery.
