# 👪 Create new user and remove default one

First add a new user and give it superuser privileges:

```sh
# Create a new user
sudo adduser <your-chosen-username>

# Add the new user to the sudoers list
sudo visudo 

# In the editor add a new line that looks like this:
<your-chosen-username> ALL=(ALL:ALL)ALL

# Log on as the new user 
su -l <your-chosen-username>

# Check superuser privileges
sudo apt update # (or any other command)
```

On you local machine, find the public key:

```sh
# Do this, and copy the output
ssh-keygen -y -f <path-to-the-new-oracle-key>
```

On your VM, paste the public key to the correct file:

```sh
# Do this from the new user home
mkdir .ssh
touch .ssh/authorized_keys
nano .ssh/authorized_keys # paste the public key here  
```

{% hint style="danger" %}
Before disconnecting your current session from the VM, open a new terminal window and try to connect as the new user with the old key, to check that everything worked.
{% endhint %}

```sh
# Connecting to your instance for the first time
ssh -i "<path-to-the-new-oracle-key>" <your-chosen-username>@<the-ip4-address-of-the-new-vm>
```

Once connected as your new user, delete the old one:

```
sudo deluser --remove-home <ubuntu-or-other-default-user>
```

For more details about this process, refer to this [Digital Ocean document](https://www.digitalocean.com/community/tutorials/how-to-add-and-delete-users-on-ubuntu-18-04).
