

Deploy a pod named nginx-pod using the nginx:alpine image.
``` k run nginx-pod --image=nginx:alpine ```

Deploy a redis pod using the redis:alpine image with the labels set to tier=db
Pod Name: redis

Image: redis:alpine

Labels: tier=db
```  k run redis --image=redis:alpine --labels tier=db ```

Create a service redis-service to expose the redis application within the cluster on port 6379
Service: redis-service

Port: 6379

Type: ClusterIP
``` kubectl expose pod redis --port=6379 --name redis-service ```

Create a deployment named webapp using the image kodekloud/webapp-color with 3 replicas.


Name: webapp

Image: kodekloud/webapp-color

Replicas: 3

```  k create deploy webapp --image=kodekloud/webapp-color --replicas=3 ```


Create a new pod called custom-nginx using the nginx image and expose it on container port 8080.

``` kubectl run custom-nginx --image=nginx --port=8080 ```

Create a new namespace called dev-ns.
``` k create ns dev-ns ```

Create a new deployment called redis-deploy in the dev-ns namespace with the redis image. It should have 2 replicas.
redis-deploy' created in the 'dev-ns' namespace?

replicas: 2

``` k create deploy redis-deploy --image=redis --replicas=2 -n dev-ns ```

Create a pod called httpd using the image httpd:alpine in the default namespace. Next, create a service of type ClusterIP by the same name (httpd). The target port for the service should be 80.


'httpd' pod created with the correct image?

'httpd' service is of type 'ClusterIP'?

'httpd' service uses correct target port 80?

'httpd' service exposes the 'httpd' pod?

``` k run httpd --image=httpd:alpine --port=80 --expose ```
