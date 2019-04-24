# Postgres


```bash
# persisting a csv file
psql -h localhost -p 5434 -U postgres -d warehouse -c "\COPY netsuite.csv_sales_orders(lastmodifieddate, sales_order) FROM '/Users/kassiomachado/Downloads/feb_2_so_rec.csv' DELIMITER ',' CSV HEADER;"
```

```bash
# restoring backup
psql -h localhost -p 5434 -U postgres -d warehouse -f filename
```