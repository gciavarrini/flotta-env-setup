# flotta-env-setup
Ansible playbooks to setup flotta project enviroment

# Getting started

1. Create two VMs with Fedora 36.
2. Set yout `/etc/hosts`
    ```
    <VM operator IP addr> f36-ee ansible_user=<YOUR_ANSIBLE_USER>
    <VM edge device IP addr> f36-ee-edgedevice ansible_user=<YOUR_ANSIBLE_USER>
    ```
3. From your local machine, copy your public ssh key into each VM
    `ssh-copy-id your_username@f36-ee`
    `ssh-copy-id your_username@f36-ee-edgedevice`
4. Create a new user on the VMs
    `ansible-playbook --connection ssh --user root vm-user-setup.yml -K`
5. Set up the env for the edge device
    `ansible-playbook --connection ssh --user <YOUR_USERNAME>  vm-setup-device-playbook.yml -K`
6. Set up the env for the operator
    `ansible-playbook --connection ssh --user <YOUR_USERNAME>  vm-setup-playbook.yml -K`
7. Connect to the operator vm
   1. Start minikube (`minikube start`) and follow the [instruction](https://project-flotta.io/documentation/v0_2_0/gsg/minikube.html) on the Project Flotta website



