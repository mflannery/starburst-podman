# How to run Starburst in podman

First create a folder to hold the data catalog properties files in your local directory

```mkdir -p ~/starburst/catalog```

Next put your starburst license in ~/starburst

```cp starburst.license ~/starburst```

When selinux is running

```podman run -d -p 8080:8080 --volume /home/mike/starburst:/etc/starburst:Z --name starburst starburstdata/starburst-enterprise:latest```

When selinux is disabled

```podman run -d -p 8080:8080 --volume /home/mike/starburst:/etc/starburst --name starburst starburstdata/starburst-enterprise:latest```

Next create your data catalogs and put them in ~/starburst/catalog and then restart the trino container

```podman restart starburst```

