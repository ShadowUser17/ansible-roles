#### Available tags:
- ipa_server_install
- ipa_server_remove
- ipa_client_install
- ipa_client_remove

#### Available vars:
- ipa_server
- ipa_domain
- ipa_domain_passwd
- ipa_admin
- ipa_admin_passwd

#### Install server:
```bash
./env/bin/ansible-playbook -i Home.yml -l <host> -t ipa_server_install playbooks/Services.yml
```

#### Remove server:
```bash
./env/bin/ansible-playbook -i Home.yml -l <host> -t ipa_server_remove playbooks/Services.yml
```

#### Install client:
```bash
ipa host-add --force <hostname>
```
```bash
ipa hostgroup-add-member <group> --hosts=<host>
```
```bash
./env/bin/ansible-playbook -i Home.yml -l <host> -t ipa_client_install playbooks/Services.yml
```

#### Remove client:
```bash
ipa host-disable <hostname>
```
```bash
ipa host-remove <hostname>
```
```bash
./env/bin/ansible-playbook -i Home.yml -l <host> -t ipa_client_remove playbooks/Services.yml
```
