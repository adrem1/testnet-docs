---
description: Let's create our first VMs on OCI to run Testnet nodes.
---

# ☁ Provisioning your instances

{% hint style="info" %}
**Please note:** OCI does not support this documentation in any way, financial or otherwise.
{% endhint %}

Sign into your account and navigate to **Compute > Instances**:

<figure><img src="../.gitbook/assets/oracle01.png" alt=""><figcaption></figcaption></figure>

**Choose your compartment** (you should have the _root_ one, created on sign-up):

<figure><img src="../.gitbook/assets/oracle02.png" alt=""><figcaption></figcaption></figure>

Your compute console will look slightly different: I have removed info regarding my account to avoid any confusion. Click **Create Instance**:

<figure><img src="../.gitbook/assets/oracle03.png" alt=""><figcaption></figcaption></figure>

First, give your instance a meaningful **name** (eg Preview-Relay) and then click **Edit** on **Image and Shape:**

<figure><img src="../.gitbook/assets/oracle04.png" alt=""><figcaption></figcaption></figure>

**Change Image** to choose you favourite Linux flavour (Ubuntu 20.04 in this example) and then **Change Shape** to create a Standard VM (A1.Flex) with 1 CPU and 6 GB of RAM:&#x20;

<div>

<figure><img src="../.gitbook/assets/oracle05.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../.gitbook/assets/oracle06.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../.gitbook/assets/oracle07.png" alt=""><figcaption></figcaption></figure>

</div>

{% hint style="info" %}
You can leave the networking options set to default (**Primary and Secondary VNIC**)
{% endhint %}

Let OCI **generate a key-pair for you** (you will be changing this later anyway) and set your desired **boot disk** preferences (50 GB should suffice to start):

<figure><img src="../.gitbook/assets/oracle08.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
If you already have keys that you'd rather use, go ahead. The one OCI generates will be throw-away anyway, as we'll be making new keys.&#x20;
{% endhint %}

{% hint style="success" %}
**Success:** click on **Create** and wait for the your new instance to provision.
{% endhint %}
