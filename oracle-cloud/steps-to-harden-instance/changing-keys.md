# 🔑 Changing keys

Now that you have successfully connected as the **new user** through the **new port**, make a new ssh key. This should be done in a secure environment (eg air-gapped machine):&#x20;

```bash
# Make a new key
ssh-keygen -b 4096 -m PEM -f <the-name-of-your-key>.pem

# Remove the public key from your system
rm <the-name-of-your-key>.pub

# Change permissions on the key
chmod 400 <the-name-of-your-key>.pem

# Read and copy the public key
ssh-keygen -y -f <the-name-of-your-key>.pem
```

Paste the new public key on your VM:

```bash
# From your home directory do:
nano .ssh/authorized_keys

# Paste the public key in a second line and save
```

{% hint style="danger" %}
**Please note:** check that you can connect with the new key from a second terminal window before deleting your old key
{% endhint %}
