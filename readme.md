GreatSchools API
====================

Feature GreatSchools data on your site.

GreatSchools has profiles of 200,000 public, public charter and private preK-12 schools. With more than one million school ratings and reviews by parents, teachers and students, we provide the most comprehensive information about schools in the United States.

The GreatSchools API allows you to add valuable information to your application, including:
* Schools in a city
* Schools near an address
* Data about specific schools, including school directory information, grade levels, enrollment, test scores, ratings and reviews and more.


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
