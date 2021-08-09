## PRE-REQUISITES

* 3 Ubuntu Machine (with Ubuntu version as 18.x), one as Ansible Host, one as Kubernetes Master and the remaining one as Kubernetes Wroker Node
* Ansible host should have ansible package installed and configured
* An Ansible user must be created inside all VMs (with passwordless sudo priviledge)


After cloning this repo you can bootstrap your cluster with
```
ansible-playbook install-kubernetes.yaml -v
```


Host File Format would be as below -
```
[kubemaster]
kubemaster ansible_user=<Username_of_the_created_user>

[kubeworkers]
kubeworker1 ansible_user=<Username_of_the_created_user>

[all:vars]
ansible_python_interpreter=/usr/bin/python3 #This is only required if you have Python 2.x and 3.x are installed on the system

```