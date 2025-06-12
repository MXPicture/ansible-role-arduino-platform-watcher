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

`arduino_platform_playbook`: Playbook-Path to be executed at file change

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
    - role: arduino_platform_watcher
      vars:
        arduino_platform_playbook: "{{ ansible_user_dir }}/ansible/arduino.yaml"
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
