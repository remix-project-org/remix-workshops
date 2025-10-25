---
title: S14. Block Timestamp Manipulation
tags:
  - solidity
  - security
  - timestamp
---

# WTF Solidity S14. Block Timestamp Manipulation

In this lesson, we will introduce the block timestamp manipulation attack on smart contracts and reproduce it using Foundry. Before the merge, Ethereum miners can manipulate the block timestamp. If the pseudo-random number of the lottery contract depends on the block timestamp, it may be attacked.



