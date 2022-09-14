# Design Decisions

```{toctree}
```

## Database Scaling
* **Problem:** MAGDA can operate on a four separate Postgres database (production) or one combined database (development). Our MAGDA instance currently runs on the combined database structure so the question is whether or not we should upgrade to the production databases?
* **Decision:**
Our user base will most likely never reach the amount that would justify the need for a production level environment. MAGDA will continue to run on a single combined database until we reach the point where a production level environment is needed.