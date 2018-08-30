# sawtooth-app-js
Sawtooth example network using JavaScript SDK: transaction processor and client

# Introduction

This is a minimal example of a sawtooth 1.0 application. This example demonstrates, a common usecase, where a customer deposits/withdraws/transfers money from a wallet account.

A customer can:
1. deposit money into his/her wallet account
2. withdraw money from his/her wallet account
3. check the balance in the wallet account
4. transfer money from his/her wallet account to another

The customer is identified by a customer name and a corresponding public key. The wallet account balance, is stored at an address, derived from SHA 512 hash of customer's public key and the simplewallet transaction family namespace.

# Components
The application is built in two parts:
1. The client application written in nodeJS. The `app.js` is the main javascript file from where the `main` function call occurs. Handlebars are used for templating, client related CSS and JavaScript code is written in public folder and server related files are written in `router/` folder. It is accessible via browser at `localhost:3000`.
2. The Transaction Processor, that uses the JS Sawtooth SDK.

------

**JAVASCRIPT CLIENT USAGE**

How to use the simplewallet UI:

1. Build and start the Docker containers:

`docker-compose -f docker-compose.yaml up`

2. Open bash shell in `simplewallet-client-js` container:

`docker exec -it simplewallet-client-js bash`

3. Create user accounts for jack and jill:

`sawtooth keygen jack && sawtooth keygen jill`

4. Open two new browser tabs and go to `http://localhost:3000` on each tab

5. Login in one tab as `jack` and in other as `jill` 

6. Start with an initial deposit for each user - jack and jill via the `Deposit` tab in the UI homepage

