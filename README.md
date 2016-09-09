ETCD
=========

Install etcd using ansible, Ubuntu 14.04 only!

This role install etcd by copying release tar file into remote nodes,
unpack it and do some configuration.

That's it!

Requirements
------------

None

Role Variables
--------------

TODO: add usage!

- etcd_release_dir: place to store the release tar, example: `./releases/etcd`
- etcd_version: etcd version, example: `3.0.7`,
  then the file `etcd-v3.0.7-linux-amd64.tar.gz` should be in dir `./releases/etcd`.
- etcd_bin_dir: where to put the `etcd` into, default to `/usr/bin`.
- etcd_conf_dir: where the etcd config file will comes to.
- etcd_data_dir: where etcd store data.
- etcd_client_port: default 2379
- etcd_peer_port: default 2380
- etcd_peers_group: group name of servers to install etcd. default to `etcd`
- etcd_url_scheme: http
- etcd_peer_url_scheme: http
- etcd_interface: default to "{{ ansible_default_ipv4.interface }}".

Dependencies
------------

None

Example Playbook
----------------
Example:

    - hosts: etcd
      roles:
         - role: etcd
           etcd_peers_group: etcd


**NOTES**

When using vagrant and virtualbox, the `etcd_interface` should be set
to `eth1`.

License
-------

MIT
