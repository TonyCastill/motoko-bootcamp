# motoko-bootcamp # 

# Certificaciones #
* **Qualified Developer:** Reconoce que el participante cuenta con los conociemientos básicos sobre el desarrollo en ICP utilizando Motoko como lenguaje de programación, se obtiene haciendo el Quizz de validación de conocimientos pasándolo con una calificación aprobatoria. Se necesita
* * Cumplir con las actividades
  * Pasar el Quizz de conocimientos
* **Certified Developer:** Certificado que valida que el participante cuenta con las habilidades necesarias para construir proyectos, se obtiene entregando un proyecto funcional y presentándolo en el Demo Day
* * Desarrollar una aplicación Backed con Motoko
  * Publicar el proyecto en un repositorio público de GitHub
  * La aplicación debe ser 100% funcional y original
  * La aplicación no debe se un simple CRUD
# Sobre ICP #
**Internet Computer Protocol** es una blockchain respaldada por la fundación **DFINITY** que permite crear aplicaciones 100% descentralizadas. Todo lo descentralizado corre en la web 3, lo demás es web 2.
ICP solo define cómo se van a comunicar los servidores, el software se replica en varios nodos repartidos a lo largo del mundo.
A diferencia de otras blockchains, ICP divide su red en subnets
## Blockchain ##
Un sistema de registros donde todos los registros están replicados en los nodos, por lo que si se altera el registro en un solo nodo, se invalida la comprarlo con las réplicas de los demás nodos. Como una cadena de bloques
**HAY TRES GENERACIONES DE BLOCKCHAIN**
* La uno de Bitcoin (Transacciones de criptomonedas)
* La segunda de Etherium (Transacciones y tokenizar activos físicos, que tengan una reprentación dígital)
* La tercera de ICP (Toda la aplicación frontend y backend corriendo en la blockchain, 100% descentralizada)
## Key Features de ICP ##
* **Sovereign**
* **Web2 compatible** -> Es nativamente de Web3, pero es compatible con la web2
* **Multi-Chain** -> Blockchain interoperativa con otras redes blockchain
* **Tamperproof**
* **Autonomous**
* **Cost effective** -> más económico que otros blockchain, tokens y recursos almancenados con menores costos

## Token de ICP ##
**ICP token utility**
Tal como las blockchains con sus tokens (bitcoin -> bitcoin, ehterium -> lither, ICP -> ICP)
Este token ICP se puede comprar y convertir a una divisa. Se puede usar para pagar
Si tú tienes un ICP, tú puedes votar por que se puede hacer en la blockchain, con eso te vuelves en una "neurona" que puede participar en lo que se hace en la blockchain.
Con ICPs puedes comprar Cycles o cíclos
**Cycles**
Con lo que se paga el poder de cómputo, cada modificación en el estado de la blockchain, cuesta cierto tiempo de cómputo de un procesador, eso es lo que nos cobran a nosotros como desarrolladores. Esto se paga con Ciclos que se pagan con ICPs
**IMPORTANTE**
Te cobran por modificar recursos o datos en la aplicación, no por acceder a ellos

## Chain Fusion Technology ##
El conjunto de tecnologías de ICP que me perimte comuicarme con otras blockchains. Con esto se pueden tener wallets de múltiples blockchains EVM JSON RPC
Bitcoin twin: ckBTC
Etherum asset twins: ckETH and ckERC20

## ¿Cómo funciona una dApp en ICP? ##

![Screenshot from 2024-10-05 17-40-48](https://github.com/user-attachments/assets/591d8370-2850-464e-bf72-92c9eb5c22b5)

Una dApp es una Descrentralized Application o aplicación descentralizada. La primera vez que se crea un aplicación, se crea con una arquitectura default
**Fronted Canister:** La aplicación con la que interactúa el usuario. La UI
**Backend Canister:** La aplicación con la que interactúa el usuario del lado del servidor. La lógica de la aplicación o lógica de negocio que son los flujos o tratamiento de los datos que se da para que cuando el usuario quiera hacer algo, se valide, y storage que se genera la aplicación

### Canister ###

![image](https://github.com/user-attachments/assets/d40c7840-3cc6-4ad3-bfbf-760a822e1cba)

Es un bote que puede guardar el código que se va a desplegar y tiene la memoria sobre la cual persistir información. Gracias al Web Assembly (WASM) potencialmente se puede desarrollar en cualquier lenguaje (A bajo nivel se podría hacer con PHP o Java), pero actualmente hay soporte oficial para cuatro lenguajes:
**Desarrollados por Dfinity**
* Rust
* Motoko
**Desarrollados por la comunidad**
* Typescript
* Python
<hr>

**Ejemplo de canisters**

![image](https://github.com/user-attachments/assets/1d5d5b9c-bd30-495f-9309-7ba94d74570c)

**Candid**
Los lenguajes de programación pueden estar tipados, para que haya interoperabilidad, existe un lenguaje en común llamado candid que homogeniza los tipos de datos entre todos los lenguajes de programación.
La comunicación existe gracias al mapeo de los tipos de datos entre las diferente tecnologias
Candid UI es como un Postman

![image](https://github.com/user-attachments/assets/e7b0526b-b1e2-4129-a228-2ccccca8e62b)

<hr>

### Flujo de desarrollo ###

![image](https://github.com/user-attachments/assets/b516cb1b-3d6c-4b25-9538-b61dd1720ff1)

Se necesita de la herramienta **dFx** (la navaja suiza), con ella se gestionan identidades de desarrollor, se crean ambientes y entornos de desarrollo locales, se despliegan hacia un entorno de desarrollo productivo, se gestionan los ciclos y tokens que se despliegan a los diferentes canisters

Básicamente con esta herramienta se pueden crear, editar, desplegar e interactuar con los canisters (tanto los backend como los frontend). Esta herramienta agarra el código, lo transforma en binarios WASM y los despliega en el bote.
mainnet es la red principal de la blockchain, y la testnet es la red local donde se pueden hacer pruebas
**Ambientes**
<a src="https://m7sm4-2iaaa-aaaab-qabra-cai.raw.ic0.app/
">Motoko Playground</a>
Es para miniproyectos, para proyectos más grandes:
<ul>
<li><a src="https://github.com/codespaces" name="github-codespace">Github codespace</a></li>
<li><a src="https://www.gitpod.io/">Gitpod</a></li>
<li><a src="https://internetcomputer.org/docs/current/developer-docs/getting-started/install/">Local dfxvm gestor de versiones</a></li>
 </ul>
- [Github codespace](https://github.com/codespaces)

# Enlaces #
Frontend:
https://www.youtube.com/watch?v=oFljzGmCM-g&list=PLixWO0N_iFTM3haBGfEtIhyFQJd3BVfGB

Backend:
https://www.youtube.com/watch?v=VjOO3VV-SHk&list=PLixWO0N_iFTOfmQLpBXihTdEU_MqWGIKc&index=5
