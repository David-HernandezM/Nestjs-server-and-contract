# Nestestjs server

The nestjs server contains a `.env` file where you can find the jwt secrets key and the port.

To install all dependencies, use:

```bash
pnpm i
```

To run the server in development mode, use

```bash
pnpm run start:dev
```

## Server structure

### Modules:

- auth: this module contains all the login to register, login and manage the jwt tokens from the users, it contains some to protect all the apis 
  that need verification from the user.
- keyring: this module handles all the keyring methos from the keyring service in the contract, it creates all the user wallets, handles the keyring
  data, etc.

### Services:

- sailscallsService: this service gives the instance of SailsCalls, it helps you to send messages, queries, handle the vouchers and keyring accounts,
  you can use this service in all your module if you need to send messages to your contract.


### Nestjs url
Following are the available url for nestjs server based on the provided idl:

- Url for Green command in service TrafficLight: *https://localhost:8000/trafficlight/command/green*
- Url for RandomFuncCommand command in service TrafficLight: *https://localhost:8000/trafficlight/command/randomfunccommand*
- Url for Red command in service TrafficLight: *https://localhost:8000/trafficlight/command/red*
- Url for Yellow command in service TrafficLight: *https://localhost:8000/trafficlight/command/yellow*

- Url for ContractOwner query in service TrafficLight: *https://localhost:port/trafficlight/query/contractowner*
- Url for RandomFuncQuery query in service TrafficLight: *https://localhost:port/trafficlight/query/randomfuncquery*
- Url for TrafficLight query in service TrafficLight: *https://localhost:port/trafficlight/query/trafficlight*

- Register 
  - call: http://localhost:8000/auth/register
  - data to send (user and password): { "username": "david12345678901", "password": "" }
  
- Login
  - call
  - data to send (user and password), already user registered: { "username": "david12345678901", "password": "123123123" }

- Refresh (refresh the token JWT)
  - call: http://localhost:8000/auth/refresh

- Get account data:
  - call: http://localhost:8000/keyring/:address
  - where ":address" is the account address

<p align="center">
    <img src="https://nestjs.com/img/logo-small.svg" width="120" alt="Nest Logo" />
</p>