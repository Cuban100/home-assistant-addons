# Home Assistant Addons

Personal collection of customized/forked Home Assistant add-ons. Add this repository in
Home Assistant via **Settings → Add-ons → Add-on Store → ⋮ → Repositories**:

```
https://github.com/Cuban100/home-assistant-addons
```

## Add-ons

### audiobookshelf

Forked from [petersendev/hassio-addons](https://github.com/petersendev/hassio-addons), with
one change: added `media:rw` to the add-on's folder mappings so Audiobookshelf can see the
`/media` folder (the upstream version only mapped `config` and `share`).

### hydra2

Forked from [petersendev/hassio-addons](https://github.com/petersendev/hassio-addons), which
had gone stale since January 2023 (pinned to nzbhydra2 v4.7.6-ls83). Changes made here:

- Updated to the current [linuxserver/nzbhydra2](https://github.com/linuxserver/docker-nzbhydra2) image.
- Dropped `armhf` from supported architectures — linuxserver no longer publishes 32-bit ARM
  builds for this image, only `amd64`/`aarch64`.
- Added `media:rw` to the add-on's folder mappings (upstream only mapped `config` and `share`).
- The build now floats on linuxserver's `latest` tag per architecture, and a
  [scheduled GitHub Action](.github/workflows/bump-hydra2.yml) checks daily for new upstream
  releases and bumps the add-on's version automatically, so Home Assistant surfaces "Update
  available" whenever nzbhydra2 itself updates.
- Bumped the bundled `bashio` from 0.7.1 to 0.18.1.
