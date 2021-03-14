# Terraform-Vagrant

## Step1:
### Terrform folder
 '''
    run **Terraform apply** to launch ec2 instant in AWS</br>
    tools such as _virtualbox, vagrant, ansible, py3_ will be installed automatically after ec2 spinned up

## Setep2:
### Vagrant folder 
'''
    run **vagrant up** to launch vm such as ios-xe, ios-xr, nxos, etc</br>
    pre-build your network topolegy by virtually design the physical connection
 
## Setep3:
### Ansible-Napalm folder 
 '''
    run **ansible-play playbook_datamodelling.yml -i host_vagrant_lab-iosxe.yml --tag model** to transform HLD to per-node design</br>
    run **ansible-play playbook_datamodelling.yml -i host_vagrant_lab-iosxe.yml --tag template** to template variables into config file with Jinja2 template</br>
    run **ansible-play playbook_datamodelling.yml -i host_vagrant_lab-iosxe.yml --tag deploy --e "commit=1"** to push the config file onto devices via napalm</br>
 
 
