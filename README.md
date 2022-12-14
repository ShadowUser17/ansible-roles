### Roles for my testing stand...

#### Install/Upgrade Ansible:
```bash
python3 -m venv --upgrade-deps .env
```
```bash
./.env/bin/pip3 install --upgrade ansible ansible-lint
```

#### Get example config:
```bash
./.env/bin/ansible-config init --disabled > ansible.cfg.example
```

#### Get VM info:
```bash
./.env/bin/ansible -i <inventory> -m 'gather_facts' <hosts>
```

#### New empty role:
```bash
./.env/bin/ansible-galaxy role init <role>
```

#### Run Playbook:
```bash
./.env/bin/ansible-playbook -i <inventory> -t <tags> -e <extra-vars> <playbook>
```

#### Test Playbook:
```bash
./.env/bin/ansible-playbook -i <inventory> -C <playbook>
```
