---
title: Smart Contract Configuration Guide | UD Developer Portal
description: This guide covers how to set Reverse Resolution records for UD domains using smart contracts. This process requires using the ABIs implemented into the Unstoppable Domains UNS smart contract.
---

# Smart Contract Configuration Guide

This guide covers how to set Reverse Resolution records for UD domains using smart contracts. This process requires using the ABIs built into the Unstoppable Domains UNS smart contract.

## Step 1: Select a UNS Registry Smart Contract

The [UNS Registry](/developer-toolkit/reference/smart-contracts/uns-smart-contracts.md#unsregistry) contract is where domain owners store their data and is a map of domain namehashes to key-value dictionaries of records. Choose one of the Unstoppable Registry smart contracts to interact with (either mainnet or testnet).

<figure>

![Polygon testnet registry contract](/images/polygon-testnet-registry-contract.png)

<figcaption>polygon testnet registry contract</figcaption>
</figure>

## Step 2: Open the “Write as Proxy” Tab for the Registry Contract

Navigate to the `Contract` tab in either the Etherscan or Polygonscan page of the Registry contract and click on the `Write as Proxy` tab.

<figure>

![Polygonscan write as proxy tab](/images/polygonscan-write-as-proxy-tab.png '#width=50%')

<figcaption>polygonscan write as proxy tab</figcaption>
</figure>


## Step 3: Connect Your Web3 Wallet

Click on the `Connect to Web3` button in the `Write as Proxy` tab and connect the wallet associated with the domain:

<figure class="half-inline-block">

![Polygonscan connect wallet](/images/polygonscan-connect-wallet.png)

<figcaption>polygonscan connect wallet</figcaption>
</figure>

<figure class="half-inline-block">

![Wallet provider list](/images/wallet-provider-list.png)

<figcaption>wallet provider list</figcaption>
</figure>

## Step 4: Generate the Namehash of Your Domain

You can generate the [namehash](/getting-started/domain-registry-essentials/namehashing.md) of your domain using any of the [resolution libraries](/developer-toolkit/resolution-integration-methods/resolution-libraries/libraries-overview.md) or [CLI](/developer-toolkit/resolution-integration-methods/resolution-cli.md). You can also use [online tools](https://swolfeyes.github.io/ethereum-namehash-calculator/) to calculate the namehash of the domain.

<embed src="/snippets/_namehashing-snippets.md" />

## Step 5: Set the Reverse Record

The UNS contract has a `setReverse()` ABI method that takes in the namehash of a domain and sets its reverse record to your wallet address.

<figure>

![Polygonscan setReverse method](/images/set-reverse-abi.png)

<figcaption>polygonscan setReverse method</figcaption>
</figure>

Add the generated namehash of the domain you want to configure Reverse Resolution for in the `tokenId` field of the `setReverse()` method and click the `Write` button.

<figure>

![Polygonscan setReverse response](/images/set-reverse-response.png)

<figcaption>polygonscan setReverse response</figcaption>
</figure>

## Step 6: Execute the Contract

Click the `Write` button to sign the transaction and execute the contract.

<figure>

![Metamask sign transaction](/images/set-reverse-tx-sign.png '#width=50%')

<figcaption>metamask sign transaction</figcaption>
</figure>

After signing the transaction, you can view its details on the blockchain explorer, like so:

<figure>

![Reverse record adding transaction](/images/finished-adding-reverse-record.png)

<figcaption>reverse record adding transaction</figcaption>
</figure>

Now, applications that have integrated Reverse Resolution will be able to show the reverse record for your domains instead of your wallet address.

:::success Congratulations
You have successfully configured Reverse Resolution for your domain using smart contracts. Happy hacking!
:::

<embed src="/snippets/_discord.md" />
