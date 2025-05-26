#### Available tags:
- ipa_client_install
- ipa_client_config
- ipa_client_remove
- ipa_server_install

#### Available vars:
- ipa_server
- ipa_domain
- ipa_admin
- ipa_passwd

#### Install client:
```bash
ipa host-add --force <hostname>
```
```bash
./env/bin/ansible-playbook -i Home.yml -l <host> -t "ipa_client_install,ipa_client_config" \
-v '{"ipa_server": "ipa", "ipa_domain": "testing.local", "ipa_passwd": ""}' playbooks/Services.yml
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
