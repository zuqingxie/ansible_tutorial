# ansible_tutorial
This is my awesome tutorial

1. create inventory for all server ip and username
2. try to connect with command 
''' 
    ansible all --key-file ~/.ssh/ansible -i inventory.ini -m ping  # -m module
'''
3 edit a ansible.cfg file locally which will overwrite the golbal file in /etc/ansible/config.cfg as defaults values then we can only type
'''
    ansible all -m ping
'''

    ansible all --list-hosts
    ansible all -m gather_facts
    ansible all -m gather_facts --limit zxie@192.168.106.125
    ansible all -m apt -a update_cache=true --become --ask-become-pass # run command with sudo  <=> sudo apt update
    ansible all -m apt -a name=vim-nox --become --ask-become-pass # <=> sudo apt install vim-nox
    ansible all -m apt -a "name=snapd state=latest" --become --ask-become-pass
    ansible all -m apt -a "upgrade=dist" --become --ask-become-pass # <=> sudo apt dist-upgrade -y


    ansible-playbook --ask-become-pass install_apache.yml
    
