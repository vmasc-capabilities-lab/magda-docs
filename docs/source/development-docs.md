# Developer Documentation

```{toctree}
/dev-docs/dev-tools.md
/dev-docs/connect-to-db.md
/dev-docs/connect-k8-internal-api.md
/dev-docs/bulk-delete-items-in-registry.md
/dev-docs/create-docker-image.md
```

## Connecting to MAGDA Databases
MAGDA consists of multiple Postgres database that are located in pods that are hosted on AWS EKS. In order to access these databases there are a couple of steps to follow.

1. Set up port forwarding to the postgres database 
    
    `kubectl port-forward combined-db-0 5432`

or 

   `kubectl port-forward combined-db-postgresql-0  5432`


Your terminal should now say "Forwarding from ...."

2. Open up another terminal and connect to the postgres database with:

    `PGPASSWORD="{DB_PASSWORD}" psql --host 127.0.0.1 -U postgres -d postgres -p 5432`


## Connecting to Kubernete Pods + Using Internal API commands

The process below is not recommended for altering the containers environment but we can use it to do things such as using Internal API commands that require us to be within the pod to access.

First you must figure out the pod you wish to connect to. You can do this by using kubectl:

`kubectl get pods`

To connect to the pod:

`kubectl exec -it {POD_NAME} -- /bin/sh`

## Creating Docker Images and deploying

As shown in [https://github.com/magda-io/magda/blob/master/deploy/helm/internal-charts/web-server/README.md](Web-Server Helm chart config), if you want to change the image of a particular Magda component you need to reference the root repository/organization. When the helm chart is built, it appends the Magda name to the component then retrieve the image.
