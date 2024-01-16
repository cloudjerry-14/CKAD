
How many replicaset are there 
``` k get rs ```

inspect replicaset
``` k desribe rs my-replicaset ```

delete replicaset
``` k delete rs my-replicaset ```

scale up and down replicaset 
``` k scale rs my-replicaset --replicas=1000 ```
``` k scale rs my-replicaset --replicas=1 ```

troubleshooting :
Run the command: You can check for apiVersion of replicaset by command kubectl api-resources | grep replicaset

kubectl explain replicaset | grep VERSION and correct the apiVersion for ReplicaSet.

Then run the command: kubectl create -f /root/replicaset-definition-1.yaml

