# 1. Create a namespace called mynamespace and a pod with image nginx called nginx on this namespace

 ```
kubectl create ns mynamespace 
kubectl run nginx --image=nginx -n mynamespace
```
