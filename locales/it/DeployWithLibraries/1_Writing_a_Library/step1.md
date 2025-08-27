Una libreria sembra un **contract** ma usa la parola chiave `library`

Una libreria è tipicamente una raccolta di funzioni utili presenti sulla blockchain che qualsiasi contratto può usare.  Poiché la libreria è già deployata, fa risparmiare i costi di deploy ai molti contratti che la utilizzano.

Nel contratto seguente:

- Crea una libreria con il nome `LibraryForTest`.

È possibile mettere una libreria nello stesso file con un altro contratto.  Quindi metti la libreria sotto il contratto.

Questa libreria dovrebbe avere un metodo chiamato `getFromLib` che restituisce `3`.

- Aggiorna il metodo `get` nel contratto `test` per usare la libreria `LibraryForTest`.   La funzione `get` dovrebbe restituire il valore che riceve da `getFromLib`.

---------

Puoi trovare maggiori informazioni sulle librerie in <a href="https://solidity.readthedocs.io/en/latest/contracts.html?highlight=library#libraries" target="_blank">questa sezione della documentazione di Solidity</a>.
