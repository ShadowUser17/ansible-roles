#### Available tags:
- cmd_exec

#### Available vars:
- cmd_exec
- cmd_chdir

#### Examples:
```bash
./env/bin/ansible-playbook -i Home.yml -l k3s -t 'cmd_exec' -e '{"cmd_exec": "reboot"}' playbooks/Base.yml
```
```bash
./env/bin/ansible-playbook -i Home.yml -l k3s -t 'cmd_exec' -e '{"cmd_exec": "poweroff"}' playbooks/Base.yml
```
```bash
./env/bin/ansible-playbook -i Home.yml -l k3s -t 'cmd_exec' -e '{"cmd_exec": "crictl img"}' -v playbooks/Base.yml
```
```bash
./env/bin/ansible-playbook -i Home.yml -l k3s -t 'cmd_exec' -e '{"cmd_exec": "crictl rmi -q"}' -v playbooks/Base.yml
```
```bash
./env/bin/ansible-playbook -i Home.yml -l k3s -t 'cmd_exec' -e '{"cmd_exec": "df -h -t ext4"}' -v playbooks/Base.yml
```
