#Phase 1: Basic Commands

##Module 1: Intro to ansible
**Goal**: Use ansible to connect to a remote host and gather facts using a one-liner.

**What You Will Learn**: Learn how to use the ansible command to run a module, specify a host, and print facts regarding the host. This is a pretty basic task, but you will potentially hit issues including:
  - Ansible is asking me if I want to accept the key for the remote host. If you run a playbook against multiple hosts, this can be a problem.
  - Ansible cannot connect to the remote host. This is probably due to it logging in as the wrong user, with the wrong key (identity file), or some other basic SSH issue.

**Where to Go From Here**: Try running the command against multiple hosts at once. Try grepping through the results to see if you can find details about the remote host(s) such as the OS distribution, version, network interfaces, etc.

<br>
##Module 2: Getting to know ansible-playbook
**Goal**: Use ansible-playbook to run a very simple playbook (support_files/p1m2.yml) against a *single* host.

**What You Will Learn**: Learn how ansible-playbook works, specifying and using an inventory file, and limiting the playbook run to certain hosts. You will most likely run into the following problems:
  - Not having an inventory specified when you run the playbook.

**Where to Go From Here**: Try running p1m2b.yml against the same host. This file is purposely designed to include mistakes, which you will need to fix in order to get it to run successfully.

<br>
##Module 3: Using ansible-vault
**Goal**: Carry out the following tasks:
  1. Create a file with vi and put some text in it (doesn't matter what).
  2. Encrypt the file created above with ansible-vault.
  3. Once the file is saved, open it with vi again. You should see a header indicating that the file is encrypted with AES.
  4. Now, close the file and reopen it for editing with ansible-vault. Make some change and save it again.
  5. Permanently decrypt the file with ansible-vault.
  6. Once the file is decrypted, open it with vi again. You should see the plaintext file including the changes you made in step 4.

**What You Will Learn**: Get familiar with ansible-vault as it will allow you to incorporate files with sensitive data into your playbooks while keeping that data protected.

**Where to Go From Here**: In later phases/modules, we will use ansible-vault to create a file with variables representing passwords, and include them in playbooks.

<br>
##Module 4: The .ansible.cfg file
**Goal**: Create the simplest ansible config file possible to avoid problems from here on out.

**What You Will Learn**: Understand some key things about .ansible.cfg without getting bogged down understanding 200 different knobs and levers.

**Where to Go From Here**: Once you understand the basics of this file, you can use it later as necessary.

