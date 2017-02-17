# Ethereum cluster running on Kubernetes

### 1 - Deploy a Kubernetes cluster
For Azure, follow the documentation: [Creating your Kubernetes cluster](https://docs.microsoft.com/en-us/azure/container-service/container-service-kubernetes-walkthrough)

### 2 - Spin up your Ethereum network

If you want to modify the `genesis.json`, do so in the `./geth-node` folder, then build the docker image and push it to a container registry. Finally, modify `miner-nodes.yaml` and `tx-nodes.yaml` to use your new image instead of `wbuchwalter/geth-node`

* `kubectl create -f dashboard.yaml` 
* `kubectl create -f miner-nodes.yaml` 
* `kubectl create -f tx-nodes.yaml` 

### 3 - Setup Monitoring
##### With OMS (Operation Management Suite):
If you want to use OMS (Operation Management Suite), register at [https://mms.microsoft.com](https://mms.microsoft.com), and modify the values of `KEY` and `WSID` (Workspace ID) in `oms-agent.yaml` with yours.  
Then: `kubectl create -f oms-agent.yaml`

##### With DataDog
Replace the `API_KEY` in `dd-agent.yaml` by your API key.  
Then: `kubectl create -f dd-agent.yaml` 

