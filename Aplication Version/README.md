# STEPS OF PREPARE NEW VERSION of Medio App

## From server to local

### Case: Server as old version VS local already new version

1. Clone to local.
2. Edit database.yml give new database name.
3. Make it App run first.
3. SQL dump from db server.
4. Restore SQL into new database.
5. Run with its db from server before.

Case: 

cmpbatam version 1.00 db cmpbatam
cmpbatam version 1.01 db cmpbatam_dev

Db availabe:

cmpbatam_dev: old
cmpbatam_v101: new