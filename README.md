# pretix-docker_compose
A full config to run pretix with docker-compose

Create folderstructure
```
mkdir -p data
mkdir -p conf
chown -R 15371:15371 data
chown -R 15351:15371 conf
mkdir -p postgres
```

copy example pretix.cfg to conf/pretix.cfg
```
cp pretix.cfg conf/pretix.cfg
```

Than run the docker-compose file and create a new cronjob to run the internal pretix jobs.

```
15,45 * * * * /usr/bin/docker exec pretix_app pretix cron
```

After starting the stack navigate to:
https://pretix.yourdomain.com/control/

The default user is: admin@localhost

And the default password is: admin

Change this settings!
