{% hint style="tip" %}
We recommend completing both the [Solana 101 pathway](https://learn.figment.io/protocols/solana) and [Build a Solana Wallet](https://learn.figment.io/pathways/solana-wallet) before continuing. A working knowledge of [React hooks](https://reactjs.org/docs/hooks-intro.html) and [TypeScript/JavaScript](https://www.typescriptlang.org/) is also recommended.
{% endhint %}

# 🦺 Important information for your safety

During this Pathway, we will provide you with an opportunity to use the Solana [mainnet-beta cluster](https://docs.solana.com/clusters#mainnet-beta) (hereafter referred to as "mainnet") to perform token swaps with [Jupiter](https://jup.ag) - a liquidity aggregator for Solana. This means that **actual funds may be used**.

This is **not** a requirement for completing the Pathway & we have made sure to _clearly mark the difference_ between using a wallet containing **devnet SOL** and a wallet containing **mainnet SOL**. Be aware that during step [INSERT the step where we'll be asking them to do this] of the Pathway, you will be asked to input the private key of a **devnet only** wallet, which we will walk you through setting up.

{% hint style="tip" %}

<!-- Here we might call out that you should never share your private keys with anyone or any application and explain why this step is important for the pathway's workflow. We could even suggest here that the a simple approach would be to create a tutorial wallet that they can use with minimal security risk-->

{% endhint %}

<!-- I wonder if this next paragraph could be condensed and integrated in the tip above. When we say "in the event" does that mean I might choose to skip the section or do it differently? As a learner I feel like I have to remember this warning later and it puts the cognitive burden on me to do that. Adding the step in paragraph two above will help offload that a bit-->

Before proceeding, make sure you to understand that **in the event you provide the private key of a Solana account containing mainnet SOL to the wallet component in the Pathway, you are risking exposure of your wallet and someone might gain access to the full amount of SOL in that account**. Figment is not responsible for your losses in such a scenario, and we have made every effort to communicate the risks involved throughout the Pathway.

<!-- Is this last sentence a legal requirement on our end? If not, I'd be inclined to take it out since it erodes the learner's trust that we're trying to build at this point in the narrative -->

There is a wallet component used in step [INSERT step number] of the Pathway which has a toggle switch between "mock" and "live". When the toggle is set to "live", you will be able to provide a [Solana keypair private key](https://solana-labs.github.io/solana-web3.js/classes/Keypair.html). Solana keypairs can be created using the Solana CLI, or with the JavaScript API, or even by using a browser extension wallet such as [Phantom](https://phantom.app).

The most important consideration here is that in order to perform _any_ swaps on Solana mainnet using this project, you must:

- Own a funded account on mainnet containing an amount of SOL and the USDC SPL token (a United States Dollar stablecoin)
- Be on Step 6, "Token swaps on a DEX" or Step 7, "Liquidation bot implementation"
- Switch the wallet component from "mock" to "live" & also switch from devnet to mainnet, which will present you with an alert warning you that you're going live on mainnet with real economic exposure
- Copy and paste the private key of your funded account into the text input of the **live** wallet component

<!-- Maybe you should add something here like: If this doesn't quite make sense yet, don't worry. This is just a heads up and it will make much more sense in the context of the Pathway implementation.-->

---

# 🧑‍💻 Install the Pyth client

Install the TypeScript/JavaScript library for off-chain applications. This provides a tool to do things like displaying the Pyth price on a website. Whether you're using Gitpod or a local clone of the repo, the installation procedure is the same. Run the terminal command below inside the root directory of the project (`learn-web3-dapp/`) :

```text
yarn add @pythnetwork/client
```

This Pathway will only cover use of `@pythnetwork/client`. There are also Rust-, Python- and EVM-based clients. Refer to the [list of available client libraries](https://docs.pyth.network/consumers/client-libraries) in the Pyth documentation for more.

---

# 👻 Install the Phantom wallet extension

Turn your favorite browser into a Web 3 enabled crypto wallet!

Go to <https://phantom.app> and click on the "Add to ..." button which will auto-detect your browser and redirect you to the appropriate extension page:

- Firefox: https://addons.mozilla.org/en-US/firefox/addon/phantom-app/
- Chrome / Brave / Edge: https://chrome.google.com/webstore/detail/phantom/bfnaelmomeimhlpmgjnjophhpkkoljpa?hl=en

Optionally, check out <https://phantom.app/security> to learn more about the security features of Phantom.

---

# 🧩 DataHub API keys

To make use of the Pathway content, you will need a DataHub account and a valid API key to access Solana via DataHub's infrastructure. [Sign up for a DataHub account](https://datahub.figment.io/sign_up) and verify your email address.

To use your API key, you should copy the `.env.example` file in the root directory and call the copy `.env.local`. Check that you the file was duplicated succesfully at `/learn-web3-dapp/.env.local`

> Easily duplicate the file with the terminal command `cp .env.example .env.local`!

Find your unique API key on the [**DataHub Services Dashboard**](https://datahub.figment.io/). Click on the **Solana** icon in the list of available protocols, then copy your key as shown below:

![](https://raw.githubusercontent.com/figment-networks/learn-web3-dapp/main/markdown/__images__/solana/solana-setup-00.gif?raw=true)

<!-- Should we consider using a generic key or is this a DH account dedicated to tutorials? -->

You can then paste your unique API key into `.env.local`, as the value for the environment variable `DATAHUB_SOLANA_API_KEY`. This will authenticate you and enable you to make JSON-RPC requests to Solana via DataHub:

```yaml
# DataHub API keys
DATAHUB_AVALANCHE_API_KEY=
DATAHUB_CELO_API_KEY=
DATAHUB_NEAR_API_KEY=
DATAHUB_POLKADOT_API_KEY=
DATAHUB_POLYGON_API_KEY=
DATAHUB_SECRET_API_KEY=
DATAHUB_SOLANA_API_KEY=81436edcf907b0fbb8493d281cdff5af
DATAHUB_TEZOS_API_KEY=
```

---

# 👣 Next Steps

Once you have your Solana API key saved in `/learn-web3-dapp/.env.local`, you're ready to begin.
Click on the **Next: Connect to Pyth on Solana** button below.
