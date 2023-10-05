---
description: After our first connection we'll harden our instance to make it more secure.
---

# ☁ Steps to harden instance

There are many good resources on this topic, which I will link, other than repeating everything and reinventing the wheel.&#x20;

{% hint style="danger" %}
However, please pay attention to the **Hints**, as these highlight OCI-specific quirks that if left unchallenged will make server communications very difficult and lock you out of your instance!
{% endhint %}

### First hardening steps

At the very least, before going any further, you should:

* Update your system
* Disable the _root_ account
* Add some SWAP

If you don't know how to do these things, please refer to [this guide](https://gist.github.com/lokhman/cc716d2e2d373dd696b2d9264c0287a3).&#x20;

### Create new user and remove default one

First add a new user and give it superuser privileges:

```
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

```
# Do this, and copy the output
ssh-keygen -y -f <path-to-the-new-oracle-key>
```

On your VM, paste the public key to the correct file:

```
# Do this from the new user home
mkdir .ssh
touch .ssh/authorized_keys
nano .ssh/authorized_keys # paste the public key here  
```

{% hint style="info" %}
Before disconnecting your current session from the VM, open a new terminal window and try to connect as the new user with the old key, to check that everything worked.
{% endhint %}

Once connected as your new user, delete the old one:

```
sudo deluser --remove-home <ubuntu-or-other-default-user>
```

For more details about this process, refer to this [Digital Ocean document](https://www.digitalocean.com/community/tutorials/how-to-add-and-delete-users-on-ubuntu-18-04).
