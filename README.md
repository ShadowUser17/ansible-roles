### Roles for my testing stand...

#### URLs:
- [molecule](https://github.com/ansible-community/molecule/releases)
- [ansible-lint](https://github.com/ansible/ansible-lint/releases)
- [ansible-core](https://github.com/ansible/ansible/releases)

#### Install Ansible:
```bash
python3 -m venv --upgrade-deps env && \
./env/bin/pip3 install -r requirements.txt
```

#### Get example config:
```bash
./env/bin/ansible-config init --disabled > ansible.cfg.example
```

#### Get VM info:
```bash
./env/bin/ansible -i <inventory> -m 'gather_facts' <hosts> > facts.json
```

#### Ping host:
```bash
./env/bin/ansible -i <inventory> -m 'ping' <hosts>
```

#### New empty role:
```bash
./env/bin/ansible-galaxy role init <role>
```
```bash
mkdir -p "${ROLE}"/{tasks,vars} && \
touch "${ROLE}"/{tasks,vars}/main.yml && \
touch "${ROLE}"/README.md
```

#### Run Playbook:
```bash
./env/bin/ansible-playbook -i <inventory> -t <tags> -e <extra-vars> -l <hosts-limit> <playbook>
```

#### Test Playbook:
```bash
./env/bin/ansible-playbook -i <inventory> -C <playbook>
```

#### Additional packages for Fedora:
```bash
dnf install python3-dnf python3-libdnf5
```
