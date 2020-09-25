# Ansible Tower Windows Ready Container (plus ServiceNow)
> This is an Ansible Tower custom container image that brings the pre requirements to use it with Windows Hosts and, additionally, the requirements for ServiceNow integration.

[![License](http://img.shields.io/:license-mit-blue.svg?style=flat-square)](http://badges.mit-license.org)
[![Latest Github release](https://img.shields.io/badge/release-v1.0-brightgreen)](https://github.com/abass0/winrm-tower/releases)
<img src="https://img.shields.io/github/last-commit/abass0/winrm-tower/master?style=plastic" alt="GitHub last commit">

## Container Image Description

This image was based on the following:

  * Red Hat Enterprise Linux 7
  
  * Ansible Tower 3.7.1-1
  
  * Python Packages (for connecting with Windows Hosts)
    * pywinrm
    * ptwinrm
    
  * Python Packages (for connecting with ServiceNow)
    * pysnow
    * netaddr

This image was tested on:

  * OpenShift v3.11
  * OpenShift v4.2
  * ServiceNow New York Release

## Suporting Documentation (for Windows Hosts)

Ansible Tower's default container image does not contain the necessary python libraries for it to be used on Windows Hosts.

This article describes the procedure for adding python virtualenv to a custom image on OpenShift: 

> * https://access.redhat.com/solutions/3625591

This image was also based on the official documentation for Ansible Tower deployment on OpenShift:

> * https://docs.ansible.com/ansible-tower/latest/html/administration/openshift_configuration.html#openshift-deployment-and-configuration

Additionally, there is some pre configuration that is needed to be performed on the Windows Host:

> * https://docs.ansible.com/ansible/latest/user_guide/windows_setup.html

## Suporting Documentation (for ServiceNow integration)

Using Tower on ServiceNow requires some configurations of tokens and credentials. This repo by Michael Ford walks trough the process of setting up Tower:

> * https://github.com/michaelford85/cloud-deploy/blob/master/readme/snow_integration.md

This documentation was also used to setup the user Token for OAuth2 to be able to authenticate with Tower - ServiceNow:

> * https://docs.ansible.com/ansible-tower/latest/html/userguide/applications_auth.html

Swagger API documentation for Ansible Tower also helped on the process:

> * https://docs.ansible.com/ansible-tower/latest/html/towerapi/api_ref.html

## Additional Parameters for Ansible - Windows Comunication

These parameters go on the `variables` input of your inventory:
```
---
ansible_port: 5986
ansible_connection: winrm 
ansible_winrm_server_cert_validation: ignore
ansible_winrm_transport: ntlm

```
