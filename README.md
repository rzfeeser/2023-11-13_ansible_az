## Ansible Builder Commands (create EE)
# https://github.com/ansible/ansible-builder
# https://ansible.readthedocs.io/projects/builder/en/stable/
ansible-builder build --tag azure-ee --container-runtime docker --verbosity 3
ansible-builder build --tag windows-ee --container-runtime docker --verbosity 3

## Ansible Runner (use EE)
# https://github.com/ansible/ansible-runner
# https://ansible.readthedocs.io/projects/runner/en/stable/index.html
ansible-runner run --process-isolation --process-isolation-executable docker --container-image azure-ee -p azure-resource-group-playbook.yml .
ansible-runner run --process-isolation --process-isolation-executable docker --container-image windows-ee -p windows_services01.yml .
