# 🤖 Infrastructure Automation & Monitoring with Ansible, Prometheus, and Grafana

This project is a comprehensive 4-phase journey into automating and monitoring IT server infrastructure using **Ansible**, **Prometheus**, and **Grafana**. It simulates real-world DevOps practices across multiple virtual machines, aiming to reduce manual overhead and improve system observability.

---

## 🧩 Phase 1: Foundation & Playbooks
**Goal**: Automate basic system admin tasks on a single VM using Ansible.

### ✅ Highlights:
- Setup of a dedicated Ansible user with SSH key-based access
- Created modular role-based Ansible structure
- Automated tasks:
  - Displaying custom MOTD
  - Installing packages (e.g., `tmux`)
  - Performing system updates
  - Installing services like `vsftpd`
  - Creating new users (e.g., `ftp_user`)

---

## 🌐 Phase 2: Multi-VM Management
**Goal**: Expand automation to manage a small company's infrastructure with multiple VMs (dev & ops).

### ✅ Highlights:
- Managed 3 VMs from a single control node
- Created a role to automate the creation of the Ansible service user
- Common configurations:
  - Set timezone
  - Configure custom MOTD and /etc/hosts
  - Install essential tools (e.g., `vim`, `tar`)
- Dev & Ops specific roles:
  - Dev: Created multiple users (`jodd`, `lisa`, `stev`) with SSH keys, installed developer tools
  - Ops: Installed `nginx`, deployed a static website, managed firewall with UFW

---

## 📊 Phase 3: Monitoring with Prometheus
**Goal**: Deploy and configure Prometheus and Node Exporter for system metrics collection.

### ✅ Highlights:
- Installed Prometheus using Ansible as a systemd service
- Configured dynamic targets using Jinja2 templating
- Installed Node Exporter manually (control node) and via Ansible (vm1 & vm2)
- Opened appropriate firewall ports (9090, 9100)
- Prometheus configured to scrape all nodes for:
  - Disk usage
  - Memory
  - Uptime
- Custom PromQL queries for disk %, RAM free, and uptime (validated using CLI tools like `df`, `free`, and `uptime`)

---

## 📈 Phase 4: Visualization with Grafana
**Goal**: Create real-time dashboards to visualize metrics using Grafana.

### ✅ Highlights:
- Installed and configured Grafana on control node
- Integrated Prometheus as a data source
- Opened firewall for Grafana web interface (port 3000)
- Designed a custom dashboard with panels for:
  - Disk, RAM, Swap, CPU, Network, Power, and Uptime
- Delivered a presentation with:
  - One slide per panel
  - Query logic
  - Justifications and visual design rationale

---

## 📂 Project Structure
```
automation-project/
├── phase1/
│   └── first-playbook/         # Single VM automation tasks
├── phase2/
│   └── second-playbook/        # Multi-VM ops/dev setup
├── phase3/
│   └── prometheus-node/        # Monitoring with Prometheus
├── phase4/
│   └── grafana-dashboard/      # Visual dashboards and PDFs
└── README.md
```

---

## 🛠️ Tools & Technologies
- **Ansible** (roles, playbooks, modules, templating)
- **Prometheus** (metrics collection)
- **Node Exporter** (system metrics)
- **Grafana** (visualization)
- **UFW** (firewall)
- **Linux systemd services**

---

## 🎯 Outcomes
- Real-world simulation of IT operations & DevOps workflows
- Mastery in Ansible automation and modular role design
- Monitoring setup from scratch using open-source tools
- Visualization of system health through Grafana dashboards

---

## 📄 License
This project is open-source and licensed under the [MIT License](LICENSE).

---

Made with 💡 by Yash Prajapati — Automation Enthusiast | DevOps Explorer
