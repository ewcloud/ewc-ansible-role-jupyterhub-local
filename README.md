EWC Ansible Role Jupyterhub local
=================================

Create a conda environment with jupyterhub instance running locally. The instance needs to have a public IP reachable from the Internet and the appropriate security groups configured to allow HTTP/HTTPS access.

Requirements
------------
This ansible role depends on ewc-ansible-role-conda

Role Variables
--------------
 - `jupyterhub_local_env_wipe`: Boolean to decide whether to wipe the environment if exists prior to a reinstallation. Default: no
 - `jupyterhub_local_env_name`: Name of the environment containing the Jupyerhub. Default: jupyterhub-local
 - `conda_prefix`: Prefix where conda is installed. Default: `/opt/conda`
 - `conda_user`: User owning the conda installation. Default: `root`
 - `jupyterhub_local_cert_email`: If ran outside Morpheus, pass this variable explicitly when running the ansible playbook
 - `jupyterhub_local_test_cert`: Use Lets encrypt test certificate. Default: false
 - `dns_domain`: Pass this variable explicitly when running the ansible playbook. If not present, will try to guess from instance configured hostname in /etc/hostname.
 - `jupyterhub_local_with_otp`: Use OTP authentication for Jupyterhub. Default: false

Example Playbook
----------------

    ---
    - hosts: all
      roles:
         -  ewc-ansible-role-jupyterhub-local

License
-------

Apache 2.0.

Author Information
------------------

ECMWF for the European Weather Cloud