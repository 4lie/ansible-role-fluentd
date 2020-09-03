# Fluentd Ansible Role

Fluentd is an open source data collector for unified logging layer.

## Installation

``` yaml
# requirments.yaml
- src: git@github.com:4lie/ansible-role-fluentd.git
  scm: git
  version: master
  name: fluentd
```

## Role Variables

``` yaml
# Worker count
fluentd_worker_count: 1

# Paths to custom configuration templates
fluentd_custom_conf: []

# Fluentd plugins that you want to install
fluentd_plugins: []
  # - { url: "https://raw.githubusercontent.com/emsearcy/fluent-plugin-gelf/master/lib/fluent/plugin/out_gelf.rb" }
  # - { name: "fluent-plugin-secure-forward", 'version': 0.2.3 }
```

## Example Playbook

``` yaml
- hosts: servers
  roles:
    - fluentd
```
