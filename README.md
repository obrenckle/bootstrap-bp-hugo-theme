# Bootstrap-BP hugo theme fork

This theme is a fork of the [Bootstrap-BP hugo theme](https://github.com/spech66/bootstrap-bp-hugo-theme) by [Sebastian Pech](https://www.spech.de). It introduces a few changes made to suit my tastes, but any bug fix should be send upstream. Don't hesitate to notify me if I forget to do that.

You should start with the README found in the original repository, or the copy on this repository named README_UPSTREAM.md

## Changes from upstream

### Fork-Awesome instead of Font-Awesome

Icons are taken from Fork-Awesome instead of Font-Awesome

### Customizable RSS Content

`params.rss_content_type = "full"` output the full content of pages in the rss feed. Anything else output the summaries.

You can filter which type of page will be included in the rss feed
`params.rss_include_type` is a list of strings containing the types that will be included in the rss feed. An `"*"` includes all types.
`params.rss_exclude_type` is a list of strings containing the types that will be excluded from the rss feed.

Exclusion are computed after inclusion, so:
```
params.rss_include_type = ["page"]
params.rss_exclude_type = ["page"]
```
will result in an empty rss feed.

### Add some social media options

Additional options:

- [BoardGameGeek](https://boardgamegeek.com/)
- [Funkwhale](https://funkwhale.audio/)
- [Matrix](https://matrix.org/)
- [Nextcloud](https://nextcloud.com/)
- [Peertube](https://joinpeertube.org/)
- [Spotify](https://open.spotify.com/)

### Move social media parameters to params.social in config file

As it says in the title. See the `layouts/partials/social.html` to know what parameters are expected. Most of the time it's the username as a string, but for decentralized networks it's usually a map with a `user` and an `instance` key (e.g. `mastodon = {instance = "instance.org", user = "username"}`).

### lazysizes lazy loader

[lazysizes](https://github.com/aFarkas/lazysizes) is a fast (jank-free), SEO-friendly and self-initializing lazyloader for images (including responsive images picture/srcset), iframes, scripts/widgets and much more. It also prioritizes resources by differentiating between crucial in view and near view elements to make perceived performance even faster.

### Hugo version in footer

### Fork-awesome shortcode

Use `{{% forkawesome param %}}` to output forkawesome icons. The param is the part that goes after `fa-` in the fork-awesome tag class. Multiple parameters can be present, leading to multiple `fa-...` in a single tag, but I don't know if that's useful.

### Add Fork-awesome icon in page title

Use the `titleicon` parameter in a page front matter to add a Fork-awesome icon at the beginning of a page title. The parameter value is the part that goes after `fa-` in the fork-awesome tag class.

### Add Emoji in page title

Use the `titleemoji` parameter in a page front matter to add an emoji at the beginning of a page title. The parameter value is the part that goes between the `:`.

### Output content in List type

Any page that use the default List template will actually output the page content before the listed sub-pages.

### Add a default Section template

### Fix (?) the SEO content

Not sure if I did this right, but the main page is of type Blog, individual blog posts are of type BlogPosting, and pages are of type WebPage.
