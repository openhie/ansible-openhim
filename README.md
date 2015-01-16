Role Name
========

ansible-openhim

Role Variables
--------------
```

#### Defaults for OpenHIM core
# These values may be overridden in plays/vars/etc..
# http://docs.ansible.com/playbooks_variables.html#variable-precedence-where-should-i-put-a-variable
#
openhim_dir: "/opt/openhim"
openhim_user: "openhim"

### OpenHIM Install Options ###
# Three options are below.
# By default a released version will be installed.
# If you want to install a version you have compiled and the archive is on the same machine
# you are runnig ansible from change openhim_deploy_local to true and set the location in the
# openhim_archive_loc variable.
# If you want to install the latest version from master change openhim_git_branch to master
#
# This will deploy a tar.gz of openhim that is on the same machine as ansible is running.
# Set the location of the archive using the openhim_archive_loc var.
openhim_deploy_local: false
openhim_archive_loc:

# This will install a released version of openhim
openhim_version: 1.0.0

# This will install openhim from git.  Use a branch name such as master to install the latest version.
# Leave blank to install a released version.
openhim_git_branch:

#### Defaults for OpenHIM xds-mediator
openhim_mule_version: 3.5.0
# Version of the xds-mediator to download
openhim_xds_version: 0.3.0
# URL to download xds-mediator (This should change to the offical github repo on release)
openhim_xds_url: "http://dev.ohie.org/files/openhie-xds-mediator-{{openhim_xds_version}}-SNAPSHOT.zip"
openhim_mule_url: "https://repository.mulesoft.org/nexus/content/repositories/releases/org/mule/distributions/mule-standalone/{{openhim_mule_version}}/mule-standalone-{{openhim_mule_version}}.tar.gz"
# Base directory for mule
openhim_mule_dir: /opt

#### Defaults for nodejs install
node_arch: "x64"
nodejs_version: "0.11.13"
nodejs_version_tag: "v{{nodejs_version}}"
nodejs_file_tag: "node-{{nodejs_version_tag}}"
nodejs_file_name: "{{nodejs_file_tag}}-linux-{{node_arch}}.tar.gz"
nodejs_base_url: "http://nodejs.org/dist/v{{nodejs_version}}/"
nodejs_tarball_url: "{{nodejs_base_url}}{{nodejs_file_name}}"
nodejs_shasum_url: "{{nodejs_base_url}}SHASUMS.txt"
nodejs_path: "/usr/local"

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
    openhim_git_branch: master


```

License
-------

Apache 2.0

Author Information
------------------

Ryan Yates
