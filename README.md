Ansible Role - Arduino Platform Watcher
=========

Configures a script watching platform.txt files, triggering [Asible Role - Arduino Patch Platform](https://github.com/MXPicture/ansible-role-arduino-patch-platform) and using Launch Agent for executing the script at user login.

Requirements
------------

macOS/Linux

Role Variables
--------------

`arduino_platform_script_dir`: Directory containing the script `arduino-platform-watcher.sh` (it executes the playbook)

`arduino_platform_watch_path`: Path to be watched for created/changed "platform.txt" files

`arduino_platform_playbook_path`: Playbook-Path to be executed at file change

`arduino_watcher_state`: present or absent (default: `present`)

Dependencies
------------

Arduino. At least the directory must exist.


Example Playbook
----------------
### Minimum
```
- hosts: localhost
  gather_facts: true
  roles:
    - role: MXPicture.arduino-platform-watcher
```

### Change Playbook Path
```
- hosts: localhost
  gather_facts: true
  roles:
    - role: role: MXPicture.arduino-platform-watcher
      vars:
        arduino_platform_playbook_path: "{{ playbook_dir }}/arduino-patch-platform-playbook.yml"
```

### Present State (default)
```
- hosts: localhost
  gather_facts: true
  roles:
    - role: role: MXPicture.arduino-platform-watcher
      vars:
        arduino_watcher_state: present
```

### Absent State
```
- hosts: localhost
  gather_facts: true
  roles:
    - role: role: MXPicture.arduino-platform-watcher
      vars:
        arduino_watcher_state: absent
```

Local Testing
-------

`cd ..`
`ansible-playbook -i localhost, -c local roles/ansible-role-arduino-platform-watcher/tests/test.yml`

License
-------

MIT

Author Information
------------------

Tobias Bildner
