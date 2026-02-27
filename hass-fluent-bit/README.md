# Alvin's Home Assistant Apps

A curated collection of Home Assistant apps maintained by Alvin Chen.  
This repository includes custom builds, upstream‑synced components, and operational tooling used in my Home Assistant environment.

## 📦 Available apps

### **AMR2MQTT**
Advanced Meter Reader → MQTT bridge  
- Source: https://github.com/alvinchen1/hassio-addons/tree/main/amr2mqtt  
- Based on upstream `mdegat01/amr2mqtt`  
- Provides real‑time meter decoding and MQTT publishing

### **Portainer CE**
Container management UI for Home Assistant OS  
- Source: https://github.com/alvinchen1/hassio-addons/tree/main/hass-portainer  
- Custom‑maintained build  
- Useful for debugging, container inspection, and advanced HAOS workflows

### **Fluent Bit**
High‑performance log processor and forwarder  
- Source: https://github.com/alvinchen1/hassio-addons/tree/main/fluent-bit  
- Ideal for structured logging, log shipping, and HA observability pipelines

---

## 🛠️ Installation

Add this repository to Home Assistant:

 https://github.com/alvinchen1/hassio-addons

Then install any add-on from the Add-on Store.

---

## 🧭 Maintainer

**Alvin Chen**  
GitHub: https://github.com/alvinchen1

---

## 📝 Notes

- All add-ons are built for multi‑arch compatibility (amd64/armv7/aarch64)  
- Each add-on includes its own `config.yaml`, Dockerfile, and documentation  
- Contributions or issues are welcome