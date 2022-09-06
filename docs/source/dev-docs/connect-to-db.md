# Connecting to MAGDA Databases

```{toctree}
```

MAGDA consists of multiple Postgres database that are located in pods that are hosted on AWS EKS. In order to access these databases there are a couple of steps to follow.

1. Set up port forwarding to the postgres database 
    
    `kubectl port-forward combined-db-0 5432`

      or 

   `kubectl port-forward combined-db-postgresql-0  5432`


Your terminal should now say "Forwarding from ...."

2. Open up another terminal and connect to the postgres database with:

    `PGPASSWORD="{DB_PASSWORD}" psql --host 127.0.0.1 -U postgres -d postgres -p 5432`

 