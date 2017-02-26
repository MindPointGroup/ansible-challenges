This one is a simple . . . 
> ansible -m setup -i inventory <target>

Target can be an IP, hostname, or host as aliased by name or group in your inventory file.
If you do not specify an inventory file and do not have one in the default places that Ansible will look, then you can only run against localhost. In the example above, the file named inventory is located in the same directory as the command is run from.

The following answer is incorrect. The reason is that the ping module will not gather and display facts.
> ansible -m ping -i inventory <target>