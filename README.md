# AWS Retail Sales Lakehouse (S3 + Glue + Athena)

No QuickSight in this release.

## Code map
- [`sql/`](./sql/) — Athena SQL (saved queries & transformations for Silver/Gold/views).
- [`ddl/`](./ddl/) — One file per table with `SHOW CREATE TABLE` (schema only).

## How to reproduce (Athena)
1. Run `sql/00_database.sql`.
2. Create/refresh Silver (your pipeline) and `MSCK REPAIR TABLE retailsales_lake_db.silver_retailsales;`
3. Run `sql/02_gold_create.sql` then `sql/03_gold_insert.sql`.
4. Optional: `sql/04_views.sql` & `sql/05_enriched_view.sql`.

