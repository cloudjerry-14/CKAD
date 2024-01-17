
get all secrets 
``` k get secrets ```

The reason the application is failed is because we have not created the secrets yet. Create a new secret named db-secret with the data given below.
Secret Name: db-secret

Secret 1: DB_Host=sql01

Secret 2: DB_User=root

Secret 3: DB_Password=password123

``` k create secret generic db-secret --from-literal=DB_Host=sql01 --from-literal=DB_User=root --from-literal=DB_Password=password123 ```
