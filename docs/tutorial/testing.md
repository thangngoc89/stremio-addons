### Testing Environment

Add-ons can be tested in two ways.

**Testing with [stremio-addons-client](https://github.com/Ivshti/stremio-addons-client)**

- Install & Run [stremio-addons-client](https://github.com/Ivshti/stremio-addons-client)
- Run your add-on with `npm start`
- Go to the `stremio-addons-client` url
- Open the "Add-ons" tab
- Add your add-on url (ie: `http://localhost:9005`, remember to use your add-on's port) to the "Add new add-on" form

**Testing with [Stremio](http://www.strem.io/)**

- On Windows, run Stremio with:

```
stremio . --services=http://localhost:9005/stremio/v1/stremioget
```

- On OSX / Linux, open a terminal in your add-on's directory, and do:

```
open stremio://localhost:7000/stremio/v1 & # Load this add-on in Stremio
PORT=7000 node index # Start the add-on server
```
