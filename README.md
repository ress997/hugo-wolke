Wolke
===
This theme was created based on [ress997/Robust](https://github.com/ress997/hugo-robust).

## Features
- Responsive design
- Google Analytics
- Disqus
- Atom Feed
- AMP (Accelerated Mobile Pages)
- PWA (Progressive Web Apps)
- Lazy Loading Images
- Social Share
	- Mastodon
	- Twitter
	- Facebook
	- Google+
	- Pocket
	- LINE
	- Hatena Bookmark
- Resource Hints

### Installation
```sh
cd path/to/hugo
git submodule add https://github.com/ress997/hugo-wolke themes/wolke
```

## `config.toml` example
```toml
baseurl = "https://example.com/"
title = "SiteTitle"
theme = "wolke"

googleAnalytics = "UA-XXXXXXXX-XX" # Optional
disqusShortname = "XYW" # Optional

[params]
description = "This is site description"
dateformat = "Jan 2, 2006" # Optional

# enable latests (default: false)
enableSideLatests = true # Optional

[params.fonts]
# Fonts setting

# Optional, Override body font family.
# (default: "arial, sans-serif")
fontfamily = "Roboto, sans-serif"

# Optional, Include google fonts.
googlefonts = "https://fonts.googleapis.com/css?family=Roboto:400,700"

[params.images]
# Images setting

# favicon, rel=icon
# (default: "img/icon.png")
icon = "img/favicon.png"

# default thumbnail
# (default: "img/thumb.png")
thumbnail = "img/ogp.png"

# setting Lazy Load for images
# (default: false)
lazyload = true

[params.author]
name = "John Doe"
thumbnail = "img/author.png"
description = "This is author description."

mastodon = "https://mastodon.social/@mastodon"
twitter = "twitter"
facebook = "XXXX"
github = "github"
```

### Atom Feed の有効化
```toml
[mediaTypes."application/atom"]
suffixes = ["xml"]

[outputFormats.ATOM]
mediaType = "application/atom"
baseName = "atom"
isPlainText = false

[outputs]
# default: ["HTML", "RSS"]
home = ["HTML", "RSS", "ATOM"]
```

### AMP の有効化
```toml
[outputs]
# default: ["HTML"]
page = ["HTML", "AMP"]
```

### PWA の有効化
```toml
[params.pwa]
# PWA setting

# manifest.json
manifest = "/manifest.json"

# Service Worker Script
script = "/sw.js"
# AMP: Service Worker Script Install page
iframe = "/sw.html"
```

設定されたファイルを読み込みます。

### Social Share
シェアボタンを非表示にするには以下のようにすることで可能です。

```toml
[Params]
# default: true
socialShare = false
```

特定のページのみシェアボタンを非表示にするには以下のように TOML Front-matter を記述することで可能です。

```md
+++
socialShare = false
+++
```

## shortcode
一部 shortcode は公式のものを使用しています。

### Image
```html
{{< img src="images/image.jpg" w="600" h="400" >}}
{{< img src="images/image.jpg" w="600" h="400" caption="Referenced from wikipedia." href="https://en.wikipedia.org/wiki/Lorem_ipsum" >}}
```

### Gist
```html
{{< gist id="gistID" file="file" >}}
```

### Twitter
```html
{{< twitter id >}}
```

### YouTube
```html
{{< youtube id="youtubeID" >}}
{{< youtube id="youtubeID" autoplay="true" >}}
```