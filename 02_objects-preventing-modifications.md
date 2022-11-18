> # Prevenirea modificarilor


### Obiectele, la fel ca proprietatile, au atribute interne care le dicteaza comportamentul.

#
### Un exemplu este atributul `[[Extensible]]`, 
    - o valoare booleana care specifica daca obiectul este modificabil.

#
### Toate obiectele create sunt implicit extensibile.

#
### Putem preveni adaugarea de noi proprietati obiectelor in trei moduri:


#
> ## `Object.preventExtensions()`

- ### Metoda asteapta un singur argument: obiectul pe care il vrem non-extensibil.
#
- ### Odata ce am utilizat aceasta metoda pe un obiect, nu mai putem sa adaugam proprietati.
#
- ### Putem verifica daca un obiect este extensibil folosind metoda `Object.isExtensible()`.

---

> ## Sigilarea obiectului: `Object.seal()`


### A doua metoda de a opri modificarea unui obiect este sigilarea lui.

#
### Prin sigilare nici nu putem adauga dar nici sterge sau modifica proprietatile existente.

#
### Daca un obiect e sigilat putem sa scriem si sa citim valorile proprietatilor.

#
### Pentru a sigila un obiect folosim metoda `Object.seal()`.
#

### Aceasta modifica atributul [[Extensible]] sa fie false 
- ### iar toate proprietatile vor avea `[[Configurable]] === false`.

---

> # Inghetarea obiectelor: `Object.freeze()`


### A treia modalitate de a opri modificarile asupra obiectelor este prin folosirea metodei `Object.freeze()`

#
### Putem verifica daca un obiect este inghetat cu metoda Object.isFrozen()

#
### Un obiect inghetat este un obiect sigilat dar care are si proprietatile read-only.

#
### Obiectele inghetate nu mai pot reveni la starea dinainte de inghetare.

