# De Delegate call

Na special variant for **message call**, which dey identical to di message call apart from do fact say do code for di target address dey executed for di context of di calling contract so **msg.sender** and **msg.value** no dey change their values.

Dis mean say contract fit dynamically load code for different addresss at runtime.

De storage, de current address and balance fit still refer the calling contract, na only the code go take from the called address.

So when **Proxy** delegates calls con di Logos contract, all di storage modification go impact di storage for Logic contract.