[![PyPI version](https://img.shields.io/pypi/v/swan-sdk)](https://pypi.org/project/swan-sdk/)
# Swan SDK Orchestrator Task Samples

This directory contains samples for Swan Orchestrator. Swan Orchestrator is the Web3 cloud computing solution for tasks creation, deployment and management. User can create and manage tasks through samples under this directory. For more information checkout [Swan Developer Docs](https://docs.swanchain.io/).

## Setup

### Authentication (API Key)

This sample (and Swan SDK) requires you to have API Key from Swan Orchestrator.

Steps to get an API Key:

- Go to [Orchestrator Dashboard](https://orchestrator.swanchain.io/provider-status). Make sure you're under the Mainnet environment.
- Login through MetaMask.
- Click the user icon on the top right.
- Click 'Show API-Key' -> 'New API Key'
- Store your API Key safely, do not share with others.

### Install Dependencies
1. Clone the python-sdk-docs-samples  and change directory to the directory you want to use.
```bash
$ git clone https://github.com/swanchain/python-sdk-docs-samples.git
```
and
```bash
$ cd compute
```
2. Install and updgrade pip and virtualenv if you do not already have them.
3. Create virtualenv compatible with Python 3.7+
```bash
$ python3 -m venv venv
$ source venv/bin/activate
```
4. Install the dependencies from the requirements file
```bash
$ pip install -r requirements.txt
```

### Store Your Environment Variables Securely 
Python-dotenv is recommended to be used to store environment variables safely. (Contained within requirements.txt)
1. Install python-dotenv (if you have not)
```bash
$ pip install python-dotenv
```
or
```bash
$ pip install -r requirements.txt
```
2. Create a new .env file
```bash
$ sudo vim .env
```
3. Store your personal information
public address will be required for authorization on Swan Orchestrator. \
private address will be required for signing onchain transactions. \
API key will be required for using Swan Orchestrator APIs.
```txt
WALLET_ADDRESS=<your_wallet_address>
PRIVATE_KEY=<your_private_key>
SWAN_API_KEY=<your_swanchain_api_key>
```
4. Load your personal information (Optional)
We recommand storing personal information as environment variables for safety.
```python
from dotenv import load_dotenv
load_dotenv()

import os

WALLET_ADDRESS = os.getenv('WALLET_ADDRESS')
PRIVATE_KEY = os.getenv('PRIVATE_KEY')
SWAN_API_KEY = os.getenv('SWAN_API_KEY')
```

## Run Samples

### Get Instance Resources
Retrieve all currently available CP resources online.
```bash
$ python compute/get_instance_resources.py
```

### Get Instance Information (price)
Retrieve CP resources detail with resources type.
```bash
$ python compute/get_instance_information.py
```

### Instance Configuration Example
Detailed breakdown of instance configuration structure and usage.
```bash
$ python compute/instance_configuration_example.py
```

### Connect to Orchestrator (with Swan API Key)
```bash
$ python compute/connect_orchestrator.py
```

### Create Task
```bash
$ python compute/create_task.py
```

### Renew Task / Extend Task Duration
```bash
$ python compute/renew_task.py 
```

### Terminate Task
```bash
$ python compute/terminate_task.py
```
