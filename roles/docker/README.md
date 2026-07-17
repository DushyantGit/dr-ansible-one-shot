# Docker Role

Installs and configures Docker across Ubuntu, RHEL, and Amazon Linux.

## What it does
- Installs Docker using the appropriate method per OS family
- Starts and enables the Docker service
- Optionally adds users to the docker group

## Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `docker_users` | `[]` | Users to add to the docker group |
| `docker_service_enabled` | `true` | Enable Docker on boot |

## Usage

```yaml
- hosts: all
  become: true
  roles:
    - role: docker
      docker_users:
        - ubuntu
```

## Supported OS
- Ubuntu (docker.io via apt)
- RHEL 9 (docker via dnf)
- Amazon Linux 2023 (docker via dnf)
