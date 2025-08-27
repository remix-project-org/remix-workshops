# If to say we get state variables?

Thigs go dey more complicated once we suppose deal with state variables.  Dem dey save state variables go **storage**.

`storage`: is a mapping; each value stored there is persisted and saved on chain.

_Note: Statically-sized state variables (everything except mapping and dynamically-sized array types) are laid out contiguously in storage starting from position 0. Plenty contiguous items wey need less than 32 bytes go de one storage slot if e possible. For contracts wey dey use inheritance, dem de use C3-lineared order of contracts take determine the ordering of state variables starting with the most base-ward contract_

Once we execute **delegate call**, the storage of both contracts get **"merged"** into a single messy state.

We suppose **tell** proxy contract wetin the **state** of the **Logic contract** dey look like.

The way wey easy pass to do this one na to create **separate contract** wey go represent the **state** wey proxy contract go inherit from.
