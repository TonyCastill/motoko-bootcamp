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

## Estructura de un proyecto ##

**dfx.json**
Es la estructura del proyecto de ICP
Dentro de la clave "canisters" se construyen los botes donde se pondrá la aplicación


# ¿Qué es Motoko? #

Un lenguaje de programación de alto nivel diseñado para correr aplicaciones en ICP. Se usa para desarrollar aplicaciones backend. Es un lenguaje fuertemente tipado y fue diseñado para se sencillo y fácil de apreder

## Estructura básica ##

(Cada que se haga un cambio al código, se debe correr dfx deploy para ver los cambios)

//imports

actor Echo { //canister 
  //Estado y acciones 


  //VARIABLES
  //Constantes
  let PI = 3.1416;
  //Mutables
  var _name ="";
};


**Query Update**
Métodos que me dan comportamientos

actor  Echo{
   func setName(name: Text){
      _name := name;
   }
};

Las funciones pueden ser private o public, pero public tiene dos subtipos

//Update
// Escritura y tarda más porque tiene que verificarse   replicarse en los nodos
actor  Echo{
   public func setName(name: Text){
      _name := name;
   }
};


//Query
//Solo lectura y está optimizado para eso
actor  Echo{
   public query func getName(): async Text{
      return "Tu nombre es " # _name; 
      // se concatena con #
   }
};

//Convertir Float a Text para imprimirlo

import Text "mo:base/Text";
import Float "mo:base/Float"; //From documentation

actor Echo {
   let PI = 3.1416

    public query func getPI() : async Text{
       return "El número PI es igual a " # Float.toText(PI);
    };
}
