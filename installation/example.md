




```bash
[servers]
server1 ansible_host=<Public IP>
server2 ansible_host=<Public IP>

[prd]
server3 ansible_host=<Public IP>
```

```bash
[all:vars]
ansible_python_interpreter=/usr/bin/python3
ansible_user=ubuntu
ansible_ssh_private_key_file=/home/ubuntu/keys/ansible-master-key-demo.pem
```


```bash
ansible-inventory --list
```

```bash
ansible prd -m ping 
```
