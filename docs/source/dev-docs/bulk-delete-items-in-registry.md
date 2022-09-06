# Bulk delete items within Registry

```{toctree}
```


The deployment of Magda contains a PSQL Database that contains 8 tables. Those tables are as follows:
- aspects
- events
- recordaspects
- records
- schema_version
- webhookevents
- webhooks


Items are managed by the syntax of the recordid, aspectid, eventid, etc on the tables.

## Delete datasets in Registry

To delete multiple datasets within a registry we first have to identify the id syntax of the dataset you are trying to delete.

Example:

- A connector will have a name/id associated with the datasets and aspects it retrieves and append that name/id to the randomly generated id for a table.
    - **recordid**: "dist-connector-datagov-doa-033a537c7bcf84bd0669dd70e0fe7b6efb5761cd8f9e6c366dc058fdcd860de6"


### Delete items in record aspects

To bulk delete the datasets we have identified, we must delete the record aspects tied to those datasets. Run the following command but replace ID with the ID of the datasets to delete.

```sql
DELETE FROM public.recordaspects
WHERE recordid LIKE '%{ID}%'
```

***NOTE*** : KEEP % sign, this is a wildcard for the randomly generated id portion.

### Delete items in records

Once you have deleted all aspects associated with an ID, you can now run the following command to delete all datasets in the Registry.

```sql
DELETE FROM public.records
WHERE recordid LIKE '%{ID}%'
```