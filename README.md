![DLX Logo TM](https://user-images.githubusercontent.com/18197505/212561424-959357bb-191b-48f5-8772-cb775925c83e.png)

# Dataledger-Node

## How to Use

**This is the Data LedgerTM applicaiton which is deployed at user locations to create network to transfer data securely. This software creates a Node and each decivse that wants to trasact data needs to connect to the Exchange network.**

## Usage

### 1. Clone repository

Clone git repository from [CosysX/dataledger_node](https://github.com/CosysX/dataledger_node)
```bash
git clone https://github.com/CosysX/dataledger_node.git
```

### 2. create.env

Create a .env file with your settings in the root directory.

Always start with a new unused seed!

MAX_PAYMENT_TIME is the time until created paymentes aren't checked anymore in minutes (4320 = 3 days to pay, transactions after that are ignored)

If you want to send payouts, without receiving iotas via payments first, send the iotas to the first address of the seed (index 0)

```bash
SEED='REPLACEWITHEIGHTYONETRYTESEED'
IOTANODE='https://nodes.thetangle.org:443'
FALLBACKNODE='https://node01.iotatoken.nl'
MAX_PAYMENT_TIME=4320
NAME="Data Ledger Exchange Node"
VALUE=5
```

### 3. Generate new seed

Create a seed and insert it to your .env file.

#### Linux
 enter this line in your terminal.
```bash
cat /dev/urandom |tr -dc A-Z9|head -c${1:-81}
```

#### Mac
 enter this line in your terminal.
```bash
cat /dev/urandom |LC_ALL=C tr -dc 'A-Z9' | fold -w 81 | head -n 1
```

#### Windows
For Windows, the best way is to use [KeePass](https://keepass.info/), or use one of the two online generators above.

You will want to use the password generator with the following settings:

- Length of generated password: 81
- Check Upper-case (A, B, C, ...)
- Make sure all other boxes are unchecked
- Also include the following characters: 9

### 5. Build the frontend

enter these lines in your terminal.
```bash
cd frontend
npm install
npm run build
cd ..
```

### 5. Run Exchange Node

enter these lines in your terminal.
```bash
npm install
npm start
```


Copyright (C) 2023 CosysX.
