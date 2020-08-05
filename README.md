# Ansible Tower Windows Ready Container 
> This is an Ansible Tower custom container image that brings the pre requirements to use it with Windows Hosts.

[![License](http://img.shields.io/:license-mit-blue.svg?style=flat-square)](http://badges.mit-license.org)
[![Latest Github release](https://img.shields.io/badge/release-v1.0-brightgreen)](https://github.com/abass0/winrm-tower/releases)
<img src="https://img.shields.io/github/last-commit/abass0/winrm-tower/master?style=plastic" alt="GitHub last commit">

## Container Image Description

This image was based on the following:

  * Red Hat Enterprise Linux 7
  
  * Ansible Tower 3.7.1-1
  
  * Python Packages
    * pywinrm
    * ptwinrm

This image was tested on:

  * OpenShift v3.11
  * OpenShift v4.2

## Suporting Documentation

Ansible Tower's default container image does not contain the necessary python libraries for it to be used on Windows Hosts.

This article describes the procedure for adding python virtualenv to a custom image on OpenShift: 

> * https://access.redhat.com/solutions/3625591

This image was also based on the official documentation for Ansible Tower deployment on OpenShift:

> * https://docs.ansible.com/ansible-tower/latest/html/administration/openshift_configuration.html#openshift-deployment-and-configuration

Additionally, there is some pre configuration that is needed to be performed on the Windows Host:

> * https://docs.ansible.com/ansible/latest/user_guide/windows_setup.html





