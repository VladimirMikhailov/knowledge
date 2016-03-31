# Postgresql

## How to monitor

[wiki/Monitoring](https://wiki.postgresql.org/wiki/Monitoring) is
a good place to star overview of existing solutions.

[https://pganalyze.com/](https://pganalyze.com/) - Saas that gives a
quick overview of your existing pg instance (IO, Memory, CPU Usage, tables, indices, views
queries info)

## Where postgres does spend time

![Performance](/postgres/postgres-performance.png)

## Tuning

Postgresql has defatult set up settings in order to
work in a wide kind of machines (having low CPU and Memory).
You can achieve better performance by chanding settings a bit.

You can start exploring [wiki page](https://wiki.postgresql.org/wiki/Tuning_Your_PostgreSQL_Server)
or give a try to [PgTune as a Service](http://pgtune.leopard.in.ua/) or [pg_tune extension](https://github.com/gregs1104/pgtune).
