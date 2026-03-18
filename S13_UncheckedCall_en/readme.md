---
title: S13. Unchecked Low-Level Calls
tags:
    - solidity
    - security
    - transfer/send/call
---

# WTF Solidity S13. Unchecked Low-Level Calls

In this lesson, we will discuss the unchecked low-level calls in smart contracts. Failed low-level calls will not cause the transaction to roll back. If the contract forgets to check its return value, serious problems will often occur.



