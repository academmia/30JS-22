
> # Functii constructor


### Un constructor este o functie utilizata cu cuvantul cheie `new` pentru a crea un nou obiect.

#
### Obiectele create cu acelasi constructor contine aceleasi proprietati si metode.

#
### Constructorul este doar o functie, la fel ca orice alta functie.

#
### Pentru a le diferentia de o functie normala, prin conventie, denumirea incepe cu litera mare.

```js
    function Departament() {
        // ...
    }
```

#
### Dupa ce declaram constructorul, putem crea instante ale lui:

```js
    var dep1 = new Departament();
    var dep2 = new Departament();
```

#
### Daca nu avem parametri putem chiar sa omitem parantezele:

```js
    var dep1 = new Departament;
    var dep2 = new Departament;
```

#
### Chiar daca functia nu returneaza nimic, dep1 si dep2 sunt instante ale functiei Departament.

```js
    dep1 instanceof Departament; 
```

#
### dep1 si dep2 au fost create cu constructorul Departament asa ca vor avea proprietatea 

```js
    constructor == Departament;
```

#
### Daca vrem totusi sa verificam daca un obiect este o instanta a unei functii, folosim instanceof pentru ca proprietatea constructor poate fi suprascrisa.


#
### Orice proprietate si functie a constructorului va exista si pe instantele ei.
- Mai mult, putem folosi parametri la creare pentru a initializa valorile proprietatilor.

---

