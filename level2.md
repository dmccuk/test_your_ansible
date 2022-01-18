# Create Ansible to do the following

  * Create 3 users [tom:UID 2001, dick:UID 2002 & harry:UID 3001]
  * For users with a UID < 3000, add them to the "wheel" group
  * Set X11Forwarding to yes (permanently)
  * Set the MOTD to contain "Unauthorised access is not allowed on this server"

Bonus points will be awarded if the playbook runs on the REDHAT and DEBIAN ansible_os_family.

### successful tests

This is what I'd like to see if you pass:

<details>
 <summary>Expand for Successful output</summary>
  <p>

````
[ec2-user@ip-172-31-16-55 test_yourself]$ ansible-playbook level2.yml
[WARNING]: No inventory was parsed, only implicit localhost is available
[WARNING]: provided hosts list is empty, only localhost is available. Note that the implicit localhost does not match
'all'

PLAY [tests] **********************************************************************************************************

TASK [check sshd_config for X11 forwarding] ***************************************************************************
changed: [localhost]

TASK [check tz] *******************************************************************************************************
ok: [localhost] => {
    "changed": false,
    "msg": "All assertions passed"
}

TASK [Check tom exists] ***********************************************************************************************
changed: [localhost]

TASK [confirm tom exists] *********************************************************************************************
ok: [localhost] => {
    "changed": false,
    "msg": "All assertions passed"
}

TASK [Check dick exists] **********************************************************************************************
changed: [localhost]

TASK [confirm dick exists] ********************************************************************************************
ok: [localhost] => {
    "changed": false,
    "msg": "All assertions passed"
}

TASK [Check harry exists] *********************************************************************************************
changed: [localhost]

TASK [confirm harry exists] *******************************************************************************************
ok: [localhost] => {
    "changed": false,
    "msg": "All assertions passed"
}

TASK [Check Toms groups] **********************************************************************************************
changed: [localhost]

TASK [confirm toms groups] ********************************************************************************************
ok: [localhost] => {
    "changed": false,
    "msg": "All assertions passed"
}

TASK [Check dicks groups] *********************************************************************************************
changed: [localhost]

TASK [confirm dicks groups] *******************************************************************************************
ok: [localhost] => {
    "changed": false,
    "msg": "All assertions passed"
}

TASK [Check harrys groups] ********************************************************************************************
changed: [localhost]

TASK [confirm harrys groups] ******************************************************************************************
ok: [localhost] => {
    "changed": false,
    "msg": "All assertions passed"
}

TASK [collect MOTD contents] ******************************************************************************************
changed: [localhost]

TASK [confirm string in MOTD] *****************************************************************************************
ok: [localhost] => {
    "changed": false,
    "msg": "All assertions passed"
}

PLAY RECAP ************************************************************************************************************
localhost                  : ok=16   changed=8    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

````
</p></details>

Good Luck

