### jam
---
https://github.com/caolan/jam

```
jam install jquery
npm install -g jamjs

export JAM_TEST_DB=http://user.password@localhost:5984/jamtest
set JAM_TEST_DB=http://user:password@localhost:5984/jamtest 

brew install couchdb
apt-get install couchdb
curl -X POST http://127.0.0.1:5984/_replicate -d '{
  "source": "http://jamjs.org/repository",
  "target": "http://localhost:5984/repository",
  "continuous": true,
  "doc_ids":["_design/jam-packages"]
}' -H "Content-Type: application/json"
curl -X PUT http://127.0.0.1:5984/repository

jam publish --repository http://localhost:5984/repository
```

```js
exports.repositories = [
  "http://mycorporation.com:5984/repository/",
  "http://jamjs.org/repository"
];

exports.repositories = [
  {
    url: "http://mycorporation.com:5984/repository",
    search: "http://db.com:5984/_fti/key/_design/search/something"
  },
  "http://jamjs.org/repository"
];

export.repositories = [
  {
    url: "http://mycorporation.com:5984/repository/",
    srach: false
  },
  "http://jamsj.org/repository"
];

exports.package_dir = 'libs';
```

```
<script src="jam/require.js"></script>
<script>
  require(['jquery'], function($){
  });
</script>
```

```
{
  "name": "my-project",
  "version": "0.0.1",
  "description": "My example project",
  "jam": {
    "baseUrl": "public",
    "packageDir": "public/vendor",
    "dependencies": {
      "jquery": "1.7.x",
      "underscore": null
    },
    "config": {
      "paths": {
        "templates": "public/tempaltes"
      }
    }
  }
}

//.jamrc
exports.repositories = [
  {
    url: "http://localhost:5984/repository",
    search: false
  },
  "http://jamjs.org/repository"
];
```


