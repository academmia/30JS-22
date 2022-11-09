
> # OBIECTE

### Obiectele in JavaScript sunt dinamice. Pot fi modificate in orice moment, 
- putem sa adaugam proprietati noi sau putem sa stergem din cele existente.

#
### Ne vom lovi de obiecte la fiecare pas. 

---

#
### Cand adaugam proprietati noi, JavaScript foloseste o metoda interna `[[Put]]` 
- pentru a defini valori initiale si alte atribute ale proprietatilor.

#
### Cand se apeleaza metoda `[[Put]]` se creeaza o proprietate pe instanta (nu pe prototype) 
- si orice operatie asupra ei trebuie facuta prin obiectul respectiv.

#
### Cand modificam valoarea unei proprietati existente, se apeleaza o metoda interna `[[Set]]`


```js

    var person2 = new Object();     // 
    person2.name = "Daniel";        // [[PUT]] name
    person2.age = "110";            // [[PUT]] age
 
    person2.name = "Michael";       // [[SET]] name

```

---

> # Detectarea existentei proprietatilor 

### Proprietatile pot fi adaugate dinamic, 
- cu atat mai util este sa verificam existenta unei proprietati pe un obiect.
#
### Daca va ganditi la urmatoarea solutie, nu este chiar corect:

```js
    // nu da rezultatul corect de fiecare data
    if (person1.age) {
        // ...
    }
```
#
### JavaScript transforma orice expresie intr-o valoare booleana 
- atunci cand este asteptata o valoare booleana, asa cum este conditia de la if.

#
### Asa ca valori true sunt: `un obiect, un string care nu e gol, un numar diferit de 0, true`.

#
### Valori false sunt: `null, undefined, 0, NaN, un string gol, false`.

#
### Deci daca `person1.age` este `0, un string gol etc.` nu inseamna ca proprietatea nu este definita.

#
### Pentru a verifica existenta unei proprietati folosim operatorul `in`.

---

> # `Accesibila` instantei sau `pe` instanta


### Operatorul in are beneficul ca nu verifica valoarea proprietatii ci doar existena ei.

#
### Dar in verifica daca proprietatea este disponibila obiectului, 
- adica daca este pe instanta sau pe prototip.

#
### Pentru a verifica daca este doar pe obiect, 
- folosim o functie prezenta pe orice obiect: `hasOwnProperty()`

---

> # Stergerea proprietatilor


### Stergerea proprietatilor
    
`person1.name = null; // [[SET]] null - nu sterge proprietatea de pe obiect`

#
### Operatorul `delete` apeleaza metoda interna `[[Delete]]` care sterge proprietatea de pe instanta.

#
### Daca operatorul a reusit sa stearga proprietatea returneaza true.

---

> # Enumerable


### Implicit orice proprietate adaugata unui obiect are atributul intern `[[Enumerable]] === true`.

#
### Asta inseamna ca putem sa cream iteratii asupra lor: `for-in`.

#
### Daca vrem sa obtinem lista de proprietati avem la dispozitie functia 
`Object.keys()` care returneaza un array de proprietati:

#
### Cand avem nevoie de array de proprietati folosim `Object.keys()` altfel putem folosi `for-in`

#
### Dar mai este o diferenta:
- `Object.keys()` returneaza doar proprietatile de instanta
- `for-in` itereaza asupra proprietatilor de instanta si a celor din prototip.

---
> # `propertyIsEnumerable()`

### Nu toate proprietatile au [[Enumerable]] === true.
- De fapt majoritatea metodelor native de pe obiecte nu sunt enumerabile.

#
### Pentru a verifica daca o metoda este enumerabila folosim functia propertyIsEnumerable() care se afla pe orice obiect.

`person1.propertyIsEnumerable("name")`


---

> # Tipuri de proprietati

### Sunt doua tipuri de proprietati:

- ### proprietati de tip data 
    - (cele utilizate in mod normal si care contin o valoare; tipul implicit pentru [[Put]])

- ### proprietati de tip accesor 
    - (acestea nu contin o valoare ci definesc o functie care va fi apelata la citire(getter) 
    - si o functie apelata la scriere(setter) )

#
### Proprietatile de tip accesor pot defini oricare dintre functii sau ambele.

#
### Daca definim doar un getter atunci proprietatea devine read-only iar daca vrem sa scriem in ea, 
- in modul `nonstrict` nu se arunca eroare iar in modul `strict` vom avea eroare.

#
### Daca definim doar un setter atunci putem doar scrie in proprietate nu si citi, 
- nu vom avea eroare nici in modul `nonstrict` nici in modul `strict`.
---

> # Atribute ale proprietatilor


### Inainte de ES5 nu puteam sa modificam valorile atributelor interne ale obiectelor.


#
### Sunt doua atribute ale proprietatilor comune si celor de tip data si accesorilor:

- `[[Enumerable]]` - care determina daca proprietatea va fi inclusa 
    in interatiile asupra proprietatilor obiectului

- `[[Configurable]]` - determina daca o proprietate este modificabila. 
    O proprietate configurabila o putem sterge cu delete si putem sa-i modificam atributele.


#
### Implicit, toate proprietatile sunt si enumerabile si configurabile.


#
### Daca vrem sa modificam atributele proprietatilor, putem folosi `Object.defineProperty()`

#
### Aceasta asteapta trei parametri:

- obiectul
- proprietatea
- un obiect care contine atributele ce trebuiesc setate 
    - (numele proprietatilor nu contine [[]])

---

> # Citirea atributelor unei proprietati

### Folosind `Object.getOwnPropertyDescriptor()` putem sa aflam atributele proprietatilor de pe instanta.


