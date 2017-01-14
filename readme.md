GreaetSchools API
====================

GreatSchools has its own API. It is not compatible with the [Basecamp Classic API](https://github.com/basecamp/basecamp-classic-api) or the [Basecamp 3 API](https://github.com/basecamp/bc3-api). The core ingredients are still the same, though. This is a REST-style API that uses JSON for serialization and OAuth 2 for authentication.


Making a request
----------------

All URLs start with `https://basecamp.com/999999999/api/v1/`. **SSL only**. The path is prefixed with the account id and the API version. If we change the API in backward-incompatible ways, we'll bump the version marker and maintain stable support for the old URLs.

To make a request for all the projects on your account, you'd append the projects index path to the base url to form something like https://basecamp.com/999999999/api/v1/projects.json. In curl, that looks like:

```shell
curl -u user:pass -H 'User-Agent: MyApp (yourname@example.com)' https://basecamp.com/999999999/api/v1/projects.json
```

To create something, it's the same deal except you also have to include the `Content-Type` header and the JSON data:

```shell
curl -u username:password \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: MyApp (yourname@example.com)' \
  -d '{ "name": "My new project!" }' \
  https://basecamp.com/999999999/api/v1/projects.json