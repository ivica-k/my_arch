## my_arch
A role for Ansible that configures my Arch Linux installation just the way I like it, including:
- KDE
- PyCharm Professional
- nVidia drivers
- Bumblebee configured
- Vagrant
- VirtualBox
- Docker
- LibreOffice
- Inkscape, Gimp
- Compression utilities
- Performance tweaks

## Prerequisites
- Base installation of Arch Linux. Run this playbook when you're ready to work on [post-installation](https://wiki.archlinux.org/index.php/installation_guide#Post-installation)
- Python 3 installed on the arch_box `pacman -Sy python --noconfirm`

## Verify connectivity
Edit the `ansible.cfg` file and change the values for `remote_user` and `private_key_file`. After that, verify connectivity with:
```
ansible -m ping arch_box
```

Successful run of the command produces:
```
127.0.0.1 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
```

## How to run
 
1. Edit the `hosts` file and replace `127.0.0.1` and `2222` with the host and port of your Arch box
```
[arch_box]
ansible_host=127.0.0.1 ansible_port=2222 ansible_python_interpreter=/usr/bin/python3
```
2. Create and activate a virtual environment
```
virtualenv -p python3 venv
source venv/bin/activate
pip install -r requirements.txt
```
3. Run the playbook. 'git_user' and 'git_email' are optional
```
ansible-playbook run.yml -e user_pass='CHOOSE_A_PASSWORD' -e git_user='GIT_USERNAME' -e git_email='GIT_EMAIL'
```

## Vagrant
A `Vagrantfile` is included for testing and development, and the machine it creates has 4 cores and 4GB of RAM - feel free to tweak them.

#### Good luck, and enjoy your Arch Linux
