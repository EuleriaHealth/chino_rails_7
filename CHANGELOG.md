# Changelog

## [next release date] - next release



## [2020-02-01] - v 3.0.0
- Migrated code from GitHub
- Changed behaviour of `update_user_partial` from 

        def update_user_partial(user_id, attributes)

    to
    
        def update_user_partial(user_id, attributes=nil, username=nil, password=nil)

    which allows to only specify username, password or a set of attributes.

    Now it is possible to update username and password of the users too.

    On top of that, the `attributes` have been correctly wrapped in order to match the 
    request described in the 
    [Chino.io API docs](https://console.test.chino.io/docs/v1#users-user-object-patch)
  
- Raise a `ChinoAuthException` when receiving a `400` response that contains:
  `"message": "Invalid credentials given."`

- fix path in BLOB test so it can be invoked both from folder `test/` and from 
  the repository base folder
