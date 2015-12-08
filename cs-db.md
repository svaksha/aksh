+ [Postgres-XC](#postgres-xc)

====

# Postgres-XC
+ http://www.postgresql.org/download/

WARNING: enabling "trust" authentication for local connections
You can change this by editing pg_hba.conf or using the option -A, or
--auth-local and --auth-host, the next time you run initdb.

Success.
 You can now start the database server of the Postgres-XC coordinator using:

    postgres --coordinator -D DN2
or
    pg_ctl start -D DN2 -Z coordinator -l logfile

 You can now start the database server of the Postgres-XC datanode using:

    postgres --datanode -D DN2
or 
    pg_ctl start -D DN2 -Z datanode -l logfile

 * Starting Postgres-XC datanode                                                                                                                             [ OK ] 
 * Starting Postgres-XC coordinator                                                                                                                          [ OK ] 
 * Starting Postgres-XC gtm                                                                                                                                  [ OK ] 
 pgxc_pool_reload 


+ https://wiki.openstreetmap.org/wiki/PostgreSQL
+ https://help.openstreetmap.org/questions/11102/example-postgres-queries-for-osm
+ https://wiki.openstreetmap.org/wiki/Osm2pgsql/schema

----

# SQL Temporal data
+ [groupdate.sql](https://github.com/ankane/groupdate.sql) :: The simplest way to group temporal data.

----

