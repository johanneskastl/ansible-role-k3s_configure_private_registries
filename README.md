k3s_configure_private_registries
=========

Configure k3s to use a private registry via the registries.yaml file

Requirements
------------

A node running k3s, this can be either a server or agent node.

Role Variables
--------------

- `node_type`: (default: `server`) Type of the node, can be either `server` or `agent`
- `mirrored_registries`: a list of dicts containing the information for each of the private registries
  - `name`: the name of the mirrored registry
  - `endpoint` the endpoint to use for mirroring

Dependencies
------------

None

Example Playbook
----------------

```
- hosts: servers
  roles:
    - role: 'johanneskastl.k3s_configure_private_registries'
      vars:
        mirrored_registries:
          - name: 'docker.io'
            endpoint: 'http://my-private-registry.example.com:5000'
          - name: 'quay.io'
            endpoint: 'http://my-private-registry.example.com:5000'
          - name: 'ghcr.io'
            endpoint: 'http://my-private-registry.example.com:5000'
```

License
-------

BSD-3-Clause

Author Information
------------------

I am Johannes Kastl, reachable via kastl@b1-systems.de.
