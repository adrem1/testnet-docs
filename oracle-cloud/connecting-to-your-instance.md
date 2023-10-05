---
description: Here we'll connect to the new instance for the first time
---

# ☁ Connecting to your instance

Open a Terminal session and connect to your new instance with the generated key:

```
# Connecting to your instance for the first time
ssh -i "<path-to-the-new-oracle-key>" ubuntu@<the-ip4-address-of-the-new-vm>
```

{% hint style="warning" %}
**Please note:** the default user for Ubuntu instances is "ubuntu" but this may differ for other OS.&#x20;
{% endhint %}
