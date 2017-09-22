# Introduction

This is my private ansible-playbook to provision ubuntu running on AWS EC2.

# How to use

## Prerequisite

You need python in the host. SSH-in and install python.

```
sudo apt install python
```

If you are provisioning gpu node, you need to [download cuDNN deb file](https://developer.nvidia.com/cudnn) "cuDNN v6.0 Runtime Library for Ubuntu16.04 (Deb)" and "cuDNN v6.0 Developer Library for Ubuntu16.04 (Deb)" and place them to roles/gpu/files.
If names of downloaded files are not "libcudnn6_6.0.21-1+cuda8.0_amd64.deb" and "libcudnn6-dev_6.0.21-1+cuda8.0_amd64.deb" respectively, you must configure defaults/main.yml accordingly.

Finally, add names of provisioned hosts to `production`.

## Running Ansible-Playbook

Check validity of the playbook with:

```
ansible-playbook -i production site.yml --check
```

Run the actual playbook with:

```
ansible-playbook -i production site.yml
```
