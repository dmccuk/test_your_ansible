# Test your Ansible
This repo contains Ansible "Assert" tests. Can you work out what you need to do to pass the tests?

## What do you have to do?
Every month or so, I'll upload a new "level" file. It will contain "assert" tests that you will need to create an ansible playbook to pass. Some will be simple, others will be harder.

Think of this as a game. Can you write the ansible you need to pass the test?

## How will it work?
You'll need to clone the tests and run them on your server. The tests will fail the first time they are run (of course!). You must write the correct ansible code to pass the tests. Once you're successful, create an issue and add your GitHub repo . I'll run your Ansible code on a clean server, then my "Assert" playbook and see if you passed.

The best solution, will become the levelX champion and their solution will be added to the repo for everyone else to see how it's done.

LEVEL1:
======
Level 1 is relatively simple and doesn;t require much experience with Ansible.

Tasks:
  * Set the timezone to UTC
  * Install NGINX
  * start NGINX and make sure port 80 is listening
  * Your index.html file must contain the string "Sorry for the inconvenience but"

Level2:
======
Slightly harder but you shold have no issues with this.

Tasks:
  * Create 3 users [tom:UID 2001, dick:UID 2002 & harry:UID 3001]
  * For users with a UID < 3000, add them to the "wheel" group
  * Set X11Forwarding to yes (permanently)
  * Set the MOTD to contain "Unauthorised access is not allowed on this server"

---

This is what I'd like to see if you pass:

<details>
 <summary>Expand for Successful output</summary>
  <p>
    
````
[ec2-user@ip-172-31-16-55 test_yourself]$ ansible-playbook level1.yml
[WARNING]: No inventory was parsed, only implicit localhost is available
[WARNING]: provided hosts list is empty, only localhost is available. Note that the implicit localhost does not match
'all'

PLAY [tests] **********************************************************************************************************

TASK [store date output for timezone check] ***************************************************************************
changed: [localhost]

TASK [check tz] *******************************************************************************************************
ok: [localhost] => {
    "changed": false,
    "msg": "All assertions passed"
}

TASK [Check if NGINX is installed] ************************************************************************************
ok: [localhost]

TASK [confirm nginx is installed] *************************************************************************************
ok: [localhost] => {
    "changed": false,
    "msg": "All assertions passed"
}

TASK [Check if port 80 is listening] **********************************************************************************
changed: [localhost]

TASK [confirm port 80 is listening] ***********************************************************************************
ok: [localhost] => {
    "changed": false,
    "msg": "All assertions passed"
}

TASK [collect index.html contents] ************************************************************************************
changed: [localhost]

TASK [confirm string in index.html] ***********************************************************************************
ok: [localhost] => {
    "changed": false,
    "msg": "All assertions passed"
}

PLAY RECAP ************************************************************************************************************
localhost                  : ok=8    changed=3    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
````
</p></details>

Level2 will follow shortly.
