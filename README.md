# kubernetes-ansible
ansible roles to set up a simple kubernetes cluster

*Multi-Master setups are NOT supported*

## Usage
First, edit the `hosts` file to contain the list of nodes in your cluster. 
Next, edit the ansible.cfg file with the username you want to use to connect. 
Once these steps are done the playbooks can be run. Run them with
`ansible-playbook install.yaml`. 
There are several steps which can be skipped. 
By default, all hosts in the cluster will have their hostname changed to match
the hostname in the ansible inventory. This can be skipped with `--skip-tags=hostname`.

A secure kubernetes token can be generated with `echo "$(openssl rand -base64 24 | sed 's/[\/\+A-Z]//g' | head -c 6).$(openssl rand -base64 64 | sed 's/[\/\+A-Z]//g' | head -c 16)"`
