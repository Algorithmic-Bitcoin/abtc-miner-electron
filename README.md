# abtc-miner
A desktop miner for ABTC.

It's a free chance for everyone to join the mining party of Bitcoin on Ethereum.

## How to use it

### Preparation
1. Ethereum endpoint RPC

    Users should have Ethereum endpoint RPC, like infura.
    * How to get a Ethereum endpoint RPC? Register [infura](https://infura.io/) account, then you will have 3 free endpoint RPC.
    * The infura endpoint RPC should be http format, something like: `https://kovan.infura.io/v3/bacd74e720210d858b29a1b5643fd3b3` (Don't use it, it is a)
   
2. Ethereum account with ETH

    Users need some ETH to pay gas when submit mined block.


### Let's party!

1. Download miner

    There two platform supported right now: Windows/MacOS. Download what suit for you.

2. Fill in RPC and private key

    RPC endpoint is what you applied above. It's important to remember that infura free service has a max of 100000 request per day, so if you run out of request, you should a new RPC endpoint so that you can continue, otherwise it will fail when you submit your mined block.
    
    Private key is your hex string format of private key, you should always handle your private key carefully, for a surcurity reason, you shouldn't have much ETH in your mining account, just some ETH that enough to pay the gas will do.
    
    Gas Price is optional, since low gas price could lead slow block confirm, which is a chance wasting. It recommanded that you should select `HIGH` gas price.
    
3. Start mining

    Just press the `START` button when you fill in above options. Let your computer do the magic and hopefuly will get you a `ABTC`!
      
4. Other

    * My address: Your address decoded from your private key
    * Target: Current target of POW difficulty
    * Height: Current height of POW
    * Balance: Your balance of ABTC, this will increase when you get more coin
    * Log: Some logs of mining events
    
 5. For Developers
 
    For users that prefer write their owne code, they can write mining code.
    
    We use `Keccak256` as POW hash algorithm, the target calculation forluma is: 
    ```
    target <= keccak256(new_height, last_nonce, my_account, my_nonce)
    ```

