# databricks-medallion-pipeline

Goals: 

  1- Ingest raw data as-is. Bronze = raw, no transformations, keep bad records to preserve full history.
  
  2- Transform Bronze to Silver: cast types, filter bad records, deduplicate, and use MERGE INTO for incremental updates instead of overwriting the whole table.
  
  3- Build Gold layer objects: a stored aggregate table, a view, and data quality checks on the Silver output.
  
Summary :  Bronze = raw (everything). Silver = valid, typed, deduplicated. Gold = business aggregations ready for BI/analytics.
