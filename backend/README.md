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


