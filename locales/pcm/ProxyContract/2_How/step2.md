# How e dey work?

**EIP-7 DelegateCall** opcode allows a separate execution in another contract while maintain de original execution context.

All di **message calls** from de yuser go through a **Proxy contract**.

Di **Proxy contract** then will redirect them to the **Logic contract**.

When u need to **upgrade** the logic, you'll **just** deploy that - **HOWEVER** - the implementation of Proxy will remain di same.

U need update di address of logic contract in proxy.

Di proxy contract dey use **Delegate calls** and **Solidity assembly** because without it, it's impossible to return any value from **delegatecall**.
