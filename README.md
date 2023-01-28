# k8s_ansible_setup

保证 目标机器能ssh 自动登录 ansible ok
0.验证
```
ansible -i k8s.hosts YOUR_MACHINE_HOSTNAME1,YOUR_MACHINE_HOSTNAME2,YOUR_MACHINE_HOSTNAME3 -m ping
```

1
```
ansible-playbook -i k8s.hosts install-k8s-new.yml  -e 'variable_host=YOUR_MACHINE_HOSTNAME1,YOUR_MACHINE_HOSTNAME2,YOUR_MACHINE_HOSTNAME3' -vvv  -K
```
2
```
ansible-playbook -i k8s.hosts create_master.yml  -e 'variable_host=YOUR_MASTER_MACHINE_HOSTNAME' -vvv  -K
```
3
```
ansible-playbook -i k8s.hosts create_workers.yml  -e 'variable_host=YOUR_WORKER_MACHINE_HOSTNAME1,YOUR_WORKER_MACHINE_HOSTNAME2' -vvv  -K
```
