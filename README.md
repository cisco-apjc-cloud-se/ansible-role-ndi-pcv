# ansible-role-ndi-pcv
Ansbile role for running Nexus Dashboard Insights - Pre-Change Validation jobs

Use the following in the collection requirements.yml file

https://galaxy.ansible.com/docs/using/installing.html

```yaml
---
roles:
  - name: ndi-pcv
    src: https://github.com/cisco-apjc-cloud-se/ansible-role-ndi-pcv
    version: main
    scm: git
```

Execute the role as a play with host/inventory and customised variables

```yaml
- name: Initiate Nexus Dashboard Insights - Pre-Change Delta Analysis
  hosts: nd
  gather_facts: false
  vars:
    insights_group: MEL-SE-LAB-ACI
    job_name: ANSIBLE-CICD-PCV
    site_name: MEL-SE-LAB-ACI
    input_file: config.json
  roles:
    - role: ndi-pcv
```