# Terraform-Vagrant

## Step1:
### Terraform foler
    run **Terraform apply** to launch ec2 instant in AWS
    tools such as _virtualbox, vagrant, ansible, py3_ will be installed automatically after ec2 spinned up


## Step2:
### Vagrant folder 
    run **vagrant up** to launch vm such as ios-xe, ios-xr, nxos, etc
    pre-build your network topolegy by virtually design the physical connection

 
## Step3:
### Ansible-Napalm folder 
    run **ansible-play playbook_datamodelling.yml -i host_vagrant_lab-iosxe.yml --tag model** to transform HLD to per-node design
    run **ansible-play playbook_datamodelling.yml -i host_vagrant_lab-iosxe.yml --tag template** to template variables into config file with Jinja2 template
    run **ansible-play playbook_datamodelling.yml -i host_vagrant_lab-iosxe.yml --tag deploy --e "commit=1"** to push the config file onto devices via napalm

 
