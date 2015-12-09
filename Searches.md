# Search Plugins

FlexGet provides framework for plugins meant for querying searches from supported sites. These cannot be used directly in a task, but can be used with the [urlrewrite_search](/Plugins/urlrewrite_search) & [discover](/Plugins/discover) plugins where they act like options for their parent plugins. This page lists these options and gives a brief description of their function.


## Overview



| **Keyword** | **Description** |
| --- | --- |
| [btn](/Searches/btn) | Searches private torrent site BTN |
| [cpasbien](/Searches/cpasbien) | Generates entries from [cpasbien.pw](http://www.cpasbien.pw/) |
| [flexget_archive](/Searches/flexget_archive) | Searches within previously archived entries |
| [freshon](/Searches/freshon) | Generates entries from [freshon.tv](http://freshon.tv) |
| [iptorrents](/Searches/iptorrents) | Generates entries from [iptorrents.com](http://iptorrents.com) |
| [isohunt](/Searches/isohunt) | Generates entries from [isohunt.com](http://isohunt.com) |
| [kat](/Searches/kat) | Generate entries from [kat.ph](http://kat.ph) |
| newtorrents | Generates entries from [newtorrents.info](http://newtorrents.info) |
| newzleech | Broken as Newzleech.com is no more |
| [newznab](/Searches/urlrewrite_newznab) | Generates entries from [newznab.com](http://newznab.com) |
| [nyaa](/Searches/nyaa) | Generates entries from [nyaa.se](http://nyaa.se/) |
| [piratebay](/Searches/piratebay) | Generates entries from [thepiratebay](http://thepiratebay.gl/) |
| [ptn](/Searches/ptn) | Searches private torrent site PtN |
| [publichd](/Searches/publichd) | Generates entries from [PublicHD](http://publichd.se/) |
| [rarbg](/Searches/rarbg) | Generates entries from [RarBG](http://rarbg.com/) |
| [sceneaccess](/Searches/sceneaccess) | Searches private torrent site sceneaccess |
| [search_rss](/Searches/search_rss) | Generates query based rss feeds |
| [torrent411](/Searches/t411) | Generates entries from [t411.me](http://www.t411.me/) |
| torrentshack | Searches private torrent site torrentshack |
| [torrentleech](/Searches/torrentleech) | Generates entries from [torrentleech.org](http://torrentleech.org/) |
| [torrentz](/Searches/torrentz) | Generates entries from [torrentz.eu](http://torrentz.eu) |
| whatcd | Searches private torrent site whatcd |


You can always get an up to date overview of the available search plugins by using the command line. On Flexget>=1.2, the command is now 'flexget plugins --group search', and documentation for a plugin can be obtained with 'flexget doc <plugin-name>'.

** Example **
```
flexget plugins --group search
-- Supported search plugins: --------------------------------------------------
 search_rss
 piratebay
 newzleech
 flexget_archive
 newtorrents
 torrentz
-------------------------------------------------------------------------------
```