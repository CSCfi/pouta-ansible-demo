pouta-ansible-demo
==================

Simple Ansible demo to deploy a machine to Pouta

To use this demo you will need:

- Ansible 2.0 or higher version:
   <http://docs.ansible.com/intro_installation.html>
- Python >=2.7:
   Needed by the os_security_group ansible module
- OpenStack command line tools:
   <http://docs.openstack.org/user-guide/content/install_clients.html>
- Shade: pip install shade
   <http://docs.openstack.org/infra/shade/>
- Access to pouta:
   <https://research.csc.fi/pouta-access>
- Your Pouta openstack RC file:
   <https://research.csc.fi/pouta-install-client>
- Your SSH public key uploaded to Pouta
   <https://pouta.csc.fi/dashboard/project/access_and_security/>

## Example: running the demo using python virtual inside the project folder

```
python3 -m venv venv
source venv/bin/activate
pip install ansible
pip install python-openstackclient
pip install shade
```

Configuration:

You will need to get some information from your pouta account in order to run this demo. See the comments in demo.yml.

To launch the demo:

    ansible-playbook demo.yml --extra-vars "demo_key=ansible_vm_key  demo_sg=demo-sg-ansible net_name=project_2001316 vm_name=pouta-demo path_to_key='/home/<host-username>/.ssh/your_publi_key.pub'"

Finally testing it in a browser or curl

    http://[floating_ip address]/
