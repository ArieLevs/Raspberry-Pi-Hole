# Raspberry-Pi-Hole
Ansible installation of pi-hole

###Installation

* MacOS users: to fix below error
    ```
    Galaxy at 'https://galaxy.ansible.com/api/': <urlopen error [SSL: CERTIFICATE_VERIFY_FAILED]
    certificate verify failed: unable to get local issuer certificate (_ssl.c:1123)>
    ```
    cd to the python directory Ansible is using and execute (python 3.8 for example)
    ```
    cd /Applications/Python\ 3.8
    ./Install\ Certificates.command
    ``` 


install dependencies 
```shell script
ansible-galaxy install -r requirements.yaml
```

```shell script
ansible-playbook \
  --ask-become-pass --become --user lev \
  -i "10.99.0.83," \
  setup_pi_hole.yaml \
  --key-file ~/.ssh/id_rsa
```


```shell script
ansible-playbook \
  --ask-become-pass --become --user pi --ask-pass \
  -i "10.99.0.61," \
  setup_pi_hole.yaml
```
