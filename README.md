### VCverifierIdThon
 A website that utilizes Verifiable Credentials to implement access restrictions.
 
 This Repo is part of solution for PolygonIdThon Challenge-2 and inspired by template made by [@oceans404](https://github.com/oceans404/vc-verifier) 


## Local Server Setup

### 1. Clone the GitHub repo locally

```
  git clone https://github.com/0xShax2nk/VCverifierIdThon
  cd VCverifierIdThon
  npm i
```

### 2. Set up ngrok server forwarding

If you don't have ngrok already set up, you can install ngrok via homebrew or download. Login (I used GitHub login) to create a free account and add your account's config token to the command line.
After ngrok is set up, start a tunnel to port 3000 to expose your server to the internet beyond only being available to your laptop on localhost:3000. This is necessary because the Polygon ID mobile wallet app will use a verification URI you provide and needs to be able to send the verification result to this exposed public endpoint.

  ```
  ngrok http 3000
  ```
You'll see a forwarding address in the logs

```
  Forwarding  https://abc-your-forwarding-address-def.ngrok-free.app -> http://localhost:3000
```
![Ngrok](https://i.ibb.co/1JrNbc2/Ngrok.png)

### 3. Create .env file
  ```
   
   HOSTED_SERVER_URL="https://add-your-free-ngrok-app.ngrok-free.app"

   VERIFIER_DID="YOUR_DID_FROM_POLLYGON_WALLET_ID"

   RPC_URL_MUMBAI="https://polygon-mumbai.g.alchemy.com/v2/yourAlchemyKeyForPolygonMumbai"

   CLIENT_URL="http://localhost:8080"

  ```

   Update the environmental variables in the .env file as
   
   
   &bull; HOSTED_SERVER_URL = The forwarding address you get while you spin up ngrok server
   
   &bull; VERIFIER_DID = The DID from polygon walled id app
   
   &bull; RPC_URL_MUMBAI = RPC Testnet endpoint
   
   &bull; CLIENT_URL = Don't change for local setup

   
### 4. Run your server on port 3000

   ```
      node index.js
   ```

### 5. Hook the server up to a frontend

   This repo covers server setup. Next hook the server up to a frontend using this code:

   &bull; frontend GitHub repo: [https://github.com/0xShax2nk/VCgatedSiteIdThon](https://github.com/0xShax2nk/VCgatedSiteIdThon)
    
  
       
