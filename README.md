# virtual-dev-environment

## Reqs
- Python3
- Virtualenv
- AWS CLI access set up in a way that Ansible can assume it

## Usage
```bash
# set up the local env
source ./venv/bin/activate
python3 -m pip install requirements.txt

# provision the environment
ansible-playbook playbook.yml -t provision

# nuke it
ansible-playbook playbook.yml -t nuke

# start / stop the instance
ansible-playbook playbook.yml -t [stop,start]
```