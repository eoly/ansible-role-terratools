Terratools
=========

Ansible role to manage the installation of various Terraform related tools.

Requirements
------------

None

Role Variables
--------------

```
terratools_install_terraform: yes
terratools_install_terragrunt: yes

terraform_archive_versions:
 - 0.12.20
 - 0.11.14
terraform_active_version: 0.11.14
terraform_system_arch: amd64
terraform_release_base_url: "https://releases.hashicorp.com/terraform"

terragrunt_binary_versions:
 - 0.18.7
terragrunt_active_version: 0.18.7
terragrunt_system_arch: amd64
terragrunt_release_base_url: "https://github.com/gruntwork-io/terragrunt/releases/download"

tflint_archive_versions:
 - 0.14.0
tflint_active_version: 0.14.0
tflint_system_arch: amd64
tflint_release_base_url: "https://github.com/terraform-linters/tflint/releases/download"

terratools_install_path: /opt/terratools
```

Dependencies
------------

None

Example Playbook
----------------

```
- hosts: localhost
  become_method: sudo
  connection: local
  gather_facts: yes
  tasks:
    - import_role:
        name: terratools
      become: true
      tags:
      - packages
      - terratools
      vars:
        terraform_archive_versions: "{{ my_terraform_versions }}"
        terraform_active_version: "{{ my_terraform_active_version }}"
        terragrunt_binary_versions: "{{ my_terragrunt_versions }}"
        terragrunt_active_version: "{{ my_terragrunt_active_version }}"
```

License
-------

BSD

Author Information
------------------

Eric Olsen <ericjolsen@gmail.com>
