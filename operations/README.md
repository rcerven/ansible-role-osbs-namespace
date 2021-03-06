ansible-role-osbs-namespace/operations
======================================

Collection of common maintenance operations for an OpenShift cluster.
By default, all tasks in this sub-roles are disabled. Use the control
booleans to enable the desired operations:

Requirements
------------

A running instance of OpenShift.

Role Variables
--------------


    # Update docker daemon on each OpenShift node.
    # It's highly recommended to use `serial: 1` in your playbook.
    osbs_upgrade_docker: false
    # Docker version to update to.
    osbs_docker_version: <default not set>

See `operations/defaults/main.yml` for a comprehensive list of all
available variables.

Dependencies
------------

None.

Example Playbook
----------------

    - name: update docker
      hosts: nodes
      roles:
         - role: ansible-role-osbs-namespace/operations
           osbs_upgrade_docker: true
           osbs_docker_version: docker-1.12.6-61.git85d7426.el7

License
-------

BSD

Author Information
------------------

Luiz Carvalho <lui@redhat.com>
