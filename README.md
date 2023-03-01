New Relic script tag for the HTML Webpack Plugin
========================================

Add new relic script tag using [html-webpack-plugin](https://github.com/ampedandwired/html-webpack-plugin).

Installation
------------
You must be running webpack on node 8.x or higher

Install the plugin with yarn:
```shell
$ yarn -D html-webpack-new-relic-plugin
```

Or npm:
```shell
$ npm install --save-dev html-webpack-new-relic-plugin
```

Basic Usage
-----------
Require the plugin in your webpack config:

```javascript
var HtmlWebpackNewRelicPlugin = require('html-webpack-new-relic-plugin');
```

Add the plugin to your webpack config:

```javascript
plugins: [
  new HtmlWebpackPlugin(),
  new HtmlWebpackNewRelicPlugin({
    accountID: '121212',
    agentID: '343434',
    trustKey: '565656',
    licenseKey: '123456',
    applicationID: '654321'
  })
]  
```

Updating the New Relic JS Snippet
---------------------------------
As new browser agents become available, it is best to update this code to use the most recent snippets.

- [New Relic Browser Agent Release Notes](https://docs.newrelic.com/docs/release-notes/new-relic-browser-release-notes/browser-agent-release-notes/)
- [Update your copy/paste installation](https://docs.newrelic.com/docs/browser/new-relic-browser/installation/update-browser-agent/#upgrading-copy-paste)
- [Retrieving snippet from NR UI](https://docs.newrelic.com/docs/browser/new-relic-browser/installation/update-browser-agent/#snippet)


This plugin adds the script for New Relic "Pro + SPA" instrumentation. If you have "Pro" configured under Browser =>
"Application settings", the SPA data will be collected, but dropped by New Relic during ingestion. SPA data will be
ready to be ingested when and if you switch to "Pro + SPA" instrumentation. The plugin option values can be found at the
bottom of the JavaScript snippet under these settings.

This plugin will add the HUGE New Relic script tag to your html file without making your template file ugly. It suits
best using with [html-webpack-template](https://github.com/jaketrent/html-webpack-template) because you actually don't
need a template file.
