# abtc-miner-electron
A desktop miner for ABTC.

It's a free chance for everyone to join the mining party of Bitcoin on Ethereum.

* ABTC token address: 0xFa37A50DA41B4B50E58186ddeA3B6BB19b39A024, you can refer to [HECO chain explorer](https://scan.hecochain.com/token/0xfa37a50da41b4b50e58186ddea3b6bb19b39a024).

## How to use it

### Preparation
   
1. HECO account with HT

    Users need some HT to pay gas and mining fee when submit mined block. You need enough HT to pay gas when you submit a mined block.
    
    It is recommanded to use [wallets](https://www.hecochain.com/en-us/wallet) that HECO suggests.


### Let's party!

1. Download miner

    There two platform supported right now: 
    * [Windows](https://github.com/Algorithmic-Bitcoin/abtc-miner-electron/releases/download/v0.4.0/Miner-0.4.0.exe) 
    
        (MD5: 26d44fd375a8f6b605a4af4c89c57091, SHA1: 21b8a2464869b087f538dd0e289990938ae0bb43)
    * [MacOS](https://github.com/Algorithmic-Bitcoin/abtc-miner-electron/releases/download/v0.4.0/Miner-0.4.0.dmg) 
    
        (MD5: 85774ae65bac4c95703e42a715b2120b, SHA1: 1cc0c20fc928b5338c923ab0be32d92412d198bf)
    
    Chooese one what suits for you.

2. Configure

    Open miner application. There are 2 fields you should fill in.
    
    `Private key` is your hex string format of private key, you should always handle your private key carefully, for a surcurity reason, you shouldn't have much HT in your mining account, just some HT that enough to pay the gas will do.
    
    `Process number` is how many miners your application to start, it is recommended that you should set it as your CPU proccer's number.
    
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
    
    `Height` is current height of POW, it increases 1 per block. The average block time is 1 minutes theoretically speaking.
    
    `Mine Fee` is current mining fee of POW, it is decided by DAO, and is used for buy ABTC in ABTC/WBTC pair.
    
    `ABTC Balance` is your ABTC balance, it changes when your balance changes. For example, you mined a block, or somebodu send you ABTC coin.
    
    `Log` prints something running logs during whole application.
 
 5. For Developers
 
    For users that prefer write their owne code, they can write mining code.
    
    We use `Keccak256` as POW hash algorithm, the target calculation forluma is: 
    ```
    keccak256(new_height, last_nonce, my_account, my_nonce) <= current_target
    ```
    
    The core code is determine if your calculated target is smaller than current target. The target changed every 6 blocks, which means 6 minutes theoretically speaking.
