# Contributing to Coulter ZimaOS Store

This store is designed for household clarity, beginner-safe onboarding, and forensic consistency.  
Contributions should follow the conventions below so every app feels narratable and predictable.

---

## 🗂 Folder Structure
- Place all app manifests in the `Apps/` folder.
- Each manifest filename must match the app `id` (e.g., `keycloak.json` → `"id": "keycloak"`).
- Update `index.json` to include new apps with categories, version, and maintainer info.

---

## 🔖 Manifest Conventions
- **Networks**: Use VLAN names from the household VLAN table (`Backend`, `Infrastructure`, `Media`, etc.).
- **MAC Addresses**: Follow the convention `52:42:00:Device:VLAN:ID`
  - `Device` → `01` for Unraid, `02` for ZimaOS
  - `VLAN` → decimal VLAN ID (e.g., `23`, not hex)
  - `ID` → user-readable device number (e.g., `01`, `02`)
- **Persistence**: Always mount volumes under `/DATA/AppData/<appname>/...` for clarity and backups.
- **Healthchecks**: Include a `healthcheck` block to ensure services are ready before dependents start.

---

## 🗂 Categories
Use categories to group apps in the App Store UI:
- **Identity & Security** → Keycloak, LDAP, SSO
- **Directory Services** → Samba AD DC
- **Database & Backend** → PostgreSQL, MySQL
- **Observability** → Prometheus, Grafana
- **Media** → Jellyfin, Lidarr, Radarr
- **IoT** → Home Assistant, Zigbee2MQTT

---

## 🔖 Versioning
- Start at `1.0.0` for new apps.
- Increment **minor** version for configuration changes (networks, MACs, healthchecks).
- Increment **major** version for breaking changes (new database versions, incompatible configs).

---

## 👤 Maintainer
All apps should list `"maintainer": "Lawrence Household"` unless explicitly delegated.  
This ensures household members know the source of each manifest.

---

## 🛠 How to Add a New App
1. Create a manifest in `Apps/` (e.g., `Apps/jellyfin.json`).
2. Add the app entry to `index.json` with categories, version, and maintainer.
3. Test the manifest locally in ZimaOS.
4. Commit changes with a clear message:
   git commit -m "Add Jellyfin manifest (Media VLAN 34)
5. Push to the repo so it appears in the household App Store.

---

## 🎭 Household Narrative
Every contribution should be narratable:
- VLAN names and MACs tell the story of where the app lives.
- Categories make browsing intuitive.
- Versioning makes upgrades predictable.
- Healthchecks prevent race conditions.

This way, anyone in the household can confidently install, update, or troubleshoot apps without CLI anxiety.
