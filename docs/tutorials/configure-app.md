# Configure

The most important file of configuration is `data/hoverboard.config.json`
which looks like:

```
  "pages": {..},
  "navigation": [..],
  "url": "..",
  "mailchimp": {..},
  "partnershipProposition": "..",
  "languages": [..],
  "footerBlocks": [..],
  "contactBlock": {..},
  "tickets": {..},
  "teamPageTitle": "..",
  "teamPageText": "..",
  "statistics": [..],
  "hashtag": "..",
  "social": [..],
  "tweetsSource": "..",
  "gallery": {..},
  "location": {..},
  "videosSessionsUrl": "..",
  "callToAction": {..}
```

**Note**, the project supports localization using [AppLocalizeBehavior][
AppLocalizeBehavior], that's why some of the config values are keys in
[localization resources][localization resources].

### SEO
The project doesn't use any generators, so there is a need to edit manually
meta data in `index.html`
```
<head>
  <meta name="description"
        content="The largest free community created tech conference in the UK, carefully crafted for you by the Google Developer Group (GDG) community and University College London (UCL)! GDG London is a group of developers passionate about Google technologies with a strong focus on knowledge exchange and networking. Learn about Android, Web, Cloud, Machine Learning and more from world experts.">
  <meta name="keywords"
        content="event, gdg, gde, devfest, google, programming, android, chrome, polymer, developers, web, cloud, androiddev">
  <meta name="author" content="GDG London">

  <title>GDG DevFest London 2017</title>
  ...
```

### Google Analytics
Replace GA tracking code in `index.html`
```
trackingId: window.ENV === 'prod' ? 'UA-43643469-8' : 'UA-43643469-9'
```

It's possible to have analytics for development and production. Select
your environment on line:
```
window.ENV = 'dev';
```

### Pages config

```
"pages": {
  "home": {
    "headerSettings": {
      "backgroundColor": "#FFC107",
      "backgroundImage": "/images/backgrounds/home.jpg",
      "fontColor": "#fff",
      "tabBarColor": "#fff",
      // data only applicable for the home page
      "video": {
        "title": "GDG DevFest London 2016",
        "youtubeId": "DfMnJAzOFng",
        "text": "See how it was in 2015"
      },
      // hides logo from the toolbar
      "hideLogo": true,
      // Is more like hack :)
      "minHeight": "360px"
    }
  },
  "blog": {
    "headerSettings": {
      "backgroundColor": "#03a9f4",
      "fontColor": "#fff",
      "tabBarColor": "#fff"
    }
  },
  ...
 }
```

If you don't need some pages, don't forget to remove them (or comment out)
in `hoverboard-app.html`

```
<neon-animated-pages attr-for-selected="name">

    <home-page name="home"></home-page>
    <blog-page name="blog"></blog-page>
    ...
<
```

And in navigation


### Navigation

```
"navigation": [
  {
    "route": "home",
    "permalink": "/"
  },
  {
    "route": "blog",
    "permalink": "/blog/"
  },
  ...
```

This configs reflects in `toolbar-block.html` and `drawer-block.html`


# Next steps

Now your Hoverboard is up configured, learn how to [style app][style app] and [deploy][deploy].

[AppLocalizeBehavior]: https://elements.polymer-project.org/elements/app-localize-behavior
[localization resources]: /data/en/resources.json
[style app]: styling.md
[deploy]: deploy.md
