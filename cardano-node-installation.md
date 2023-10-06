---
description: Now you can proceed with cardano-node and -cli installation as usual
---

# 🪢 Cardano node installation

Excellent guides exist about this, so no need for repetition. Please refer to [Coincashew](https://www.coincashew.com/coins/overview-ada/guide-how-to-build-a-haskell-stakepool-node#7-create-startup-scripts) for more information.&#x20;

{% hint style="info" %}
**Pre-compiled binaries** for ARM-based architectures have been provided by the lovely bunch at[ Armada Alliance](https://armada-alliance.com/), and can be found [here](https://github.com/armada-alliance/cardano-node-binaries). &#x20;
{% endhint %}

### Testnet environment node configuration files:

<table data-full-width="false"><thead><tr><th>Preview</th><th>Preprod</th></tr></thead><tbody><tr><td><a href="https://book.world.dev.cardano.org/environments/preview/config.json">Config</a></td><td><a href="https://book.world.dev.cardano.org/environments/preprod/config.json">Config</a></td></tr><tr><td><a href="https://book.world.dev.cardano.org/environments/preview/topology.json">Topology</a></td><td><a href="https://book.world.dev.cardano.org/environments/preprod/topology.json">Topology</a></td></tr><tr><td><a href="https://book.world.dev.cardano.org/environments/preview/byron-genesis.json">Byron-genesis</a></td><td><a href="https://book.world.dev.cardano.org/environments/preprod/byron-genesis.json">Byron-genesis</a></td></tr><tr><td><a href="https://book.world.dev.cardano.org/environments/preview/shelley-genesis.json">Shelley-genesis</a></td><td><a href="https://book.world.dev.cardano.org/environments/preprod/shelley-genesis.json">Shelley-genesis</a></td></tr><tr><td><a href="https://book.world.dev.cardano.org/environments/preview/alonzo-genesis.json">Alonzo-genesis</a></td><td><a href="https://book.world.dev.cardano.org/environments/preprod/alonzo-genesis.json">Alonzo-genesis</a></td></tr><tr><td><a href="https://book.world.dev.cardano.org/environments/preview/conway-genesis.json">Conway-genesis</a></td><td><a href="https://book.world.dev.cardano.org/environments/preprod/conway-genesis.json">Conway-genesis</a></td></tr></tbody></table>

The full complement of configuration files is available [here](https://book.world.dev.cardano.org/environments.html).

{% hint style="danger" %}
**Please note:** aside from getting the correct configs, you must remember to assign the --testnet-magic \<natural> flag instead of --mainnet whenever needed.&#x20;
{% endhint %}

{% hint style="danger" %}
**Please note:** for your nodes to communicate correctly you will need to add the node port you assign during the build, both to firewalld and OCI Security List. [This is similar to what you did for ssh here](oracle-cloud/steps-to-harden-instance/change-ssh-port.md).
{% endhint %}

{% hint style="success" %}
**Success:** once you are done with your first node, rinse and repeat for the others.&#x20;
{% endhint %}
