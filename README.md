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
