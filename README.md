Ansible Role: MongoDB Exporter
=========

Install the Prometheus MongoDB exporter.

Requirements
------------

MongoDB installed and operational.

Role Variables
--------------

    # Download location for the prometheus mongodb_exporter tarball file
    mongodb_exporter_tarball: 'https://github.com/percona/mongodb_exporter/releases/download/v2.37.0/mongodb_exporter-2.37.0.linux-amd64.tar.gz'

    # MongoDB URI. By default, listen on IP address used to connect to the host.
    mongodb_exporter_mongodb_uri: mongodb://"{{ ansible_default_ipv4.address }}":27017

Dependencies
------------

None.

Example Playbook
----------------

    # ===========================================================================
    # MongoDB Prometheus exporter
    # ===========================================================================

    - name: Install and configure mongodb prometheus exporters
      hosts: mongo

      vars_files:
        # Ansible vault with all required passwords
        - "../../credentials.yml"

      roles:
        - { role: ansible-role-mongodb_exporter,
            # Download location for the prometheus mongodb_exporter tarball file
            mongodb_exporter_tarball: 'https://github.com/percona/mongodb_exporter/releases/download/v2.37.0/mongodb_exporter-2.37.0.linux-amd64.tar.gz',

            # MongoDB URI. By default, listen on IP address used to connect to the host.
            mongodb_exporter_mongodb_uri: 'mongodb://"{{ ansible_default_ipv4.address }}":27017'
        }

License
-------

MIT

Author Information
------------------

Aaron Patten
aaronpatten@gmail.com
