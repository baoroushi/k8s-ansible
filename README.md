
## 环境

```
CentOS Linux release 7.6.1810 (Core)
```
## Install Epel 
yum install epel-release -y

## Install Ansible
yum install ansible -y

## ANSIBLE 

```
// I'm using Ansible version 2.6.2 and solution with host_key_checking = false doesn't work.

// Adding environment variable export ANSIBLE_HOST_KEY_CHECKING=False skipping fingerprint check.

export ANSIBLE_HOST_KEY_CHECKING=False
```
### 秘钥登录
ssh-keygen

```
// copy to other nodes

ssh-copy-id  root@10.57.1.202
```

## Insall
### k8s Cluster

```
cd /etc/ansible/playbook/k8s/cluster/

ansible-playbook  deploy_kubernetes_cluster.yml -i /etc/ansible/inventory
```

### Add New Node

```
cd /etc/ansible/playbook/k8s/new_node

ansible-playbook add_new_node.yml -i /etc/ansible/inventory
```

## 配置文件

```
/etc/ansible/inventory
```
