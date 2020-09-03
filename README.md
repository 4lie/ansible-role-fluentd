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
fluentd_sources_conf: []
# fluentd_sources_conf:
#   - "type": forward
#     "params":
#       "port": 24224
#       "bind": 0.0.0.0
#   - "type": dummy
#     "params":
#       "dummy": "{\"hello\":\"world\"}"
#       "tag": testi
#   - "type": exec
#     "params":
#       "command": cmd arg arg
#       "parse":
#         "keys": k1 k2 k3
#       "extract":
#         "tag_key": k1
#         "time_key": k2
#         "time_format": "%Y-%m-%d %H:%M:%S"
#       "run_interval": 10s

fluentd_outputs_conf: []
# fluentd_outputs_conf:
#   - "type": file
#     "tag": "app.*"
#     "params":
#       "path": /tmp/myapp_log
#       "compress": gzip
#       "buffer":
#         "timekey": 1d
#         "timekey_use_utc": true
#         "timekey_wait": 10m
#   - "type": copy
#     "tag": "*"
#     "params":
#       "store":
#         - "type": file
#           "path": /tmp/myapp
#           "compress": gzip
#           "format":
#             "localtime": false
#           "buffer":
#             "timekey_wait": 10m
#             "timekey": 86400
#             "timekey_use_utc": true
#             "path": /tmp/myapp
#           "inject":
#           "time_format": "%Y-%m-%d %H:%M:%S"
#           "localtime": false
#         - "type": elasticsearch
#           "host": fluentd
#           "port": 9200
#           "index_name": fluentd
#           "type_name": fluentd

fluentd_filters_conf: []
# fluentd_filters_conf:
#   - "type": grep
#     "tag": foo.bar
#     "params":
#       "regexp":
#         - "key": message
#           "pattern": /cool/
#         - "key": hostname
#           "pattern": /^web\d+\.example\.com$/
#       "exclude":
#         "key": message
#         "pattern": uncool

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
