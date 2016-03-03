# How to use it

1) Installation.

    git clone git@github.com:fansible/tywin.git ~/tywin

2) Generate the default conf

You can generate the default conf by running in the root directory of your project:

    python ~/tywin/generate.py

You can now find your provisioning in the `devops` directory

3) Create the VM
You can create the VM with `vagrant up`.

4) Put your ssh key in the vagrant

i) Copy your public key `cat ~/.ssh/id_rsa.pub`

ii) Log in the vagrant with `vagrant ssh`

iii) Add your key in the authorized_keys file: `nano .ssh/authorized_keys`

iv) Exit the VM and try to log in with `ssh vagrant@10.0.0.10`

If it's OK you can provision the VM

5) Provision the VM

Provision it with `ansible-playbook -i devops/provisioning/hosts/vagrant devops/provisioning/playbook.yml`.

Your VM is now ready ! =)

### Database configuration
Change the value of the database configuration in `devops/provisioning/hosts/group_vars/vagrant`

### Go further: customize your provisioning
What you can do:

1) Add your roles in the `devops/provisioning/roles` directory.

2) Modify the playbook to call your roles.

3) Overide vars (in `devops/provisioning/vars`).