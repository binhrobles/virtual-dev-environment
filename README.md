# virtual-dev-environment
Provisions an EC2 instance for use as a remote dev environment while I'm delaying buying a higher powered laptop than this chromebook. 

Just using an EBS-backed AMI atm -- should assume the dev machine can / will be torn down regularly, so all work is pushed regularly into github.

## Local Env Reqs
- Python3
- Virtualenv
- AWS CLI access set up in a way that Ansible can assume it
- An SSH key at `~/.ssh/vdev`

## AWS Account Reqs
- EC2 Instance Connect endpoint set up on the target VPC
  - bypasses need to provision a public IP

## Usage
```bash
# set up the local env
source ./venv/bin/activate
python3 -m pip install requirements.txt

# all interaction is done via tags
ansible-playbook playbook.yml -t [provision|stop|start|nuke]

# see example.ssh.config to continue w/ ssh
```
