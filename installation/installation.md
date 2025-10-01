

### Send key-pair (ansible-master-key-demo.pem) from your local computer to ansible server


1. Create keys folder in master server

```bash
mkdir keys
```

2. Run Scp (source copy) command in your local machine

```bash
chmod 400 ansible-master-key-demo.pem
```

```bash
scp -i "ansible-master-key-demo.pem" ansible-master-key-demo.pem ubuntu@ec2-54-152-.compute-1.amazonaws.com:/home/ubuntu/keys
```

3. Master server (you can see the key has come here)

```bash
cd keys 
ls
```



### Update hosts file

```bash
sudo vim /etc/ansible/hosts
```

```bash
[servers]
server1 ansible_host=<Public IP>
server2 ansible_host=<Public IP>
server3 ansible_host=<Public IP>
```

```bash
[all:vars]
ansible_python_interpreter=/usr/bin/python3
ansible_user=ubuntu
ansible_ssh_private_key_file=/home/ubuntu/keys/ansible-master-key-demo.pem
```

Esc:wq!






### Ping all servers

```bash
ansible servers -m ping 
```


```bash
ansible servers -a "free -h"
```

```bash
ansible-inventory --list
```











