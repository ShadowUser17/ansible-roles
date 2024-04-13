#### Available tags:
- k3s_server
- k3s_agent
- k3s_network_none
- k3s_config
- flux
- istio
- cilium
- hubble
- kubectl
- cilium_cli

#### K3S vars:
- k3s_version
- k3s_server
- k3s_token

#### Other vars:
- flux_version
- istio_version
- cilium_version
- kubectl_version
- cilium_cli_version

#### URLs:
- [k3s](https://github.com/k3s-io/k3s/releases)
- [flux2](https://github.com/fluxcd/flux2/releases)
- [istio](https://github.com/istio/istio/releases)
- [cilium](https://github.com/cilium/cilium/releases)
- [cilium-cli](https://github.com/cilium/cilium-cli/releases)

#### Deploy K3S server:
```bash
./env/bin/ansible-playbook -i Home.yml -l k3s-server -t k3s_server playbooks/Services.yml
```
```bash
kubectl taint node <server_node> "node-role.kubernetes.io/master:NoSchedule"
```
```bash
kubectl taint node <server_node> "node-role.kubernetes.io/control-plane:NoSchedule"
```

#### Deploy K3S server with Cilium:
```bash
./env/bin/ansible-playbook -i Home.yml -l k3s-server -t k3s_network_none playbooks/Services.yml
```
```bash
./env/bin/ansible-playbook -i Home.yml -l k3s-server -t "k3s_config,cilium" playbooks/Services.yml
```

#### Deploy K3S agents:
```bash
./env/bin/ansible-playbook -i Home.yml -l k3s-agents -t k3s_agent playbooks/Services.yml
```

#### Configure kubectl:
```bash
mkdir ~/.kube && scp k3s-server:/etc/rancher/k3s/k3s.yaml ~/.kube/ && \
sed 's/127\.0\.0\.1/192\.168\.56\.11/g' ~/.kube/k3s.yaml > ~/.kube/config && \
chmod 600 ~/.kube/config && rm -f ~/.kube/k3s.yaml
```
