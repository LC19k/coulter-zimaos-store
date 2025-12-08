# Apps Folder

This folder contains custom manifests for ZimaOS App Store.

Included apps:
- **Keycloak**: Identity and SSO provider
- **PostgreSQL**: Backend database for Keycloak
- **Samba AD DC**: Windows-native Kerberos/LDAP domain controller

All apps are designed for household clarity:
- Backend VLAN 83 (10.0.83.0/24) for inter-container traffic
- Frontend LAN (10.0.0.0/22) for user-facing GUIs
