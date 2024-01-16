k=kubectl
deploy=deployment

How many deployments exist?
``` k get deploy ```

create deployment imperative

Save deployment to a configuration file
``` k create deploy my-deployment --image=nginx --replicas=10 -o yaml > deployment.yaml ```

create deployment using the yaml file 

``` k create -f deployment.yaml ```

inspect deployment 
``` k describe deploy my-deployment ```


delete deployment

``` k delete deploy my-deployment ```
