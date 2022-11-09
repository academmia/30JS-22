> # Proprietatea Prototype

#
### Aproape orice functie (exceptie fac cateva functii built-in) au o proprietate `prototype`  

#
### Acel `prototype` este accesibil oricaror instante a obiectului. 
- ### Toate instantele pot accesa proprietatile prototipului.

#
### Exemplu: 
- ### In JavaScript exista obiectul generic `Object` care are si el o proprietate `prototype`

- ### Acest obiect prototype are printre alte metode si metoda `hasOwnPropery("denumireProprietate")` 
    - care verifica daca pe instanta exista o proprietate cu numele specificat:

---

> # `[[Prototype]]`   


### O instanta are o proprietate interna cu ajutorul careia tine o referinta catre obiectul `protoype` pe care il foloseste ( `[[Prototype]]` ).

#
### Cand cream un nou obiect folosind `new`, proprietatea `prototype` a constructorului este asignata proprietatii `[[Prototype]]` a noii instante.


#
### Putem citi valoarea proprietatii `[[Prototype]]` folosind functia `Object.getPrototypeOf()`

#
### Putem folosi functia `isPrototypeOf()` pentru a verifica daca un obiect este prototipul altui obiect:

#
### Atunci cand accesam o proprietate a unui obiect (`departament.denumire`) 
- ### JavaScript verifica daca obiectul are o astfel de proprietate definita; 

- ### Daca nu gaseste atunci cauta prototipul obiectului 
    - si verifica din nou existenta proprietatii pe obiectul prototip.   

- ### Daca nici pe prototip nu o gaseste atunci returneaza undefined.

---

