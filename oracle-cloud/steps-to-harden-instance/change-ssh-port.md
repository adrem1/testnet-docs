---
description: >-
  Compared to other Clouds, OCI requires some extra steps to avoid getting
  locked out.
---

# 🚪 Change ssh port

From the **OCI control panel** navigate to **Compute > Instances** and **select your instance**. You should see something like this:

<figure><img src="../../.gitbook/assets/oracle09.png" alt=""><figcaption></figcaption></figure>

Click on the **subnet**:

<figure><img src="../../.gitbook/assets/oracle10.png" alt=""><figcaption></figcaption></figure>

Next, either make a new **Security List**, or simply edit the **Default**:

<figure><img src="../../.gitbook/assets/oracle11.png" alt=""><figcaption></figcaption></figure>

Add a new **Ingress Rule**:

<figure><img src="../../.gitbook/assets/oracle12.png" alt=""><figcaption></figcaption></figure>

In the following panel enter the required information:

* **Source Type:** CIDR
* **Source CIDR:** either 0.0.0.0/0 or \<the-ip-you'll-be-connecting-from>/32
* **IP Protocol:** TCP
* **Destination Port Range:** \<the-port-you-want-to-use-for-ssh>
* **Description:** something that makes sense to you

{% hint style="danger" %}
**Please note:** DO NOT delete the default SSH (port 22) Ingress Rule at this point
{% endhint %}

<figure><img src="../../.gitbook/assets/oracle13.png" alt=""><figcaption></figcaption></figure>

Next, connect to your instance as you did [here](../connecting-to-your-instance.md) and change SSH port on the VM:

```sh
# Edit the ssh configuration file
sudo nano /etc/ssh/sshd_config

# Find the line that says #Port 22 and replace it with:
Port <the-port-you-selected-earlier>

# Save your changes and reload the daemon
sudo systemctl restart sshd
```

More details about this process can be found [here](https://www.ubuntu18.com/ubuntu-change-ssh-port/).

{% hint style="danger" %}
**Please note:** you must include the following steps for this to work in OCI
{% endhint %}
