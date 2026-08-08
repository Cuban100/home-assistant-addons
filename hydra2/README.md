# Home Assistant Add-ons by Cuban100: HYDRA2

Forked from [petersendev/hassio-addons](https://github.com/petersendev/hassio-addons), which
had gone stale (pinned to nzbhydra2 v4.7.6-ls83 since January 2023). Changes made here:

- Updated to the current [linuxserver/nzbhydra2](https://github.com/linuxserver/docker-nzbhydra2) image.
- Dropped `armhf` from supported architectures — linuxserver no longer publishes 32-bit ARM
  builds for this image, only `amd64`/`aarch64`.
- Added `media:rw` to the add-on's folder mappings so hydra2 can see the `/media` folder
  (the upstream version only mapped `config` and `share`).
- The Docker build now floats on linuxserver's `latest` tag per architecture, and a
  [scheduled GitHub Action](../.github/workflows/bump-hydra2.yml) checks daily for new
  upstream releases and bumps this add-on's version automatically, so Home Assistant will
  show "Update available" whenever nzbhydra2 itself updates. Triggering that update in the
  Home Assistant UI rebuilds the add-on and pulls whatever is current at that time.
- Bumped the bundled `bashio` from 0.7.1 to 0.18.1.

## About

[Hydra2](https://github.com/theotherp/nzbhydra2) is a meta search application for NZB indexers, the "spiritual successor" to NZBmegasearcH, and an evolution of the original application [NZBHydra](https://github.com/theotherp/nzbhydra).

It provides easy access to a number of raw and newznab based indexers.

This addon is based on the [docker image](https://github.com/linuxserver/docker-nzbhydra2) from linuxserver.io.

## Installation

1. [Add this add-ons repository][repository] to your Home Assistant instance.
1. Install this add-on.
1. Click the `Save` button to store your configuration.
1. Start the add-on.
1. Check the logs of the add-on to see if everything went well.
1. Carefully configure the add-on to your preferences, see the official documentation for that.

## Configuration

Webui can be found at `<your-ip>:5076`.

[repository]: https://github.com/Cuban100/home-assistant-addons
