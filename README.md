# Marge-bot Helm Chart
Marge-bot is a merge-bot for GitLab

See [smarkets/marge-bot](https://github.com/smarkets/marge-bot) for more project details.

## Chart Details

This chart uses env vars from [values.yaml](values.yaml) of helm chart.

Marge-bot version listed in the [Chart.yaml](Chart.yaml)

## Installing the Marge-bot Helm Chart

### Inline
```bash
$ helm repo add stable https://
$ helm install <RELEASE_NAME> stable/marge-bot \
 --set "env[0].name=MARGE_GITLAB_URL" --set "env[0].value=<GITLAB_URL>" \
 --set "env[0].name=MARGE_AUTH_TOKEN" --set "env[0].value=<GITLAB_AUTH_TOKEN>"
 --set "env[0].name=MARGE_SSH_KEY" --set "env[0].value=$(cat ssh-key)"
```

### With values file

```bash
$ cat my.values
env:
  - name: MARGE_GITLAB_URL
    value: https://gitlab.com
  - name: MARGE_AUTH_TOKEN
    value: asdfsdkafjkdaf
  - name: MARGE_SSH_KEY
    value: |-
      -----BEGIN RSA PRIVATE KEY-----
$ helm install <RELEASE_NAME> stable/marge-bot -f my.values
```
