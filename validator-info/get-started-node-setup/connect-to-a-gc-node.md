# Connect to a GC Node

If you choose not to use the public RPC and want to connect to your own GC node, follow these instructions:

* If using a 3rd party node provider, set `XDAI_RPC_URL`=https://\<your-endpoint>&#x20;

### **Fallback IPs (Lighthouse only)**

Use comma-separated RPC urls for the `XDAI_RPC_URL` variable to set fallback IPs in Lighthouse. This is useful if your node goes offline. For example:

* `XDAI_RPC_URL`=https://\<your-endpoint>, [https://rpc.gnosischain.com](https://rpc.gnosischain.com)&#x20;

### **Sharing machines for GC and GBC clients**

Previous instructions included adding the `extra_hosts` parameter to your `docker-compose.yml` file to expose the container and connect to the node if you were running both a Gnosis Chain and Gnosis Beacon Chain client on the same machine.  **This is no longer necessary with the inclusion of the bridge network driver in the latest releases**.

* `XDAI_RPC_URL`=[http://localhost:8545](http://localhost:8545)
