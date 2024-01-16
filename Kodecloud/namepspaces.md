k=kubectl
ns =namespace
-n = namepspace

how many namespace are there ?
  ``` k get ns ```

  create a namespace my-namespace

  ``` k create ns my-namespace ``` 

  How many pods are there in namespace my-namespace

  ``` k get po -n my-namespace ```

  Create a POD in the finance namespace
  
Name: redis

Image name: redis

  ``` k run redis --image -n finance ```

Which namespace has the blue pod in it?

 ``` kubectl get pods --all-namespaces | grep blue ```
