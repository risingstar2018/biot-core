# biot-core

## Unstable! Use testnet only.

##### How to experience it?
```sh
$ npm install
$ cd examples
$ node balance.js
```


##### Docs
```sh
$ npm run docs
```

---
---

### Steps of channel work.
A -> B

#### Opening of channel 
1) **A:** await_get1Contract
2) **B:** get1Contract
3) **B:** await_get1Contract
4) **A:** await_getInputsAndAddresses
5) **B:** await_createChannel
6) **A:** waiting_transfers
7) **B:** waiting_transfers


#### Transfer
1) **A:** waiting_reverse_transfer
2) **B:** waiting_transfer
3) **B:** waiting_reverse_transfer
4) **A:** waiting_transfer
5) **A:** waiting_transfers
6) **B:** waiting_transfers


#### closeOneSide
1) **A:** waiting_mci
2) **A:** close


#### closeMutually
1) **B:** await_closing
2) **A:** mutualClose
3) **B:** mutualClose

---

### Messages in channel

#### Opening of channel 
1) **A:** get1Contract
2) **B:** 1Contract
3) **A:** getInputsAndAddresses
4) **B:** inputsAndAddresses
5) **A:** channelAddress

#### Transfer
1) **A:** transfer_start
2) **B:** transfer_end
3) **A:** pass
5) **B:** pass

#### closeOneSide
Nothing is sent

#### closeMutually
1) **A:** close