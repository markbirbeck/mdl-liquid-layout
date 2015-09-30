# layout-liquid-mdl

A set of layout files that implement the layout part of Google's [Material Design Lite](http://www.getmdl.io/) templates.

## Dependencies

This layout requires a CSS file called `main.css`.

## Overrides

If using Markheim then any partial can be overridden by placing a partial of the same name in a higher priority directory. For example, to use a different CSS file than `main.css` simply create a partial called `head-styles.html` and ensure Markheim has access to it; Markheim will then use it in preference to the `head-styles.html` partial in this module.

More information on this process will follow when Markheim becomes available.

## Layouts

MDL provides a number of layouts. So far only the `entry.html` file has been converted, from the `blog` template.

## Partials

A collection of partials.

### google-tag-manager.html

Adds the necessary script for Google Tag Manager.

Requires a GTM ID.

Example usage in a Liquid template:

```
{% include google-tag-manager.html id=site.google_tag_manager %}
```

Needs to be kept in sync with [Google Tag Manager for Web Tracking - Quick Start Guide](https://developers.google.com/tag-manager/quickstart).

### disqus-comments.html

Adds the necessary script for Disqus comments.

Requires the site shortname and an optional page identifier.

Example usage in a Liquid template:

```
{% if page.comments %}
  {% include disqus-comments.html
      shortname=site.disqus_shortname
      identifier=site.disqus_identifier | append:page.url | replace:"index.html", ""
  %}
{% endif %}
```

Needs to be kept in sync with [Disqus Setup Instructions for Universal Code](https://disqus.com/admin/universalcode/).

### head.html

Adds a container for various head partials. All of the partials beginning `head-*` are included.

### head-canonical.html

Add a canonical URL.

Requires the URL of the page, the base URL for the page, the URL for the site, and the title of the page.

Example usage in a Liquid template:

```
  {% include head-canonical.html
      url=page.url
      baseurl=site.baseurl
      siteurl=site.url
      title=site.title
  %}
```

### head-description.html

Add a description of the page, based on either the page content or a description of the whole site.

### head-title.html

Add a title for the page, based on either the page itself or the title of the whole site.

### head-charset-utf-8.html

Adds the UTF-8 charset meta tag.

### head-fonts.html

This can be overridden in order to provide font information.

### head-styles.html

This can be overridden in order to provide style information.

### head-ie-legacy-document-mode.html

Adds settings for Internet Explorer Legacy Document mode.

### head-viewport.html

Adds the viewport settings.

### head-homescreen-android.html

Add tags for setting a homescreen link on Android.

### head-homescreen-ios.html

Add tags for setting a homescreen link on iOS.

### head-homescreen-win8.html

Add tags for setting the icon on Windows 8.
