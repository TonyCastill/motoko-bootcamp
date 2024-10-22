# Backend #

<hr>

## Usuario Web3 ##
Se pueden hacer interfaces muy pensadas en los usuarios, a diferencia de otras blockchains que se tiene que tener una wallet y se paga por cualquier cosa. Con ICP se piensa tener una aplicación full stack (como una aplicación cualquiera de web 2) que funcione con la web 3

### Internet Identity ###

Es la propuesta que hace ICP para tener identidades web3 sin wallets. Ojo, a diferencia de las aplicaciones centralizadas, esta identidad no comparte datos de los usuarios a las aplicaciones, por lo que se garantiza la privacidad del usaurio.
Con esta identidad se cuentan con métodos de verificación en casi cualquier dispositivo, además, está completamente integrado con Canisters de ICP
Crear una:
https://identity.ic0.app/

### NNS ###

Es una aplicación de Internet Computer que me permite tener mi wallet, ahí están presentes las criptomonedas de la blockchain ICP. Ahí se puede realizar transacciones o recibir criptomonedas como la ICP
Acceder:
https://nns.ic0.app/


### Hobbi ###

Una red social (frontend desplegado en un canister frontend y un backend desplegado en un canister backend)
https://hobbi.me

 ## Identidades de Developer ##
 Comandos dfx

 **Identidad**
 
<table>
  <tr>
    <th>Comando</th>
    <th>Uso</th>
  </tr>
  <tr>
    <td>$ dfx identity list</td>
    <td>Lista las identidades del proyecto. AL inicio se crea la default y la annonymous</td>
  </tr>
  <tr>
    <td>$ dfx identity new _nombre_</td>
    <td>Crear una nueva identidad</td>
  </tr>
  <tr>
    <td>$ dfx identity whoami</td>
    <td>Verificar con que identidad se está trabajando</td>
  </tr>
  <tr>
    <td>$ dfx identity use _identity_</td>
    <td>Usar una identidad</td>
  </tr>
  <tr>
    <td>$ dfx identity get-principal</td>
    <td>Devuelve el identificador de la identidad</td>
  </tr>
</table>

**Crear nuevo proyecto**

<table>
  <tr>
    <th>Comando</th>
    <th>Uso</th>
  </tr>
  <tr>
    <td>$ dfx new _proyect-name_</td>
    <td>Crear un nuevo proyecto. Posteriormente te pregunta con qué lenguaje backend se quiere crear el proyecto. Luego te pregunta por el frontend. Luego te pregunta por una criptomoneda a usar</td>
  </tr>
  <tr>
    <td>$ code .</td>
    <td>Abrir VS code en la carpeta actual</td>
  </tr>
</table>

**Local replica**

<table>
  <tr>
    <th>Comando</th>
    <th>Uso</th>
  </tr>
  <tr>
    <td>$ dfx start --background --clean</td>
    <td>Crear una replica de una network de producción en local. Con --background corre el canisteren 2do plano y con --clean la crea desde cero borrando todo rastro de anteriores ejecuciones</td>
  </tr>
 <tr>
    <td>$ dfx stop</td>
    <td>Parar la replica</td>
 </tr>
</table>

**Desplegar**

<table>
  <tr>
    <th>Comando</th>
    <th>Uso</th>
  </tr>
  <tr>
    <td>$ dfx deploy</td>
    <td>Desplegar todos los canisters</td>
  </tr>
  <tr>
    <td>$ dfx deploy _name_</td>
    <td>Desplegar un canister, este va después del start. Esto crea los canisters, compila el código y lo lanza en los canisters</td>
  </tr>
</table>


**Interactuar con un canister desde la consola**

<table>
  <tr>
    <th>Comando</th>
    <th>Uso</th>
  </tr>
 <tr>
  <td>
   dfx canister call _canister-name_ _function_
  </td>
  <td>
   Call a function of a canister, you can see your canister names in dfx.json
  </td>
 </tr>
 </table
## Estructura de un proyecto ##

**dfx.json**
Es la estructura del proyecto de ICP
Dentro de la clave "canisters" se construyen los botes donde se pondrá la aplicación


# ¿Qué es Motoko? #

Un lenguaje de programación de alto nivel diseñado para correr aplicaciones en ICP. Se usa para desarrollar aplicaciones backend. Es un lenguaje fuertemente tipado y fue diseñado para se sencillo y fácil de apreder

## Estructura básica ##

(Cada que se haga un cambio al código, se debe correr dfx deploy para ver los cambios)
```
//imports
actor Echo { //canister 
  //Estado y acciones 
  //VARIABLES
  //Constantes
  let PI = 3.1416;
  //Mutables
  var _name ="";
};

```

** Funciones **
Métodos que me dan comportamientos
```
actor  Echo{
   func setName(name: Text){
      _name := name;
   }
};
```
Las funciones pueden ser private o public, pero public tiene dos subtipos

**Update**
Modifican el estado de un actor
Escritura y tarda más porque tiene que verificarse y replicarse en los nodos. Tardan de 2 a 3 segundos dependiendo de lo que se está haciendo.
Con los dos puntos indica lo que devuelve la función, si es solo un paréntesis, no regresa nada.
El shared indica que los funciones públicas o funciones que se comparten con otros actores, puedan compartir las variables. Que se puede usar la función desde fuera
```
actor  Echo{
   public shared func setName(name: Text):(){
      // := para asignar valor a la variable
      _name := name;
   }
};
```
_Otro ejemplo_
COmo la comunicación entre los actores es asíncrona, se usa la palabra reservada async para devolver algo desde una función
```
actor  Echo{
   public func setName(name: Text): async Text{
      // := para asignar valor a la variable
      _name := name;
      return _name;
   };
};
```

**Query**
Solo lectura y está optimizado para eso. Leen el estado de un actor
```
actor  Echo{
   public query func getName(): async Text{
      return "Tu nombre es " # _name; 
      // se concatena con #
   }
};
```
//Convertir Float a Text para imprimirlo
```
import Text "mo:base/Text";
import Float "mo:base/Float"; //From documentation

actor Echo {
   let PI = 3.1416

    public query func getPI() : async Text{
       return "El número PI es igual a " # Float.toText(PI);
    };
}
```
# Memorías #
Cada que se hace un deploy de un canister, se genera una cadena hash que sirve para verificar si hay cambios. En caso de que haya cambios, al generar la cadena deja de ser la misma, y cuando no hay cambios, es la misma cadena haciendo que sea más rápido el deploy

Hay dos tipos de memoria
* Heap Memory
* Stable Memory

<table>
 <tr>
  <th>
   Memory feature
  </th>
  <th>
   Heap Memory
  </th>
  <th>
   Stable Memory
  </th>
 </tr>
 <tr>
  <td>Store capacity</td>
  <td>40GB</td>
  <td>400GB</td>
 </tr>
 <tr>
  <td>Intended use</td>
  <td>Small datasets, frequently accessed data, temporary data</td>
  <td>Large datasets, infrequently accessed data, important data that msut persist</td>
 </tr>
 <tr>
  <td>Persistance</td>
  <td>Does not persist across upgrades</td>
  <td>Data is preserved and persists across upgrades</td>
 </tr>
 <tr>
  <td>Performance</td>
  <td>Fast read/write operations</td>
  <td>Slightly decreased read/write operations</td>
 </tr>
</table>




