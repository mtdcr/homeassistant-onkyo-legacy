# homeassistant-onkyo-legacy

This is a custom component based on the onkyo integration of [Home Assistant](https://github.com/home-assistant/core) 2024.6.4. It was created, because version 2024.7 broke many setups for months. At the time of writing, no short-term fix was foreseeable.

## Upstream issue

- *Onkyo integration fails to connect and then fails to sleep after upgrade to 2024.7* [#121882](https://github.com/home-assistant/core/issues/121882)

## Reproduction

This repository was initialized using [git-filter-repo](https://github.com/newren/git-filter-repo) with the following command-line:

```sh
git clone -b dev --single-branch https://github.com/home-assistant/core.git homeassistant-onkyo-legacy
cd homeassistant-onkyo-legacy
git filter-repo \
  --path homeassistant/components/media_player/onkyo.py \
  --path homeassistant/components/onkyo \
  --path-rename homeassistant/components/media_player/onkyo.py:custom_components/onkyo/media_player.py \
  --path-rename homeassistant/components/onkyo:custom_components/onkyo
git checkout -b main 2024.6.4
```
