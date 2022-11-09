
> # `Object.prototype` si inlantuirea prototipurilor

#
### In limbaje traditionale orientate pe obiect, clasele pot mosteni proprietati ale altor clase.

#
### In JavaScript nu avem clase, insa poate exista mostenire intre obiecte.

#
### Mecanismul prin care putem obtine asta se foloseste de prototype.

#
## Inlantuirea prin `prototype`

- ### Proprietatile de pe `prototype` sunt automat disponibile instantelor 
    - ### (ceea ce este o forma de mostenire)

#
- ### `Prototype` este la randul lui un obiect care are propriul `prototype` 
    - ### si mosteneste proprietatile lui, si asa mai departe... 
    - ### Deci avem o inlantuire a prototipurilor.

#
- ### Toate obiectele, inclusiv cele create de noi, mostenesc proprietatile de pe prototipul lui `Object` 
    - ### (daca nu am specificat un alt prototip). 

#
- ### Deci toate obiectele mostenesc `Object.prototype`

---

> ## `Object.prototype`

#
### Nu este recomandat sa modificam prototipurile obiectelor predefinite 
- ### si cu atat mai mult a tipului generic Object.

#
### Obiecte diferite ca functionalitate mostenesc `Object.prototype`, 
- ### daca adaugam o functie aici, mai mult ca sigur ca functia respectiva nu va avea sens pentru toate instantele ce mostenesc `Object.prototype`

---


