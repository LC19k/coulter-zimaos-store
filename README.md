# Coulter ZimaOS Store

Custom App Store for ZimaOS, focused on household identity and infrastructure apps.

## 📦 Included Apps
- **Keycloak** (SSO and federation)
- **Samba AD DC** (Windows-native Kerberos/LDAP domain controller)
- **PostgreSQL** (backend database for Keycloak)

## 🗂 Categories
Apps are grouped into categories for clarity:
- **Identity & Security** → Keycloak
- **Directory Services** → Samba AD DC
- **Database & Backend** → PostgreSQL

## 🔖 Versioning
Each app manifest includes a `version` field:
- Starts at `1.0.0` for initial release
- Increment **minor** version for configuration changes (e.g., updated networks, MACs)
- Increment **major** version for breaking changes (e.g., Postgres 18 → 19 upgrade)

This ensures household members know when an app definition has changed and whether updates are safe.

## 👤 Maintainer
All apps are curated and maintained by the **Lawrence Household**.
- Narratable conventions for MAC addresses and VLAN names
- Beginner-safe onboarding flows
- Forensic clarity with persistent logging and healthchecks

## 🛠 Usage
1. Add this repo to ZimaOS App Store (`Settings → Add Store → paste repo URL`).
2. Browse apps by category in the App Store UI.
3. Click **Install** to deploy with household-safe defaults.
4. For dual-homed apps (Keycloak, Samba AD DC), networks are pre-defined and static MACs ensure predictable identity.

## 🎭 Household Narrative
This store is designed so every family member can:
- Recognize apps by name, category, and icon
- Understand version changes at a glance
- Confidently install or update services without CLI anxiety
