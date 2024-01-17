k=kubectl
cm = configmaps

Tip : You cannot edit a running pod imperatively , you need to delete it and recreate after your edits

Sample pod.yml with env config 

```
apiVersion: v2
kind: Pod
metadata:
  creationTimestamp: "2024-01-17T01:04:55Z"
  labels:
    name: webapp-color
  name: webapp-color
  namespace: default
  resourceVersion: "913"
  uid: 8bb4756c-3180-4628-b4a4-bed1f63714b7
spec:
  containers:
  - env:
    - name: APP_COLOR
      value: green
    image: kodekloud/webapp-color
    imagePullPolicy: Always
    name: webapp-color
    resources: {}
    terminationMessagePath: /dev/termination-log
    terminationMessagePolicy: File
    volumeMounts:
    - mountPath: /var/run/secrets/kubernetes.io/serviceaccount
      name: kube-api-access-mhj98
      readOnly: true
  dnsPolicy: ClusterFirst
  enableServiceLinks: true
  nodeName: controlplane
  preemptionPolicy: PreemptLowerPriority
  priority: 0
  restartPolicy: Always
  schedulerName: default-scheduler
  securityContext: {}
  serviceAccount: default
  serviceAccountName: default
  terminationGracePeriodSeconds: 30
  tolerations:
  - effect: NoExecute
    key: node.kubernetes.io/not-ready
    operator: Exists
    tolerationSeconds: 300

```


get all configmaps
``` k get cm ```

Create a new ConfigMap for the webapp-color POD. Use the spec given below.

ConfigMap Name: webapp-config-map

Data: APP_COLOR=darkblue

Data: APP_OTHER=disregard

``` k create cm webapp-config-map --from-literal APP_COLOR=darkblue --from-literal APP_OTHER=disregard   ```

usinf configMapKeyRef to fetch values from a configMap
```
apiVersion: v1
kind: Pod
metadata:
  creationTimestamp: "2024-01-17T01:04:55Z"
  labels:
    name: webapp-color
  name: webapp-color
  namespace: default
  resourceVersion: "913"
  uid: 8bb4756c-3180-4628-b4a4-bed1f63714b7
spec:
  containers:
  - env:
    - name: APP_COLOR
      valueFrom:
        configMapKeyRef:
          name: webapp-config-map
          key: APP_COLOR
    image: kodekloud/webapp-color

```
