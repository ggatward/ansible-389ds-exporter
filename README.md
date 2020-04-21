# Ansible Role: 389ds_exporter

## Description

Deploy prometheus [389ds_exporter](https://github.com/terrycain/389ds_exporter) using ansible.

## Requirements

- Ansible >= 2.9 (It might work on previous versions, but we cannot guarantee it)

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `ldap_389ds_exporter_version` | 0.1.2 | 389ds_exporter package version |
| `ldap_389ds_exporter_web_listen_address` | "0.0.0.0:9496" | Address on which 389ds_exporter will listen |


| `ldap_389ds_scrape_address` | localhost:389 | Address of the 389ds LDAP instance |
| `ldap_389ds_user` | cn=DirectoryManager | User to access 389ds |
| `ldap_389ds_password` | 'ChangeMe' | Password of the user accessing 389ds |
| `ldap_389ds_ipa_domain` | example.org | IPA domain to query |
| `ldap_389ds_scrape_interval` | 1m | How often to poll LDAP for data |
| `ldap_389ds_exporter_config_flags_extra` | {} | Additional configuration flags passed at startup to 389ds_exporter binary |


## Example

### Playbook

Use it in a playbook as follows:
```yaml
- hosts: all
  roles:
    - 389ds_exporter
  vars:
    ldap_389ds_ipa_domain: ipa.example.com
    ldap_389ds_password: 'Itsa$ecret'
```
