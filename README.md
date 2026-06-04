# Ansible

Personal sandbox for learning Ansible — a collection of small, self-contained projects, each exploring a different feature.

## Projects

| Directory | What it covers |
| --- | --- |
| [`first-playbook/`](first-playbook/) | A single playbook that installs Apache and copies an `index.html` to a remote host. |
| [`first-role/`](first-role/) | Refactors the Apache setup into a custom role (`httpd`) called from `entrypoint.yml`. |
| [`first-galaxy/`](first-galaxy/) | Uses a role pulled from Ansible Galaxy (`aavanish.docker`) instead of a hand-written one. |
| [`first-project/`](first-project/) | A multi-role playbook (app + nginx + db) using `group_vars/` and an Ansible Vault for secrets. |
| [`digital-ocean/`](digital-ocean/) | Provisions a DigitalOcean droplet locally via the `create-droplet` role. |

## Running a playbook

Each project is independent. From inside the project directory:

```bash
ansible-playbook -i inventory.ini playbook.yml
```

`first-project/` uses Ansible Vault, so it needs:

```bash
ansible-playbook -i inventory.ini playbook.yaml --ask-vault-pass
```

## Notes

- `passwords.txt` and vault password files are gitignored — never commit secrets.
- Inventories point at hosts that exist (or existed) in my own environment; update `inventory.ini` before running anything.
