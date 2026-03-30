# Changelog

All notable changes to this add-on will be documented in this file.

The format is based on [Semantic Versioning](https://semver.org/), using
`MAJOR.MINOR.PATCH` version numbers.

---
## [2.2.0] — 2026‑03‑29
### ✨ New Features
- Added Subaru HomeLink RF detector service
- Added unified logging pipeline
- Added full healthcheck coverage for all services

### 🔧 Internal Improvements
- Modernized add‑on structure using rootfs overlay
- Added supervised multi‑service architecture

## [2.1.2] — 2026-03-29
### 🐛 Bug Fixes
- Fix finish script for `rtl_tcp` @mdegat01 (#78)

---

## [2.1.1] — 2026-02-14
### 🔧 Maintenance
- Internal cleanup and documentation updates
- Minor improvements to MQTT handling

---

## [2.1.0] — 2026-01-07
### ✨ Enhancements
- Improved meter parsing reliability
- Updated base images and dependencies

---

## [2.0.0] — 2025-12-01
### 🚀 Major Changes
- Migration to new add-on structure
- Updated rtlamr integration
- Improved MQTT discovery behavior

---

## [1.x.x] — 2021–2024
### 📜 Historical Notes
- Initial releases by original author
- Early support for SCM, SCM+, IDM, NETIDM, R900, and R900BCD
- First MQTT discovery implementation