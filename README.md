# ansible-rabbitmq
[![Build Status](https://travis-ci.org/jimbydamonk/ansible-rabbitmq.svg?branch=master)](https://travis-ci.org/jimbydamonk/ansible-rabbitmq)

Install and configure rabbitmq.

Requirements
------------

NA

Role Variables
--------------

The default variables for this role are listed below. They are defined in defaults/main.yml`.

```yml
---
rabbitmq_plugins:
  - rabbitmq_management
  - rabbitmq_shovel
  - rabbitmq_shovel_management
rabbitmq_version: 3.6.3-1

erlang_version: 18.3
erlang_cookie_file: "/var/lib/rabbitmq/.erlang.cookie"
erlang_cookie_data: "ERLANGCOOKIE"
mnesia_base: "/var/lib//rabbitmq/mnesia"
rabbitmq_reverse_dns_lookups: true
rabbitmq_cluster_partition_handling: "pause_minority"
# can be on of: pause_minority {pause_if_all_down, [nodes], ignore | autoheal}, autoheal

rabbitmq_management_load_json: true
rabbitmq_management_json: "/etc/rabbitmq/rabbitmq_defs.json"

rabbitmq_clusterer: false
rabbitmq_clusterer_config_file: "/etc/rabbitmq/rabbitmq_clusterer.config"
rabbitmq_permission: []
rabbitmq_polices: []
rabbitmq_users: []
rabbitmq_vhosts: []

rabbitmq_ssl: false
rabbitmq_ssl_port: 5671
rabbitmq_ssl_cacert: ""
rabbitmq_ssl_cert: ""
rabbitmq_ssl_key: ""
rabbitmq_ssl_verify: "verify_peer"
rabbitmq_ssl_fail_if_no_peer_cert: false
```

Dependencies
------------

None

Example Playbook
----------------

Simple Playbook:

    - hosts: servers
      roles:
        - ansible-rabbitmq


License
-------

Apache

Author Information
------------------
Mike Buzzetti
