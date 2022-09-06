# Connecting to Kubernete Pods + Using Internal API commands

```{toctree}
```

The process below is not recommended for altering the containers environment but we can use it to do things such as using Internal API commands that require us to be within the pod to access.

First you must figure out the pod you wish to connect to. You can do this by using kubectl:

`kubectl get pods`

To connect to the pod:

`kubectl exec -it {POD_NAME} -- /bin/sh