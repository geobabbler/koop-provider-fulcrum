[![Build Status](https://travis-ci.org/koopjs/koop-provider-geojson.svg?branch=master)](https://travis-ci.org/koopjs/koop-provider-geojson) [![Greenkeeper badge](https://badges.greenkeeper.io/koopjs/koop-provider-geojson.svg)](https://greenkeeper.io/)


# Koop Fulcrum Data Share Provider

This is a geojson that demonstrates how to build a Koop Provider. Full documentation is provided [here](https://koopjs.github.io/docs/specs/provider/).

`/fulcrum/{share_id}/FeatureServer/0/query`

Example:
With the following Fulcrum data share URL: https://web.fulcrumapp.com/shares/0f9c51f389d22079.geojson

The 'share_id' value will be 0f9c51f389d22079

The resulting Koop URL will be: /fulcrum/0f9c51f389d22079/FeatureServer/0/query

## Files

| File | | Description |
| --- | --- | --- |
| `index.js` | Mandatory | Configures provider for usage by Koop |
| `model.js` | Mandatory | Translates data share to feature service |
| `routes.js` | Optional | Specifies additional routes to be handled by this provider |
| `controller.js` | Optional | Handles additional routes specified in `routes.js` |
| `server.js` | Optional | Reference implementation for the provider |
| `test/model-test.js` | Optional | tests the `getData` function on the model |
| `test/fixtures/input.json` | Optional | a geojson of the raw input from the 3rd party API |
| `config/default.json` | Optional | used for advanced configuration, usually API keys. |

## Test it out
Run server:
- `npm install`
- `DEPLOY=dev node server.js`

Example API Query:
- `curl localhost:8080/fulcrum/FeatureServer/0/query?returnCountOnly=true`

Tests:
- `npm test`

## With Docker

- `docker build -t koop-provider-geojson .`
- `docker run -it -p 8080:8080 koop-provider-geojson`

## Publish to npm
- run `npm init` and update the fields
  - Choose a name like `koop-provider-foo`
- run `npm publish`
