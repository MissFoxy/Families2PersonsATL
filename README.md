### Appunti

Esercizio svolto da Giulia Pascale e Gabriele Benedetti @Betto94

Tutorial link: https://wiki.eclipse.org/ATL/Tutorials_-_Create_a_simple_ATL_transformation#The_ATL_transformation_code

Trasformiamo un modello in un altro, ma per farlo ci occorre i metamodelli di entrambi affinché possiamo fare una sorta di traduzione (ma è più corretto dire trasformazione)..

In questo esercizio la source è Families e il target è Person.

- Nella cartella Metamodels abbiamo i metamodelli di Families.ecore e Persons.ecore. Notare che le modifiche sono state effettuate in proprietà e sono svariate.

## Il codice ATL si occupa della transformazione

- helper: sono funzioni che ci serviranno dopo nella rules
	- context Families!Member: prende in input un booleano, ci serve per capire se è un uomo o una donna. Lo fa verificando se il membro è una madre o una figlia, restituendo false nel caso contrario
	- context Families!Member: il secondo ha lo stesso nome ma prende in input una stringa. Restituisce il cognome.  It must look for it in every reference to the family, to see which one is defined (familyFather, familyMother, familySon or familyDaughter)

- rules: 
	- Dubbio esistenziale: perché scrive Person:Male e Family:Member? perché una è una classe che compone/eredita l'altra?
	
.
