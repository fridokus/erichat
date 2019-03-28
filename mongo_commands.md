# These commands should be executed in the mongo container

First go to the mongo container by doing

```
kubectl get po
```

Copy pod name of mongo

```
kubectl exec -it <mongo pod name> sh
```

Now we're in the mongo container in the mongo pod

```
mongo

use admin

db.createUser(
  {
    user: "root",
    pwd: "password",
    roles: [ { role: "userAdminAnyDatabase", db: "admin" } ]
  }
)
```
