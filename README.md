# Enterprise Monitoring & Security Patch Rollout

## Project Overview
This project demonstrates enterprise-level automation of Linux monitoring and security patch management using Ansible and Prometheus Node Exporter across multi-environment infrastructure.

The solution ensures standardized monitoring deployment and automated security patching across Debian and RedHat-based systems.

---

## Objectives

- Deploy Prometheus Node Exporter across multiple Linux hosts
- Automate security patching for Debian and RedHat systems
- Configure scheduled patch execution using cron
- Maintain idempotent Infrastructure-as-Code standards

---

## Architecture

- Multi-environment inventory (dev, qa, uat, prod)
- Automated monitoring agent deployment
- Cross-platform package management
- Systemd service validation
- Scheduled patching configuration

---

## Playbooks

### deploy.yml
- Installs Prometheus Node Exporter
- Creates dedicated service user
- Configures and enables systemd service
- Validates service status

### server_patching.yml
- Handles apt and yum-based updates
- Configures unattended upgrades (Debian)
- Schedules recurring patch jobs via cron
- Logs patch execution results

### inv.yml
- Defines multi-environment host groups
- Standardizes deployment targeting

---

## Key Skills Demonstrated

- Infrastructure as Code (IaC)
- Cross-platform Linux automation
- Configuration management using Ansible
- Service orchestration with systemd
- Security patch lifecycle management

---

## Future Enhancements

- Prometheus server integration
- Alertmanager configuration
- Centralized logging integration
- Terraform-based infrastructure provisioning
- ---

## How to Execute

Run Node Exporter deployment:

```bash
ansible-playbook -i ansible/inv.yml ansible/deploy.yml
```

Run security patching:

```bash
ansible-playbook -i ansible/inv.yml ansible/server_patching.yml
```
