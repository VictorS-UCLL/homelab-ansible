# homelab-ansible

Ansible playbooks and roles for managing a self-hosted Proxmox + K3s homelab.

## Infrastructure
- `ansible-control` (192.168.0.138) — Ansible control node
- `k3s-main` (192.168.0.137) — K3s single-node cluster

## Usage
```bash
ansible -i inventory/hosts.yml all -m ping
ansible-playbook -i inventory/hosts.yml playbooks/<name>.yml
```

## Playbooks
| Playbook | Purpose |
|----------|---------|
| baseline.yml | VM baseline configuration |
| proxmox_snapshots.yml | Automated Proxmox snapshot management |
