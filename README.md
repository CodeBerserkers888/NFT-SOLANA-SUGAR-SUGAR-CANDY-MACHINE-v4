<p align="center">
  <img src="https://i.imgur.com/ReG1HKH.png" alt="Logo">
</p>


  <h3 align="center">Solana NFT Candy Machine V3</h3>

  <p align="center">
    An Awesome ReadME Generator To Jumpstart Your Projects
    <br/>
    <br/>
    <a href="https://github.com/Bulli77/Solana NFT Candy Machine V3"><strong>Explore the docs »</strong></a>
    <br/>
    <br/>
    <a href="https://github.com/Bulli77/Solana NFT Candy Machine V3">View Demo</a>
    .
    <a href="https://github.com/Bulli77/Solana NFT Candy Machine V3/issues">Report Bug</a>
    .
    <a href="https://github.com/Bulli77/Solana NFT Candy Machine V3/issues">Request Feature</a>
  </p>
</p>

![Downloads](https://img.shields.io/github/downloads/Bulli77/NFT-SOLANA-SUGAR-SUGAR-CANDY-MACHINE-v4/total)
![Contributors](https://img.shields.io/github/contributors/Bulli77/NFT-SOLANA-SUGAR-SUGAR-CANDY-MACHINE-v4?color=dark-green)
![Stargazers](https://img.shields.io/github/stars/Bulli77/NFT-SOLANA-SUGAR-SUGAR-CANDY-MACHINE-v4?style=social)
![Issues](https://img.shields.io/github/issues/Bulli77/NFT-SOLANA-SUGAR-SUGAR-CANDY-MACHINE-v4)
![License](https://img.shields.io/github/license/Bulli77/NFT-SOLANA-SUGAR-SUGAR-CANDY-MACHINE-v4)



## Table Of Contents

* [About the Project](#about-the-project)
* [Built With](#built-with)
* [Getting Started](#getting-started)
  * [Prerequisites](#prerequisites)
  * [Installation](#installation)
* [Usage](#usage)

* [Authors](#authors)


## About The Project

![Screen Shot](images/screenshot.png)

Are you ready to launch your NFT collection on Solana? Metaplex's new tool, "Sugar", is the solution for you to get started quickly. "Sugar", the latest version of Metaplex's "Candy Machine", comes with several notable improvements including:

enhanced upload performance
streamlined UX
improved error handling.

## Built With

Nodejs installed (version 16.15 or higher)
Solana CLI installed
Phantom Wallet or Solflare extension installed 
Metaplex Sugar installed
A text editor

## Getting Started

This is an example of how you may give instructions on setting up your project locally.
To get a local copy up and running follow these simple example steps.

### Prerequisites

Setup and first steps....

in your terminal with:

```sh
mkdir sugar-demo
cd sugar-demo
```


### Installation

1. Get a free API Key at [https://example.com](https://example.com)

```sh
mkdir sugar-demo
cd sugar-demo
```


2. Mac

```<(curl -sSf https://sugar.metaplex.com/install.sh)
```

3. Windows Installation

Download the windows installer from the provide LINK<
Right-click on the installer file and select "Run as Administrator"
If you receive a warning about an untrusted binary, try clicking "More Info" and then "Run Anyway"
If you don't have the "Run Anyway" option:
Right-click on the executable file and go to Properties
If you trust the Metaplex developer team, check the "Unblock" button as shown in the image
Click "Apply" and "Ok"
Run the installer again

4. Setting Up a New Wallet

One of the great features of Sugar is that it allows you to set your wallet and RPC configurations using Solana CLI, so that you don't need to re-enter them in each of your Sugar commands.

To get started, we'll create a new wallet for devnet testing with the following command:

```sql
solana-keygen new --outfile ./wallet.json```
Note that you can skip entering a password (by hitting Enter) as this wallet will only be used on devnet, so the funds are not important.

To confirm that the Solana CLI is using the wallet we just generated, run the following command:

```arduino
Copy code
solana config set --keypair ./wallet.json
```

5. Verifying Solana CLI Connection

We need to make sure that our Solana CLI is connected to a node. You can use public nodes or manage your own infrastructure, but if you'd like faster response times, you can leave the heavy lifting to "USE QUICKNODE RPC".

With your endpoint set up on the Solana Devnet, you can run the following command, replacing YOUR_QUICKNODE_URL with the HTTP URL you've copied:

```solana config set --url YOUR_QUICKNODE_URL```

To fund your wallet, you can run the following command:

```solana airdrop 1```

## Preparation of NFT Assets

If you have previously used Candy Machine, this process will be familiar to you. We need to create a .json file for each digital asset using a simple numerical format, starting with 0 and incrementing sequentially without skipping any numbers (e.g. 0.json maps to 0.png, followed by 1.json mapping to 1.png). Additionally, we have the option to create a collection.json and collection.png, which will allow Sugar to automatically create an on-chain collection.



## Usage

Configure Candy Machine

Create a new file, config.json in your root project folder:

```bash echo > config.json```

Open the file and paste this config: 

```
{
  "price": 0.01,
  "number": 10,
  "symbol": "NB",
  "sellerFeeBasisPoints": 500,
  "gatekeeper": null,
  "solTreasuryAccount": "YOUR_WALLET_ADDRESS",
  "splTokenAccount": null,
  "splToken": null,
  "goLiveDate": "2022-07-24T00:00:00Z",
  "endSettings": null,
  "whitelistMintSettings": null,
  "hiddenSettings": null,
  "uploadMethod": "bundlr",
  "awsS3Bucket": null,
  "retainAuthority": true,
  "isMutable": true,
  "creators": [
    {
      "address": "YOUR_WALLET_ADDRESS",
      "share": 100
    }
  ]
}
```


NOTE: you can run solana address in your terminal to obtain the wallet address that you just created.

## Now, we should be all set. If you're following along to this point you should have a directory structure like this: 

```
sugar-demo/wallet.json
sugar-demo/config.json
sugar-demo/assets/[0-9].png
sugar-demo/assets/[0-9].json
sugar-demo/assets/collection.png
sugar-demo/assets/collection.json
```

Sugar has a built in validation error that will let us check for any errors before we proceed. In terminal, run: 

```sugar validate```

Create Candy Machine

Because we've set our RPC and wallet using Solana CLI and because we've saved our assets and config.json to Sugar's default directories, our commands will be quite simple! 

Upload Your Assets
In your terminal enter:

```sugar upload```

Deploy Candy Machine
In your terminal enter:

```sugar deploy```


If you get a "Blockhash not found" error, try running the command again.

Make sure to store the Candy Machine ID provided in your terminal locally. We'll need this later.

Verify Candy Machine

Let's make sure everything has worked as we'd expected. In your terminal enter:

```sugar verify```


Test Your Candy Machine
Try minting an NFT using sugar. In your terminal enter:

```sugar mint```


Set Up a Minting Site

For the easiest possible set up, we will be using the front end that Metaplex provides us, Candy Machine UI. 

From your project directory, in your terminal enter: 

```
git clone https://github.com/metaplex-foundation/candy-machine-ui ./candy-machine-ui/
cd candy-machine-ui
```

Rename the file .env.example to .env. After changing the file name, you can change the values in there to the following:

```
REACT_APP_CANDY_MACHINE_ID=<YOUR_CANDY_MACHINE_PUBKEY>
REACT_APP_SOLANA_NETWORK=devnet
REACT_APP_SOLANA_RPC_HOST=<YOUR_QUICKNODE_DEVNET_ENDPOINT>
```

If you don't remember your Candy Machine ID, you should be able to find it in cache.json in the program.candyMachine field. 

With all of that information plugged in, you can now save the file. From that candy-machine-ui folder, run the following commands:

```
yarn install
yarn start
```

This will open up a browser at localhost:3000, where you can connect your wallet and have the ability to mint an NFT. Confirm that your Phantom Wallet is set to devnet and not mainnet before proceeding.

You'll need devnet SOL in your Phantom wallet to mint an NFT. You can use Solana CLI to airdrop to your Phantom wallet by entering this command in your terminal: 

```
solana airdrop 1 YOUR_PHANTOM_WALLET_ADDRESS
```

Once you're ready, click "Mint". If done successfully, you should see a website like this:

Candy Machine Mint Page

If you see an error that says “Mint Failed”, you might not have enough funds. Try again once you’ve added funds. You can view the NFT in your wallet after purchasing. Phantom may take a moment before rendering the NFT in your wallet.




### Creating A Pull Request

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request


## Authors

**Autor**

- [How to Create a Solana NFT Collection using Candy Machine v3 and TypeScript](https://www.quicknode.com/guides/solana-development/nfts/how-to-create-a-solana-nft-collection-using-candy-machine-v3-and-typescript/)
