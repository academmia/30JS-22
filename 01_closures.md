> # CLOSURES

### O functie declarata in interiorul altei functiei va avea access la scope-ul ei dar si la scope-ul parintilor.

#
### Functiile au spatiul lor privat in care pot contine variabile si functii (inner).

```js

    var a = "global variable";  // spatiu global, de aici nu vedem b si c
    var F = function () {       
        var b = "local variable" // spatiul functiei F, de aici nu vedem c dar vedem a
        var N = function () {
            var c = "inner local";    //spatiul privat N, vedem c, b si a
        };
    };

```

---


#
### `N` devine closure daca reuseste sa treaca de `F` si sa ajunga in spatiul global (sau un scope superior).
- ### Atunci `N` este in acelasi spatiu cu `a`.

#
### Functiile isi aduc aminte contextul in care au fost definite, 
- ### deci `N` inca va vedea spatiul `F`, deci poate accesa `b`.

#
### Deci ajungem la urmatorul fapt:

- ### Functia `N` este in contextul global si are access la spatiul `F` (poate accesa variabila `b`)
- ### Din acelasi context, global, nu se poate accesa spatiul lui `F` (`b` ramane invizibil)

#
### Aceste closures rup lantul normal stabilit de contextele functiilor inner.

#
### Cum reusesc functiile sa devina closures?

- ### Daca omitem declararea (nu folosim `var`, `let`) atunci functiile ajung in spatiul global (nerecomandat)
    - ### functioneaza in mediu `non strict`

#
- ### Daca functia care o contine o returneaza in spatiul global (sau parinte)

#
- ### Daca pre-declaram o variabila intr-un context parinte, si asignam functia acelei variabile.

---

> ## Primul exemplu:

```js
    var a = "global variable";
    var F = function () {
        var b = "local variable b";
        var N = function () {
            var c = "inner local";
            return b;   // N vede contextul lui F deci poate returna valoarea lui b
        };
        return N;       // returnam functia N
    };
    
    //spatiul global
    var inner = F();    // F returneaza functia N care acum va fi in spatiul global prin inner
    inner();
    "local variable b"    // functiile isi aduc aminte contextul unde au fost definite deci are access la b
```
---

> ## Al doilea exemplu

### Rezultatul va fi similar cu primul exemplu dar abordarea este diferita:

```js
    var inner; // initial declaram o variabila globala

    var F = function () {
        var b = "local variable b";
        var N = function () {
            return b;
        };
        inner = N;  // functia N este atasata variabilei globale
    };  
    F();
    inner();
    "local variable b"
```

In momentul cand a fost definita functia N era in interiorul lui F 
    deci are access la contextul lui F.

Chiar daca apoi se va regasi pe scopul global, va pastra aceasta legatura cu contextul de definire.


Deci un closure este creat atunci cand functia pastreaza un link catre contextul de definire 
    chiar daca s-a iesit din functia parinte.


Exemplu closure folosind parametri
    
        function F(param) {
            var N = function () {
                return param;
            };
            param++;    // param a fost incrementat dupa definitia functiei
            return N;
        }

        var inner = F(123); // la momentul definitiei param este 123 apoi este incrementat

        // functie closure pastreaza legatura cu contextul lui F deci va afisa noul param incrementat
        inner();    // 124