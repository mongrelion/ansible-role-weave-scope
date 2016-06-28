[![Build Status](https://travis-ci.org/mongrelion/ansible-role-weave-scope.svg?branch=master)](https://travis-ci.org/mongrelion/ansible-role-weave-scope)

weave scope
=========

Install [Weave Scope](https://www.weave.works/products/weave-scope/)

Requirements
------------

Docker must be installed.

Role Variables
--------------

None

Dependencies
------------

None

Example Playbook
----------------
```
- hosts: servers
  roles:
     - mongrelion.weave-scope
```

And here is an example on how ensure that weave scope is running
```
- hosts: servers
  roles:
    - mongrelion.weave
  tasks:
    - name: check for scope state
      command: docker ps -q -f name=weavescope
      register: check

    - name: ensure scope is running
      command: scope launch
      when: check.stdout_lines | length == 0
```
License
-------

MIT

Author Information
------------------

You can find me on Twitter: [@mongrelion](https://twitter.com/mongrelion)
