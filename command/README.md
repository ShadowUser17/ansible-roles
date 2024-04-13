#### Available tags:
- cmd_exec

#### Available vars:
- cmd_exec
- cmd_chdir

#### Examples:
```bash
./env/bin/ansible-playbook -i Home.yml -t 'cmd_exec' -e '{"cmd_exec": "reboot"}' playbooks/Base.yml
```
```bash
./env/bin/ansible-playbook -i Home.yml -t 'cmd_exec' -e '{"cmd_exec": "poweroff"}' playbooks/Base.yml
```
```bash
./env/bin/ansible-playbook -i Home.yml -l k3s -t 'cmd_exec' -e '{"cmd_exec": "cilium status"}' -v playbooks/Base.yml
```
```bash
./env/bin/ansible-playbook -i Home.yml -l k3s -t 'cmd_exec' -e '{"cmd_exec": "crictl rmi -q"}' -v playbooks/Base.yml
```
```bash
./env/bin/ansible-playbook -i Home.yml -l k3s -t 'cmd_exec' -e '{"cmd_exec": "k3s-killall.sh"}' playbooks/Base.yml
```
