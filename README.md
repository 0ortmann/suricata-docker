Suricata Docker
===============

- Builds [Suricata IDS](https://suricata-ids.org/) from scratch (github master)
- Container base is `debian:stretch`
- Build stages to separate install dependencies
- Enables `python 3` helper script `suricata-update` inside the container 

### Usage

You can mount a directory to `/etc/suricata` with a custom `suricata.yaml` in it to override what is baked into the container image.

### Build

    $ docker build . -t fixel/suricata
    
### Run

You can find a container image on docker hub: [fixel/suricata](https://cloud.docker.com/repository/docker/fixel/suricata)

The container expects that you pass arguments to it, everything is passed to the `suricata` command. To listen on the interface `enp0s31f6` you would run this:

    $ docker run --net=host --name=suricata -ti fixel/suricata -i enp0s31f6

The logs will be stored in `/var/log/suricata`, which is marked as docker volume. You can extract them by the usual means of container management.