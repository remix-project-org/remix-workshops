# If to say we get state variables?

Thigs go dey more complicated once we suppose deal with state variables.  Dem dey save state variables go **storage**.

'for where we dey keep tins' na mapping; wey value wey dem store dey persist and saved for onchain.

_Note: Statically-sized state variables (everything except mapping and dynamically-sized array types) are laid out contiguously for storage starting from position 0. Plenty contiguous items wey need less than 32 bytes go de one storage slot if e possible. For contracts wey dey use inheritance, dem de use C3-lineared order of contracts take determine the ordering of state variables starting with the most base-ward contract_

Once we don execute delegate call the storage for the two contract get merged into a single messy State.

We suppose **tell** proxy contract wetin the **state** of the **Logic contract** dey look like.

The way wey easy pass to do this one na to create **separate contract** wey go represent the **state** wey proxy contract go inherit from.
