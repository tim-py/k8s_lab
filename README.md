# Ansible Lab Setup
Set of Ansible "Code-As-Configuration" playbooks used for creating test
VMs either locally or in a cloud service.

## Set up a local VM in VirtualBox
- Install the OS as Usual, using NAT network
- Create an RSA keypair for authentication
- Copy the contents of the public key into a new
file on the VM ~/.ssh/authorized_keys
- Locate keys on host machine in ./ssh and make
sure the private key has mode 600
- Add user to /etc/sudoers using the NOPASSWORD: ALL option
- Add a NAT traslation for SSH using this command:
 VBoxManage modifyvm "_vm_name_" --natpf1 "guestssh,tcp,,_host_port_,,_guest_port_"
- SSH to the VM using: ssh -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null
-p _host_port_ -i ~/.ssh/_rsa_key_file_ user@localhost


