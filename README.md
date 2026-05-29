# Nexus Maven Artifact Publisher

Automates the promotion of Java artifacts from local development environments
to the team's Nexus Maven repository, eliminating manual uploads and ensuring
every release is versioned, traceable, and available to the wider team.

## Setup

1. Create your vault file with Nexus credentials:
```bash
ansible-vault create vault.yml
```

2. Add the following to the vault file:
```yaml
nexus_password: "yourpassword"
```

3. Update `push-artifact.yml` vars with your Nexus URL and username.

## Usage

```bash
ansible-playbook push-artifact.yml  \
    -e "jar_file=./my-app.jar" \
    -e "artifact_id=my-app" \
    -e "version=1.0.0" \
    --ask-vault-pass \
    --extra-vars "@vault.yml"
```

## Security
Nexus credentials are stored in `vault.yml`, encrypted with Ansible Vault.
`vault.yml` is listed in `.gitignore` and must never be committed unencrypted.