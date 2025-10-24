---
title: 27. ABI Encoding and Decoding
tags:
  - solidity
  - advanced
  - wtfacademy
  - abi encoding
  - abi decoding
---

# Solidity Minimalist Tutorial: 27. ABIEncode&Decode

`ABI`(Application Binary Interface) is the standard for interacting with Ethereum smart contracts. Data is encoded based on its type, and because the encoded result doesn't contain type information, it is necessary to indicate their types when decoding.

In Solidity, `ABI encode` has four functions: `abi.encode`, `abi.encodePacked`, `abi.encodeWithSignature`, `abi.encodeWithSelector`. While `ABI decode` has one function: `abi.decode`, which is used to decode the data of `abi.encode`.

In this chapter, We will learn how to use these functions.


---

**[Continue to full tutorial →](./step1/step1.md)**
