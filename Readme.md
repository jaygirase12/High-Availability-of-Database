# High-Availability of Database (24/7 HA Database Access Cluster)

## Overview
An Active-Passive High-Availability (HA) database access cluster built using **Keepalived (VRRP)**, **Python Flask**, **Systemd**, and **MySQL 8.0** over a **VMware Host-Only (`VMnet1`)** network (`192.168.100.0/24`).

* **Windows Host (`192.168.100.20`):** Runs centralized MySQL 8.0 (`ha_enterprise_db` on TCP port `3306`) and Windows Firewall configuration.
* **Kali-Server1-Primary (`192.168.100.11`):** Keepalived `MASTER` (priority `100`) running `ha_app.service` on port `5000`.
* **Kali-Server2-Backup (`192.168.100.12`):** Keepalived `BACKUP` (priority `90`) running `ha_app.service` on port `5000`.
* **Virtual IP (`192.168.100.100`):** Floating VIP providing automatic failover in ~3–4 seconds and automatic failback with zero data loss.

## Repository Contents
* `docs/` — Project documentation and report files.
* `screenshots/` — Step-by-step configuration, service, and failover/failback screenshots.
* `README.md` — Project summary and repository guide.