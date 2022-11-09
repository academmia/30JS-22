> # Sa pornim de la urmatorul exemplu

```js
    function foo() {
        var something = "cool";
        var another = [1, 2, 3];
        function doSomething() {
            console.log( something );
        }
        function doAnother() {
            console.log( another.join( " ! " ) );
        }
    }
```

#
### Mai sus avem o functie si doua functii interne ce au access la contextul functiei externe 
- (care le contine)

#
### Sa facem urmatoarea modificare:

```js
    function CoolModule() {
        var something = "cool";
        var another = [1, 2, 3];
        function doSomething() {
            console.log( something );
        }
        function doAnother() {
            console.log( another.join( " ! " ) );
        }
        return {
            doSomething: doSomething,
            doAnother: doAnother
        };
    }

    var foo = CoolModule();

    foo.doSomething();      // cool
    foo.doAnother();        // 1 ! 2 ! 3
```

#
### Tocmai ce am utilizat (Revealing) Module Pattern.
Este una dintre variatiile Module Pattern.

#
### CoolModule este o functie simpla, ce trebuie apelata pentru a crea functionalitatea de modul.

#
### In al doilea rand observam ca returneaza un obiect ce contine referinte catre functiile interne.

#
### Variabilele nu sunt expuse, raman private.

#
### Practic obiectul returnat este un API public expus pentru a fi utlizat din exterior.

#
### (Nu este obligatoriu sa returnam un obiect, putem returna si o functie, orice functie este un obiect ce poate avea proprietati)

#
### Sunt doua conditii pentru a avea un modul:

- ### Sa avem o functie externa (aceasta trebuie invocata cel putin odata)
- ### Sa returnam cel putin o functie interna care sa aibe access la contextul privat al functiei

#
### In felul asta putem sa modificam si sa citim contextul privat prin intermediul functiei.

#
### In codul de mai sus functia poate fi invocata de mai multe ori creand mai multe instante ale modulului.

#
### O variatie a acestui pattern este atunci cand vrem ca modulul sa fie singleton 
- ### (initializat o singura data) 

```js
    var foo = (function CoolModule() {
        var something = "cool";
        var another = [1, 2, 3];
        function doSomething() {
            console.log( something );
        }
        function doAnother() {
            console.log( another.join( " ! " ) );
        }
        return {
            doSomething: doSomething,
            doAnother: doAnother
        };
    })(); // IIFE - functie imediat invocata    

    foo.doSomething();      // cool
    foo.doAnother();        // 1 ! 2 ! 3
```

#
### Modulele pot primi parametri

```js
    function CoolModule(id) {
        function identify() {
            console.log( id );
        }
        return {
            identify: identify
        };
    }

    var foo1 = CoolModule( "foo 1" );
    var foo2 = CoolModule( "foo 2" );

    foo1.identify(); // "foo 1"
    foo2.identify(); // "foo 2"       
```

#
### O noua variatie a pattern-ului ne ofera noi capabilitati.

#
### Putem sa modificam API-ul, prin stergere, adaugare sau modificari de proprietati dupa ce modulul a fost initializat.

```js
    var foo = (function CoolModule(id) {

        function change() {
            // aceasta functie modifica API-ul schimband referinta cu o alta functie interna
            publicAPI.identify = identify2;
        }

        function identify1() {
            console.log( id );
        }

        function identify2() {
            console.log( id.toUpperCase() );
        }   

        var publicAPI = {
            change: change,
            identify: identify1
        };

        return publicAPI;  // acum avem legatura facuta cu instanta obiectului API si o putem accesa ulterior

    })( "foo module" );

    foo.identify(); // foo module
    foo.change();
    foo.identify(); // FOO MODULE
```

