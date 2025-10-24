---
title:  19. Receive ETH
tags: 
  - solidity
  - advanced
  - wtfacademy
  - receive
  - fallback
---

# WTF Solidity Tutorial:  19. Receive ETH,  receive and fallback

`Solidity` has two special functions,  `receive()` and `fallback()`, they are primarily used in two circumstances.
1. Receive Ether
2. Handle calls to contract if none of the other functions match the given function signature (e.g. proxy contract)

Note⚠️: Prior to solidity 0.6.x, only `fallback()` was available, for receiving Ether and as a fallback function.  
After version 0.6,  `fallback()` was separated to `receive()` and `fallback()`. 

---

**[Continue to full tutorial →](./step1/step1.md)**
