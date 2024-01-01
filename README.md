<!-- [![hacs_badge](https://img.shields.io/badge/HACS-Default-orange.svg)](https://github.com/hacs/integration) -->

# Custom qBittorrent card for HomeAssistant/Lovelace

This Lovelace custom card displays torrents information provided by the qBittorrent Integration.
You can cycle through the different torrent types by clicking on the type label.

### Installation

[TODO] The easiest way to install it is through [HACS (Home Assistant Community Store)](https://github.com/hacs/frontend),
search for *qBittorrent* in the Frontend section and select qBittorrent Card.<br />
If you are not using HACS, you may download qbittorrent-card.js and put it into
homeassistant_config_dir/www/community/qbittorrent-card/ directory.<br />

This requires changes to the qBittorrent made in Home Assistant version 2024.02. Please make sure you are at least on that version.

### Lovelace UI configuration

Please add the card to the resources in configuration.yaml:

```
resources:
  - {type: js, url: '/hacsfiles/qbittorrent-card/qbittorrent-card.js'}
```

### Options

#### Card options

| Name                     | Type         | Required     | Default                 | Description                          |
| -------------------------| ------------ | ------------ | ----------------------- | ------------------------------------ |
| type                     | string       | **required** |                         | `custom:qbittorrent-card`           |
| no_torrent_label         | string       | optional     | `No Torrents`           | label displayed with no torrents     |
<!-- | hide_turtle              | boolean      | optional     | false                   | hide turtle button                   | -->
| hide_startstop           | boolean      | optional     | false                   | hide start/stop button               |
| hide_type                | boolean      | optional     | true                    | hide type of torrents displayed      |
| default_type             | string       | optional     | `all`                 | type of torrents to display at start |
| display_mode             | string       | optional     | `compact`               | display mode: compact or full        |
| sensor_name              | string       | optional     | `qbittorrent`          | DEPRECATED. Name of the sensor. Use sensor_entity_id instead. It will be removed in a later release. |
| sensor_entity_id         | string       | optional     | `qbittorrent`          | name of the sensor. Useful when using different entity name either deliberately or by e.g. HA generating localized entity name/id |
| hide_header              | boolean      | optional     | false                   | hide header text at the top of card  |
| header_text              | string       | optional     | `qBittorrent`          | header text at the top of card       |
<!-- | hide_add_torrent         | boolean      | optional     | false                   | hide add torrent input               |
| hide_delete_torrent      | boolean      | optional     | false                   | hide delete torrent button           |
| hide_delete_torrent_full | boolean      | optional     | false                   | hide delete torrent with data button | -->
| hide_torrent_list        | boolean      | optional     | false                   | hide torrent list |

Accepted values for default_type are: `all`, `active`, `inactive`, `completed`, `paused`, `downloading`, `seeding`.

Please find below an example of ui-lovelace.yaml card entry:

```yaml
    cards:
      - type: custom:qbittorrent-card
        hide_type: false
        default_type: 'active'
```

Transmission idle in compact mode:

![qBittorrent idle](https://raw.githubusercontent.com/finder39/qbittorrent-card/main/transmission_idle.jpg)

Transmission downloading in full mode:

![qBittorrent downloading](https://raw.githubusercontent.com/finder39/qbittorrent-card/main/qbittorrent_downloading_full_mode.jpg)

## Thanks

This card is built off of [axamimus's Transmission Card](https://github.com/amaximus/transmission-card). If you want to donate, please donate on their github repo page!

Thanks to all the people who have contributed!

[![contributors](https://contributors-img.web.app/image?repo=finder39/qbittorrent-card)](https://github.com/finder39/qbittorrent-card/graphs/contributors)
