# App Search Reference UI

The Reference UI is a configurable, generic UI meant to work with
any [App Search](https://www.elastic.co/cloud/app-search-service) Engine. It
can serve as a simple demo, a functional test for your Engine data,
and also a code reference to use when building out your own App Search
UI.

The project can be configured via a JSON [config file](src/config/engine.json),
which allows you to easily control things like:

- What Engine this UI runs against
- What fields are displayed
- What filters are used

A complete list of configuration options can be found [below](#config).

## Setup

### If you just downloaded this via the Dashboard

You'll need to install [npm](https://www.npmjs.com/). Once you have "npm"
installed, you should be able to use the `npm` command from within your
terminal.

Run the following commands to start this application:

```bash
# Run the `cd` command to change the current directory to the
# location of your downloaded Reference UI. Replace the path
# below with the actual path of your project.
cd ~/Downloads/app-search-reference-ui

# Run this to set everything up
npm install

# Run this to start your application and open it up in a new browser window
npm start
```

#### Updating configuration

If you would like to make configuration changes, there is no need to regenerate
this app from your App Search Dashboard! You can simply open up the
[engine.json](src/config/engine.json) file, update the [options](#config),
and restart this app.

### If you're checking this project out directly from github

Follow the previous steps, but you'll also need to configure
[engine.json](src/config/engine.json).

To do so, make a copy of [engine.json.example](src/config/engine.json.example),
rename it to `engine.json` and configure with your Engine's specific details.

```bash
cp src/config/engine.json.example src/config/engine.json
```

## Configuration options <a id="config"></a>

The following is a complete list of options available for configuraiton in [engine.json](src/config/engine.json).

- engineName - (String) Found in your [App Search Dashboard](http://app.swiftype.com/as)
- hostIdentifier - (String) Found in your [App Search Dashboard](http://app.swiftype.com/as)
- searchKey - (String) Found in your [App Search Dashboard](http://app.swiftype.com/as)
- fields - (Array[String]) A list of fields that will be searched, and also displayed in results
- titleField - (String)(Optional) The field to display as the title in results
- urlField - (String)(Optional) A field with a url to use as a link in results
- urlFieldTemplate - (String)(Optional) Instead of urlField, you can provide a URL "template" here, which lets you build a URL from other fields. ex: "http://www.example.com/{{id}}"
- sortFields - (Array[String]) A list of fields that will be used for sort options
- facets - (Array[String]) A list of fields that will be available as "facet" filters

## External configuration

If you are embedding this app inside of another page, and you'd like to
source the configuration from outside of the `engine.json` file,
you can simply write the configuration directly to `window.appConfig`.
