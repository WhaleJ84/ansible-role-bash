bash
=========

Installs and configures bash for the user.

Requirements
------------

To include this role in your `requirements.yml` file, add the following list item:

```yaml
---
roles:
  - names: whalej84.bash
    src: https://github.com/WhaleJ84/ansible-role-bash.git
    scm: git
```

Role Variables
--------------

| Name | Type | Description | Default |
| ---- | ---- | ----------- | ------- |
| shell.rc | string | A path to where bashrc is located | "$HOME/.bashrc" |
| HISTSIZE | string | A string value for the HISTSIZE variable | 1000 |
| HISTFILESIZE | string | A string value for the HISTFILESIZE variable | 2000 |
| inputrc | string | A path to where inputrc should be located | |

Example Playbook
----------------

This example playbook shows how I would use this role, with custom variables to suit my needs.

```yaml
- hosts: localhost

  roles:
    - role: whalej84.bash
      vars:
        shell:
          rc: "{{ ansible_user_dir }}/.bashrc"
        HISTSIZE: ""
        HISTFILESIZE: ""
        inputrc: "{{ ansible_user_dir }}/.config/bash/inputrc"
      tags: [bash]
```
