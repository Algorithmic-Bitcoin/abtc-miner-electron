# abtc-miner-electron
A desktop miner for ABTC.

It's a free chance for everyone to join the mining party of Bitcoin on Ethereum.

* ABTC token address: 0xfa37a50da41b4b50e58186ddea3b6bb19b39a024

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
    * [Windows](https://github.com/Algorithmic-Bitcoin/abtc-miner-electron/releases/download/0.3.1/Miner-0.3.1.exe) 
    
        (MD5: 05af9cb5b055052807e2e9daf0a72e73, SHA1: 546f88edc791bfe64b9a880eaf1eb4fbe920202a)
    * [MacOS](https://github.com/Algorithmic-Bitcoin/abtc-miner-electron/releases/download/0.3.1/Miner-0.3.1.dmg) 
    
        (MD5: 666434a19f9df2146dc0db5e0391cf70, SHA1: 67700cf6bc232efbb7dd5a150eb2cf429abf6301)
    
    Chooese one what suits for you.

2. Configure

    Open miner application. There are 3 fields you should fill in.
    
    `RPC endpoint` is what you applied above. It's important to remember that infura free service has a max of 100000 request per day, so if you run out of request, you should a new RPC endpoint so that you can continue, otherwise it will fail when you submit your mined block.
    
    `Private key` is your hex string format of private key, you should always handle your private key carefully, for a surcurity reason, you shouldn't have much ETH in your mining account, just some ETH that enough to pay the gas will do.
    
    `Gas Price` is the gas price you provide when you submit mined blocks. It is recommended that you should always choose `HIGH` option for quick mining speed.
    
3. Start mining

    Just come into your miner's path, execute `miner.exe`(`miner` in Mac) will do. Let your computer do the magic and hopefuly will get you a `ABTC`!
    
    When you found something in `Log` like:
    ```
    You are lukcy!
    ```
    It means you just mined a block, and be rewarded of some ABTC coin.
    
 4. Other
 
    There are also some infos that are read only.
    
    `My Address` is your account parsed from your private key. You can check it to see if you import the right key.
    
    `Target` is current target of POW. Target and difficulty are opposite, while target be bigger, difficluty be smaller, vice versa.
    
    `Height` is current height of POW, it increases 1 per block. The average block time is 10 minutes theoretically speaking, just like *Bitcoin*.
    
    `Balance` is your ABTC balance, it changes when your balance changes. For example, you mined a block, or somebodu send you ABTC coin.
    
    `Log` prints something running logs during whole application.
 
 5. For Developers
 
    For users that prefer write their owne code, they can write mining code.
    
    We use `Keccak256` as POW hash algorithm, the target calculation forluma is: 
    ```
    keccak256(new_height, last_nonce, my_account, my_nonce) <= current_target
    ```
    
    The core code is determine if your calculated target is smaller than current target. The target changed every 3 blocks, which means 30 minutes theoretically speaking.

## Donation

Please denote ABTC to us at `0x276Fd60790e458df29D972cc8D83783350Bc0cc0`, which will be used for the early community promotion.

