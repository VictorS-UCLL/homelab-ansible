# homelab-ansible

Ansible playbooks for managing a self-hosted Proxmox + K3s homelab. Control node provisions and configures infrastructure over SSH; designed to make the environment reproducible from scratch.

## Infrastructure

| Host | IP | Role |
|------|-----|------|
| `ansible-control` | 192.168.0.138 | Ansible control node |
| `k3s-main` | 192.168.0.137 | K3s single-node cluster |

## Usage

```bash
# Verify connectivity to all managed hosts
ansible -i inventory/hosts.yml all -m ping

# Run a playbook
ansible-playbook -i inventory/hosts.yml playbooks/<name>.yml
```

## Playbooks

| Playbook | Purpose | Status |
|----------|---------|--------|
| `baseline.yml` | VM baseline config (packages, SSH hardening, services) | planned |
| `proxmox_snapshots.yml` | Automated Proxmox snapshot pruning | planned |

## Structure

```
homelab-ansible/
├── inventory/hosts.yml     # Managed host definitions
├── group_vars/all.yml      # Shared connection variables
├── playbooks/              # Task playbooks
└── roles/                  # Reusable role definitions
```
