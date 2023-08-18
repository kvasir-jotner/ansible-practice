# Ansible Playbook README

This Ansible playbook is designed to automate tasks for a server, specifically targeting a Debian/Ubuntu OS environment. This document describes the steps taken and their purpose.

## Overview

- Ensuring the existence of an `automation` group.
- Creating a user named `ansible` under the `automation` group, with no home directory.
- Updating all the packages to their latest versions.
- Installing the `cmatrix` application.
- Installing required utilities such as `curl` and `jq`.
- Creating a script for Message of the Day (MOTD) which fetches a daily quote and displays it when users log in.

## Playbook Details

### Target Host

- `127.0.0.1`

### Tasks

1. **Check if 'automation' group exists**
   - This ensures that an `automation` group exists on the target host.

2. **Create 'ansible' user without a home directory and assign to 'automation' group**
   - A user named `ansible` is created and assigned to the `automation` group. This user will not have a home directory.

3. **Update all packages to their latest version (Debian/Ubuntu)**
   - All the installed packages on the server will be updated to their latest versions. 
   - Note: Any errors encountered during this task will be ignored.

4. **Install Cmatrix application (Debian/Ubuntu)**
   - The `cmatrix` application will be installed. It is a program that emulates the display from "The Matrix" in terminal.

5. **Install required utilities (Debian/Ubuntu)**
   - Installs utility tools like `curl` and `jq` which are essential for data fetching and parsing.

6. **Create script file using copy module and insert content for MOTD and make it executable**
   - This task creates a script in `/etc/update-motd.d/` that fetches a quote from an API and displays it as the Message of the Day (MOTD) when users log into the server.

## Usage

To run the playbook:

```bash
ansible-playbook <playbook_filename>.yml
