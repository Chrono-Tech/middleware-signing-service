# middleware-signing-service [![Build Status](https://travis-ci.org/ChronoBank/middleware-signing-service.svg?branch=master)](https://travis-ci.org/ChronoBank/middleware-signing-service)

Middleware service for signing transactions 

### Installation

npm i
pm2 start index.js --name='sign-rest'

#### About
This module is used for signing transactions. This happens through the layer, which is built on node-red.
So, you don't need to write any code - you can create your own flow with UI tool supplied by node-red itself. Access by this route:
```
/admin
````


#### Predefined Routes with node-red flows

| description | route | method | params | output | 
| --------- | ---- | - | ---- | --- | 
| sign transation in waves, used seed for selected address | /sign/waves/:address | POST | ```{<txObject>}``` [waves](examples/input_waves.md)  | [waves](examples/output_waves.md)
| sign transation in nem, used keys for selected address | /sign/nem/:address | POST | ```{<txObject>}``` [nem](examples/input_nem.md)  | [nem](examples/output_nem.md)
| sign transation in eth, used keys for selected address | /sign/eth/:address | POST | ```{<txObject>}``` [eth](examples/input_eth.md)  | [eth](examples/output_eth.md)
| sign transation in bitcoin, used keys for selected address | /sign/bitcoin/:address | POST | ```{<txObject>}``` [waves](examples/input_bitcoin.md)  | [bitcoin](examples/output_bitcoin.md)


##### сonfigure your .env

To apply your configuration, create a .env file in root folder of repo (in case it's not present already).
Below is the expamle configuration:

```
WAVES_SEED=3JfE6tjeT7PnpuDQKxiVNLn4TJUFhuMaaT5@foo0
NEM_KEY=3JfE6tjeT7PnpuDQKxiVNLn4TJUFhuMaaT5@foo0
ETH_KEY=3JfE6tjeT7PnpuDQKxiVNLn4TJUFhuMaaT5@foo0
BITCOIN_KEY=3JfE6tjeT7PnpuDQKxiVNLn4TJUFhuMaaT5@foo0
HTTP_ADMIN=/admin
REST_PORT=8081

```

The options are presented below:

| name | description|
| ------ | ------ |
| BITCOIN_KEY | private keys for account in bitcoin (format: address@key,address@key)
| ETH_KEY | private keys for account in eth (format: address@key,address@key)
| NEM_KEY | private keys for account in nem (format: address@key,address@key)
| WAVES_SEED | seed phrases for account in waves (format: address@seed,address@seed)
| HTTP_ADMIN | admin path for nodered or false (if not publish as default)
| REST_PORT   | rest plugin port


License
----
 [GNU AGPLv3](LICENSE)


Copyright
----
LaborX PTY
