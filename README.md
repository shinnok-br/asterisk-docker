# Asterisk container running on Docker

A simple Asterisk container.

Instructions to start:

1) Running pure Asterisk

If you want to run Asterisk with the defaults configurations, just execute:

```bash
docker run --name asterisk --net=host -d -t shinnok/asterisk
```


2) Running Asterisk with your configuration files, you can create volumes:

```bash
docker run --name asterisk --net=host -v YOUR_CONFIG_DIRECTORY:/etc/asterisk/ -d -t shinnok/asterisk
```

