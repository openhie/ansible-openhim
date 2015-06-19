ansible-openhim
========
This roles installs [openhim-core](https://github.com/jembi/openhim-core-js) and optionally [openhim-mediator-xds](https://github.com/jembi/openhim-mediator-xds).  You will also probably want to combine [ansible-openhim-console](https://github.com/yatesr/ansible-openhim-console) role to be able to use the web console. 


Role Variables
--------------
```

#### Defaults for OpenHIM core

#### Defaults for OpenHIM xds-mediator
# Install openhim-xds-mediator
openhim_xds_mediator_install: true
# Version of the xds-mediator to download
openhim_xds_version: 1.0.2
# URL to download xds-mediator (This should change to the offical github repo on release)
openhim_xds_url: "https://github.com/jembi/openhim-mediator-xds/releases/download/v{{openhim_xds_version}}/openhim-mediator-xds-{{openhim_xds_version}}.tar.gz"
# User to run as
openhim_xds_user: openhim_xds
# Directory to install to
openhim_xds_dir: /opt/openhim-mediator-xds
# URL to download xds-mediator config
openhim_xds_config_url: "https://raw.githubusercontent.com/jembi/openhim-mediator-xds/master/src/main/resources/mediator.properties"

```

Example Playbook
-------------------------
### playbook.yml

```

---
- hosts: all
  roles:
  - ansible-openhim

  vars:
   openhim_xds_version: 1.0.2

```

License
-------

Apache 2.0

Author Information
------------------

Ryan Yates
