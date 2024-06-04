# BIG-IP tmp Folder Cleanup Playbook

**Use this playbook from BIG-IQ CM to clean up the tmp folders within BIG-IPs across your estate**

1. SSH to your BIG-IQ CM instance, which has Ansible pre-installed
2. Navigate to the admin home directory

    `cd /home/admin`
3. Create a folder named `ansible_playbooks` if it does not already exist, then enter the folder

    `mkdir ansible_playbooks && cd $_`
4. Create a folder named `bigip-clean-tmp-folders`, then enter the folder

    `mkdir bigip-clean-tmp-folders && cd $_`
5. Copy the following files into the newly-created directory

    - ansible.cfg
    - big-ip-tmp-folder-cleanup.yml
    - bigiphosts
6. Update the `username` and `password` variables within `bigiphosts`
7. Update the `f5` section of the `bigiphosts` file to reflect the BIG-IP targeted in your estate. There are two pre-populated examples showing the convention used.

    `<hostname> private_ip=<ip_address>`

    e.g.

    `west-adc-02b.f5demo.com private_ip=10.1.1.16`

7. Run the Ansible playbook

    `ansible-playbook big-ip-tmp-folder-cleanup.yml`