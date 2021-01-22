# abtc-miner
A desktop miner for ABTC.

It's a free chance for everyone to join the mining party of Bitcoin on Ethereum.

## How to use it

### Preparation
1. Ethereum endpoint RPC

    Users should have Ethereum endpoint RPC, like infura.
    * How to get a Ethereum endpoint RPC? Register [infura](https://infura.io/) account, then you will have 3 free endpoint RPC.
    * The infura endpoint RPC should be http format, something like: `https://mainnet.infura.io/v3/bacd74e720210d858b29a1b5643fd3b3` (Don't use it, it just a example.)
   
2. Ethereum account with ETH

    Users need some ETH to pay gas when submit mined block. You need enough ETH to pay gas when you submit a mined block.


### Let's party!

1. Download miner

    There two platform supported right now: 
    * [Windows](https://github.com/Algorithmic-Bitcoin/abtc-miner/releases/download/0.2.0/abtc-miner-win-v0.2.0.zip) 
    
        (MD5: e8333e52a8279e3eeff6af585b545f44, SHA1: 33116b2432ee51b971d4e2e3c12dc92de642c08b)
    * [MacOS](https://github.com/Algorithmic-Bitcoin/abtc-miner/releases/download/0.2.0/abtc-miner-mac-v0.2.0.zip) 
    
        (MD5: c70872d8f1fddb44de79ed3c5afcb3d6, SHA1: e26884be1690b6eeb4e8ff992ff3723f1523775b)
    
    Download what suits for you.

2. Configure

    Unzip downloaded file, there will be a app named `miner.exe`(`miner` in Mac), and a configure file named `config.toml`. First open `config.toml` file you just unziped, it has 4 fields.
    
    `rpc` is what you applied above. It's important to remember that infura free service has a max of 100000 request per day, so if you run out of request, you should a new RPC endpoint so that you can continue, otherwise it will fail when you submit your mined block.
    
    `key` is your hex string format of private key, you should always handle your private key carefully, for a surcurity reason, you shouldn't have much ETH in your mining account, just some ETH that enough to pay the gas will do.
    
    `thread` is the number of how many miners do you want to mining on your computer, normally, it recommanded that you should keep this same as your computer's CPU kernel number, for example, if you have a 4 kernel CPU computer, you'd better set this parameter as 4.
    
    `interval` is how many seconds do you want your miner to check the latest information of the blockchain, it recommanded that you should not change this, excepte you are a expert of this.
    
3. Start mining

    Just come into your miner's path, execute `miner.exe`(`miner` in Mac) will do. Let your computer do the magic and hopefuly will get you a `ABTC`!
    
    When you found something like:
    ```
    *************Found!*************
    my nonce: xxx
    ```
    It means you just mined a block, and be rewarded of some ABTC coin.
    
 4. For Developers
 
    For users that prefer write their owne code, they can write mining code.
    
    We use `Keccak256` as POW hash algorithm, the target calculation forluma is: 
    ```
    keccak256(new_height, last_nonce, my_account, my_nonce) <= current_target
    ```
    
    The core code is determine if your calculated target is smaller than current target. The target changed every 6 blocks, which means 1 hours theoretically speaking.
    
    We implement Python implmentation for this:
    
    * [Python Miner](https://github.com/Algorithmic-Bitcoin/abtc-miner-python)

