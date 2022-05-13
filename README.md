# Chrome Extension

This action publishes your chrome extension to [Chrome Web Store](https://chrome.google.com/webstore/). This action uses Google's [Chrome Web Store API v1.1](https://developer.chrome.com/docs/webstore/api_index/#items).

This action can only publish new version of an existing extension rather than creating and publishing a new one.

## Prepare

Following items are required before publishing your chrome extension:

- A zip file to be uploaded.
- An API client ID and secret.
- A refresh token.

Please refer to this [tutorial](https://developer.chrome.com/docs/webstore/using_webstore_api/) for how to generate API keys and refresh token.

## Usage

Unless otherwise noted with default value, all options are required.

- `extension-id`: the id of your extension; can be referred from the url of your extension page on the Web Store.
- `zip-path`: path to the zip file built in the previous steps.
- `tester-only`: (boolean) `true` indicates publishing to testers only; default `false`.
- `client-id`: your API client ID.
- `client-secret`: your API client secret.
- `refresh-token`: your refresh token.

Example:

```yaml
steps:
  - uses: wdzeng/chrome-extension@v1
    with:
      extension-id: yout-extension-id
      zip-path: your-extension.zip
      tester-only: false
      client-id: ${{ secrets.CHROME_CLIENT_ID }}
      client-secret: ${{ secrets.CHROME_CLIENT_SECRET }}
      refresh-token: ${{ secrets.CHROME_REFRESH_TOKEN }}
```

## References

- [Obtaining OAuth 2.0 access tokens](https://developers.google.com/identity/protocols/oauth2/web-server#httprest_1)
- [Using the Chrome Web Store Publish API](https://developer.chrome.com/docs/webstore/using_webstore_api/)
- [Chrome Web Store API](https://developer.chrome.com/docs/webstore/api_index/)