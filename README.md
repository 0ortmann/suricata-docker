Suricata Docker
===============

- Builds [Suricata IDS](https://suricata-ids.org/) from scratch (github master)
- Container base is `debian:stretch`
- Build stages to separate install dependencies
- Enables `python 3` helper script `suricata-update` inside the container 

### Usage

You can mount a directory to `/etc/suricata` with a custom `suricata.yaml` in it to override what is baked into the container image.