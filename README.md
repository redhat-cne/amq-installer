# amq-installer
amq installer for openshift 4.9 

### AMQ installer for cloud native proxy, the producer , consumer and amq messaging bus runs locally on every node.
Local producer talks to local consumer via local  messaging router.

```
|----------------------------------------------------------|
|  Node A                                                  |
|  |------------|         |----------|      |----------|   |
|  | producer   |   ->    | Router   |  ->  | consumer |   |
|  --------------          ----------       -----------    |
|----------------------------------------------------------|

---
---
|----------------------------------------------------------|
|  Node D                                                  |
|  |------------|         |----------|      |----------|   |
|  | producer   |   ->    | Router   |  ->  | consumer |   |
|  --------------          ----------       -----------    |
|----------------------------------------------------------|

``` 

This scripts will installs qdr router on nodes with a node label `worker` and available to access via port amqp://router.router.svc.cluster.local

### To Install
```
make deploy
```

### Check installation
```
 oc get pods -n router
```

### To Uninstall
```
make undeploy
```
