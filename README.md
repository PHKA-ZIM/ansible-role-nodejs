# Nodejs install automation with ansible

## Installation steps

- Go to you ansible project folder
- Add following to your requirements file

```
- src: https://github.com/PHKA-ZIM/ansible-role-nodejs
  name: ansible-role-nodejs
```

- Install to project roles path
```
ansible-galaxy install -r requirements.yml --roles-path ./roles
```

## Use ansible-role-nodejs

- Import role and override role variables, e.g.
```
- name: Setup nodejs
  hosts: localhost
  connection: local
  roles:
    - role: ansible-role-nodejs
      vars:
        node_version: "17.x"
        node_uninstall: false
```

- All available role vars can be found in `defaults`
