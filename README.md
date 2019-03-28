# sensor.feedparser
RSS feed custom component for [Home Assistant](https://www.home-assistant.io/) which can be used in conjunction with the custom [Lovelace](https://www.home-assistant.io/lovelace) [list-card](https://github.com/custom-cards/list-card)

[![GitHub Release][releases-shield]][releases]
[![License][license-shield]](LICENSE.md)

![Project Maintenance][maintenance-shield]
[![GitHub Activity][commits-shield]][commits]

[![Discord][discord-shield]][discord]
[![Community Forum][forum-shield]][forum]

## Support
Hey dude! Help me out for a couple of :beers: or a :coffee:!

[![coffee](https://www.buymeacoffee.com/assets/img/custom_images/black_img.png)](https://www.buymeacoffee.com/zJtVxUAgH)

To get started put `/custom_components/feedparser/sensor.py` here:
`<config directory>/custom_components/feedparser/sensor.py`

**Example configuration.yaml:**

```yaml
sensor:
  platform: feedparser
  name: Engineering Feed
  feed_url: 'https://www.sciencedaily.com/rss/matter_energy/engineering.xml'
  date_format: '%a, %b %d %I:%M %p'
  inclusions:
    - title
    - link
    - description
    - image
    - language
    - pubDate
  exclusions:
    - language
```

**Configuration variables:**

key | description
:--- | :---
**platform (Required)** | The platform name
**name (Required)** | Name your feed
**feed_url (Required)** | The RSS feed URL
**date_format (Optional)** | strftime date format for date strings **Default** `%a, %b %d %I:%M %p`
**inclusions (Optional)** | List of fields to include from populating the list
**exclusions (Optional)** | List of fields to exclude from populating the list

***

Note: Will return all fields if no inclusions or exclusions are specified

Due to how `custom_components` are loaded, it is normal to see a `ModuleNotFoundError` error on first boot after adding this, to resolve it, restart Home-Assistant.

**How to find inclusions**
To find inclusions for your RSS feed open your RSS feed in a new window in your browser
Then you should see a bunch of entries with each one you want starting with '<title>' for example.
  You can also leave out the inclusions part in your configuration.yaml, then if you head over to Home Assistant and under Dev Tools open the 'states' which has the <> logo and find your RSS sensor and all available inclusions will be there, just remove "".

[commits-shield]: https://img.shields.io/github/commit-activity/y/custom-components/sensor.feedparser.svg?style=for-the-badge
[commits]: https://github.com/custom-components/sensor.feedparser/commits/master
[discord]: https://discord.gg/Qa5fW2R
[discord-shield]: https://img.shields.io/discord/330944238910963714.svg?style=for-the-badge
[forum-shield]: https://img.shields.io/badge/community-forum-brightgreen.svg?style=for-the-badge
[forum]: https://community.home-assistant.io/t/custom-component-rss-feed-parser/64637
[license-shield]: https://img.shields.io/github/license/custom-components/sensor.feedparser.svg?style=for-the-badge
[maintenance-shield]: https://img.shields.io/badge/maintainer-Ian%20Richardson%20%40iantrich-blue.svg?style=for-the-badge
[releases-shield]: https://img.shields.io/github/release/custom-components/sensor.feedparser.svg?style=for-the-badge
[releases]: https://github.com/custom-components/sensor.feedparser/releases
