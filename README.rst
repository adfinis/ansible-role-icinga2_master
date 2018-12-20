===================
ROLE ICINGA2_MASTER
===================

.. image:: https://img.shields.io/github/license/adfinis-sygroup/ansible-role-icinga2_master.svg?style=flat-square
  :target: https://github.com/adfinis-sygroup/ansible-role-icinga2_master/blob/master/LICENSE

.. image:: https://img.shields.io/travis/adfinis-sygroup/ansible-role-icinga2_master.svg?style=flat-square
  :target: https://travis-ci.org/adfinis-sygroup/ansible-role-icinga2_master

.. image:: https://img.shields.io/badge/galaxy-adfinis--sygroup.icinga2_master-660198.svg?style=flat-square
  :target: https://galaxy.ansible.com/adfinis-sygroup/icinga2_master

This role configures icinga2 to act as a master.
Furthermore, this role takes care of the configuration for all clients.


Requirements
=============

Any pre-requisites that may not be covered by Ansible itself or the role
should be mentioned here. For instance, if the role uses the EC2 module, it
may be a good idea to mention in this section that the boto package is required.


Role Variables
===============

.. code-block:: yaml

  # The icinga2 master zone
  icinga2_master_master_zone: monitoring-master

  # A list of all icinga2 api users
  icinga2_master_api_users: []
  #  - username: root
  #    password: "passw0rd"
  #    permissions: "*"
  #  - username: token-generator
  #    password: "passw0rd"
  #    permissions: "actions/generate-ticket"


Dependencies
=============

This role depends on the role `adfinis-sygroup.icinga2_agent 
<https://galaxy.ansible.com/adfinis-sygroup/icinga2_agent>`_, which installs
the icinga2 binary.

Example Playbook
=================


.. code-block:: yaml

  - hosts: monitoring-master
    roles:
       - { role: adfinis-sygroup.icinga2_agent }
       - { role: adfinis-sygroup.icinga2_master }


License
========

`GPL-3.0 <https://github.com/adfinis-sygroup/ansible-role-icinga2_master/blob/master/LICENSE>`_


Author Information
===================

icinga2_master role was written by:

* Adfinis SyGroup AG | `Website <https://www.adfinis-sygroup.ch/>`_ | `Twitter <https://twitter.com/adfinissygroup>`_ | `GitHub <https://github.com/adfinis-sygroup>`_
