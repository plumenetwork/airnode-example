# Airnode Support on Plume

The open-source [Airnode protocol](https://api3.org/airnode/) by [API3](https://api3.org/) has been deployed to Plume testnet at the following smart contract addresses:

| Contract Name                  | Contract Address                                                                                                                            |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------- |
| AccessControlRegistry          | [0x18CfFc3F5fA6c1958da1c44D86E6BD71280D8b56](https://plume-testnet.explorer.caldera.xyz/address/0x18CfFc3F5fA6c1958da1c44D86E6BD71280D8b56) |
| RequesterAuthorizerWithAirnode | [0xf6c2Ef6b99DE3bfFB990FDFE81A535F3d9a2D849](https://plume-testnet.explorer.caldera.xyz/address/0xf6c2Ef6b99DE3bfFB990FDFE81A535F3d9a2D849) |
| AirnodeRrpV0                   | [0xa7005248c0596f93dd947f74Bf11F4ba153b72Dd](https://plume-testnet.explorer.caldera.xyz/address/0xa7005248c0596f93dd947f74Bf11F4ba153b72Dd) |
| AirnodeRrpV0DryRun             | [0xf203C9091dc25d57976a0b03C9d6E9A0E391f857](https://plume-testnet.explorer.caldera.xyz/address/0xf203C9091dc25d57976a0b03C9d6E9A0E391f857) |

Use the sample [config.json](./config.json) in this repo to define an Airnode deployment. Make sure to set all appropriate configuration variables, as well as your desired cloud provider. Follow the [Deployer Image instructions](https://docs.api3.org/reference/airnode/latest/docker/deployer-image.html) in the Airnode documentation for more details. An example command to deploy your Airnode would be:

```shell
docker run -it --rm \
  -e USER_ID=$(id -u) -e GROUP_ID=$(id -g) \
  -v "$(pwd):/app/config" \
  api3/airnode-deployer:latest deploy
```

Running this command successfully will output something similar to [receipt.json](./receipt.json). An example command to remove the deployment would be:

```shell
docker run -it --rm \
  -v "$(pwd):/app/config" \
  api3/airnode-deployer:0.14.0 remove <Project_id>
```

Additional commands are available [in the Airnode documentation](https://docs.api3.org/reference/airnode/latest/docker/deployer-image.html#deployer-image-commands).
