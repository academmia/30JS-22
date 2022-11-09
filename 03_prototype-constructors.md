
> # Prototype si Constructorii


### O metoda creata pe `prototype` devine disponibila pentru toate obiectele de un anumit tip.

#
### In general, metodele fac acelasi lucru pentru toate instantele, asa ca nu este nevoie ca instantele sa aiba versiunile lor.

#
### Este mult mai eficient sa cream metodele pe prototype o singura data si vor fi disponibile pentru toate instantele.

#
### Putem stoca si proprietati care nu sunt functii, pe `prototype`, 
- ### insa trebuie sa stim daca intr-adevar vrem sa stocam date ce pot fi modificate de catre alte instante. 

---

> # Modificari asupra prototipului

### Toate instantele de un tip impart acelasi prototip (proprietatea `[[Prototype]]` contine o referinta catre acelasi obiect prototype).

#
### Asta inseamna ca putem sa modificam oricand prototipul iar toate instantele sa beneficieze de aceste modificari.

#
### Putem, de exemplu, sa adaugam proprietati prototipului si acestea vor fi automat disponibile pentru obiectele instantiate cu acel prototip.

---

> # Prototipul obiectelor standard

#
### Toate obiectele standard JavaScript au constructori, 
- ### deci au si proprietatea `protoype` ce poate fi modificata.

#
### Daca vrem sa adaugam o metoda la obiectul `Array.prototype` putem, si toate array-urile o vor putea utiliza. 
> - #### nerecomandat, codul JS nu mai este portabil

---


### Tipurile primitive, `string, number, boolean`, au cate un wrapper care le face sa se comporte ca obiecte.

#
### Daca modificam `prototype`-ul acestor wrappere vom putea adauga noi functionalitati tipurilor primitive.

