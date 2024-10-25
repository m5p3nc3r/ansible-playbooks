```bash
# install roles and collections
ansible-galaxy install -r requirements.yml

# Install the playbook
ansible-playbook -i inventory -e @secrets.enc --ask-vault-pass frontend.yaml

# Github runner
ansible-playbook -i inventory -e @secrets.enc --ask-vault-pass github-runner.yaml
```
