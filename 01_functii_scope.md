
> # SCOPE


### Contextul de executie in JavaScript este foarte important
#
### Contextul unuei variabile sau functii determina comportamentul si la ce date are acces
#
### Fiecare context de executie are un obiect asociat
- pe care se afla toate variabilele si functiile definite
#
### Cel mai cuprinzator context este cel global.
- In functie de gazda interpretorului JavaScript, acest context global poate sa difere.
#
### In web browsere contextul global este obiectul window
- deci toate variabilele si obiectele globale sunt atasate ca proprietati ale obiectului window

---

#
> # HOISTING

---

> # FUNCTII
#
### Functiile sunt de fapt obiecte.
#
### Ce le diferentiaza fata de celelalte obiecte este prezenta unei proprietati interne [[Call]]
#
### [[Call]] indica interpretorului JS ca acest obiect poate fi executat
#
### Daca verificam tipul unei functii, nu primim raspunsul object, ci function

---

> # Functii declarate versus Functii expresie

---

> # Functiile ca valori
#
### Putem folosi functiile ca orice alt obiect:

- le putem asigna variabilelor
- le putem adauga altor obiecte
- le putem trimite ca parametri altor functii
- le putem returna din alte functii
#
### Practic, oriunde am putea folosi un tip de referinta, putem folosi si functii.
#
### Aceasta capabilitate face din JavaScript un limbaj puternic si flexibil.

---

> # Parametri 

---

> # Overloading (!)

---

> # `this`

---

> # `call() apply() bind()`


### Aceleasi functii pot fi utilizate in contexte diferite.
#
### Chiar daca this este asignat automat in functie de context, putem sa-i modificam valoarea.
#
### Sunt trei functii metode cu care putem sa modificam valoarea lui this.

#
### `call()`
- ### call() poate executa o functie cu o valoare specificata pentru this.
#
- ### Primul parametru reprezinta valoarea lui this atunci cand este executata functia.
#
- ### Restul parametrilor sunt cei care vor fi trimisi mai departe functiei.

#
### `apply()`
- ### apply() este similar cu call() doar ca accepta doar doi parametri.
#
- ### Primul parametru este valoarea lui this.
#
- ### Al doilea parametru este un array (sau o lista) cu parametri cu care va fi chemata functia. 
- ### Putem sa folosim si obiectul arguments.

#
### `bind()`

- ### `bind()` se comporta diferit de primele doua metode. 
#
- ### Putem sa specificam o legatura permanenta intre functie si obiecte, 
    - sa specificam valoarea lui this si sa stabilim valori implicite ale parametrilor functiei, 
    independent pentru fiecare obiect.
#
- ### Primul argument este valoarea lui this.
#
- ### Orice alt argument reprezinta valoarea ce va fi atasata automat parametrilor 
    in ordine si care devin permanente. 

---

> # IIFE

---


