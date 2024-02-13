# kasm-addons
A few helpful addons for Kasm Workspaces

## Initial setup

To import all of the addons, run these commands:

```
cd /opt/kasm/bin
git clone https://github.com/TylerSelden/kasm-addons
cd kasm-addons
chmod +x ./*
```

This will create a directory called `kasm-addons` inside of `/opt/kasm/bin`, inside of which all the scripts are stored.

## db_access

To use this addon, simply run:

`/opt/kasm/bin/kasm-addons/db_access`

This gives you full access to the Postgres database that Kasm uses.

## db_query

To use this addon, simply run:

`/opt/kasm/bin/kasm-addons/db_access "[Your SQL Query]`, replacing `[Your SQL Query]` with the SQL query you want to run.

This will run a single SQL query in the Postgres database.

## kasm_keepalive

To use this addon, run these commands:

```
cd /opt/kasm/bin
./stop
```

Wait for Kasm to stop completely, which might take several minutes. Then, run this to install the add-on:

```
echo "# Keepalive Add-on
./kasm-addons/kasm_keepalive &" >> start
echo "# Keepalive Add-on
kill $(pgrep -f ./kasm-addons/kasm_keepalive)" >> stop
```

Finally, start Kasm again.

```
./start
```

This addon will prevent any Kasm session from expiring, which is especially useful when using the free version.
