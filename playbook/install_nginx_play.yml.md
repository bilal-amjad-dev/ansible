

```bash
vim install_nginx_play.yml
```

```bash
-
 name: Install Nginx and start it
 hosts: servers
 become: yes # it for root user
 tasks:
  - name: Install Nginx
    apt:
     name: nginx
     state: latest
  - name: Start Nginx
    service:
     name: nginx
     state: started
     enabled: yes
```

Esc:wq!

```bash
ansible-playbook install_nginx_play.yml
```

*Now, copy public ip of server2 and paste in browswer*

*and you can see*

**Welcome to nginx!**


