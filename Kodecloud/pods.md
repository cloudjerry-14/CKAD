k= kubectl
po= pods


**Que:** How many pods exist on the system?
**Ans:** ``` k get po ```

**Que:** Create a new pod with the nginx image.
**Ans:** ``` controlplane ~ ✖ k run nginx --image=nginx --restart=Never ```

describe po
k describe po nginx

Delete pod nginx
K delete po nginx
