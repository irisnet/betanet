# Betanet gentx files

## Requirement

You must have follow this [doc](https://github.com/irisnet/irishub/blob/master/docs/get-started/Install-the-Software.md) to install the `mainnet` version of **Iris**.

## Step 1: Create your own account

First you need to create a account as the corresponding validator operator for yourself, you should use the address for 
claiming [testnet rewards](https://github.com/irisnet/betanet/blob/master/fuxi-reward-claims/README.md)


## Step 2: Initialize your node

Initialize your node with `chain-id=irishub`. Please note that your monniker could be customized.

```bash
iris init --home={path_to_iris_home} --chain-id=irishub --moniker={node-name}
```

This command will create the genesis& config files in the home directory.


## Step 3: Execute `gentx` command

```bash
iris gentx --amount=XXXiris --home={path_to_iris_home} --name={key_name} --ip={sentry_node_ip}
```
This commond will generate the transaction in the directory：{path_to_iris_home}/config/gentx
Create the `CreateValidator` transaction and sign the transaction by the validator operator account you just created
The default commission data is:
*	delegation amount:           XXXiris
*	commission rate:             0.1
*	commission max rate:         0.2
*	commission max change rate:  0.01

You could also change these metrics.

> Please note the amount is what you want to self-delegate, this amount could not be bigger than your balance in genesis file
> IP is your sentry node's public IP

## Step 4: Sumbit your gentx.json
Save your gentx file as [github-user-name]-[keybase fingerprint].json, 
For example,GitHub user [irisnetvalidator](https://github.com/irisnetvalidator), its keybase fingerprint is `6763B2C7947A9363`.
Its submission should be 'irisnetvalidator-6763B2C7947A9363.json'.

Submit your json file to `https://github.com/irisnet/betanet/tree/master/gentx/betanet-gentx` by creating a pull request.

After the team has verified all the gen-tx transactions, we will publish the final genesis file.
