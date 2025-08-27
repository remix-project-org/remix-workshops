Di `visibility` wey dey specify dem dey use take control who get access to functions wit state variables.

E get four type of visibility wey dey: `external`, `public`, `internal`, and `private`.

Dem dey regulate if function wit state variable dem fit call am form inside di contrakt, na from contrakt wey dey come from di contrakt (pikin contrakt) or na from oda contrakt wit transakshion.

### inside

- Dem fit call am from di contrakt

### inside

- Dem fit call am from insid di contrakt
- Dem fit call am from child contrakt

### outside

- Dem fit call am from insid di contrakt
- Dem fit call am from insid di contrakt
- Dem fit call am from oda contrakt or transacshon

### outside

- Dem fit call am from oda contrakt or transacshon
- State variables no fit b from outside

For dis exampu we get two contrakts, di base contrakt and di pikin contrakt (line 55) wey dey collect di function and state variable from di base contraks.

Wen you commot wetin you talk di `testPrivateFunc` (lines 58-60) you go see error unto say di pikin contrakt no get access go di private function `privateFunc` from di `Base` contract.

If you go compile come scatta di two contrak you no go fit to call di funkshon `privateFunc` and `internalFunc` directly. You go fit call dem onli wit testPrivateFunc and testInternalFunc.

<a href="https://www.youtube.com/watch?v=NBzQVJ6OrrQ" target="_blank">Ho see video tutorial for visibility</a>.

## di ⭐️ Assignment

Make new function for di Child contract wey dem go call testInternalVar. Dat function go return all the state variables wey dey inside the Base contract wey e possible to return.