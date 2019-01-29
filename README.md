Suricata Docker
===============

- Builds [Suricata IDS](https://suricata-ids.org/) from scratch (github master)
- Container base is `debian:stretch`
- Build stages to separate install dependencies
- Enables `python 3` helper script `suricata-update` inside the container 

### Usage

You can mount a directory to `/etc/suricata` with a custom `suricata.yaml` in it to override what is baked into the container image.

### Run

    $ docker build . -t suricata-docker
    $ docker run --net=host suricata-docker

The logs will be stored in `/var/log/suricata`. You can extract them by the usual means of container management: mount a volume in there, mount this containers volume somewhere else or use syslog.