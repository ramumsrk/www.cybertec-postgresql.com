# [Enhanced security: Logging PostgreSQL connections](https://www.cybertec-postgresql.com/en/enhanced-security/)

#### paragraph 1

1. sus-pi-cious

## Using ````log_connections```` in PostgreSQL

I was able to see the following entries in ````/var/lib/pgsql/18/data/log/postgresql-Thu.log```` after either uncommenting or adding following entries to configuration file ````/var/lib/pgsql/18/data/postgresql.conf````

```text
log_connections = all
log_disconnections = on
```

```text
2025-11-06 13:18:05.348 IST [21449] LOG:  00000: connection received: host=[local]
2025-11-06 13:18:05.348 IST [21449] LOCATION:  BackendInitialize, backend_startup.c:230
2025-11-06 13:18:05.351 IST [21449] LOG:  00000: connection authenticated: user="pagila" method=trust (/run/media/ramumsrk/v210w_4.0GiB/var/lib/pgsql/18/data/pg_hba.conf:11)
2025-11-06 13:18:05.351 IST [21449] LOCATION:  ClientAuthentication, auth.c:656
2025-11-06 13:18:05.351 IST [21449] LOG:  00000: connection authorized: user=pagila database=pagila application_name=psql
2025-11-06 13:18:05.351 IST [21449] LOCATION:  PerformAuthentication, postinit.c:309
2025-11-06 13:18:05.354 IST [21449] LOG:  00000: connection ready: setup total=9.743 ms, fork=2.870 ms, authentication=1.150 ms
2025-11-06 13:18:05.354 IST [21449] LOCATION:  PostgresMain, postgres.c:4676
```