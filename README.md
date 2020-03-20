# Koop Fulcrum Query API Provider

This is a custom provider to simplify the use of the [https://learn.fulcrumapp.com/dev/query/intro]Fulcrum Query API with Koop.

Example usage: `/fulcrum-qapi/{query_id}/FeatureServer/0/query`

The value for the 'query_id' parameter must match an entry in the "queries" property of the 'settings' object defined in `qapi.js`.

In the example provided here, the URL `/fulcrum-qapi/geobooze/FeatureServer/0/query` will look up the query stored in the `geobooze` entry and execute the query `SELECT * FROM GeoBooze LIMIT 1;`.

A Fulcrum API is required and must be entered into the `apiKey` entry in `qapi.js`.

## Files

| File | | Description |
| --- | --- | --- |
| `index.js` | Mandatory | Configures provider for usage by Koop |
| `model.js` | Mandatory | Translates data share to feature service |
| `qapi.js` | Mandatory | Configures Fulcrum query API, set API key here |
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
- `curl localhost:8080/fulcrum-qapi/FeatureServer/0/query?returnCountOnly=true`

Tests:
- `npm test`
