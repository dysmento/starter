starter
=======
## Get started



1. Be sure to have the XCode Command-Line tools installed: `xcode-select --install`
2. Easy_install pip, and then pip install Ansible: `sudo easy_install pip; sudo pip install ansible` (or `sudo pip install --upgrade ansible` if Ansible has already been installed via pip and needs upgrading to 1.8+)
3. While that's happening [clone this repo](https://github.com/dysmento/starter.git) 
4. `cd starter`
5. `ansible-playbook --ask-vault-pass --ask-become-pass purecloud.yml`

## Configuration
You need to provide some parameters to the script. Replace `my_variables` in this project with your own file that looks like this:
```
---
bitbucket_username: someuser 
bitbucket_password: foopassword
inin_email: first.last@inin.com
inin_repo_dev_password: yet-another-password 
aws_secret_access_key_inindca: blah 
aws_access_key_id_inindca: blah
aws_secret_access_key_inintca: blah
aws_access_key_id_inintca: blah
aws_secret_access_key_ininsca: blah
aws_access_key_id_ininsca: blah
osx_mas_account: something@me.com
osx_mas_password: icloudpassword 
osx_mas_applications:
- name: Kuvva
  id: 451557061
osx_mas_upgrade: true
```
We use ansible vault to keep this file encrypted since it has _secrets_ in it:

    ansible-vault encrypt my_variables

And it'll ask you for a password. When you run `ansible-playbook`, it'll prompt you for you two passwords: the sudo password for your mac, and the vault password you just chose.

