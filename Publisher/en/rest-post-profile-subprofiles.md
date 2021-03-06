# REST API: POST profile subprofiles

To add subprofiles to a profile an HTTP post request can be sent to the following URL:

`https://api.copernica.com/v1/profile/$id/subprofiles/$collectionID?access_token=xxxx`

The $id should be replaced with the ID of the profile you want to add a
subprofile to. The $collectionID should be replaced with the ID of the
collection in which the subprofile should be stored. The new subprofile
of the profile can be placed in the body of the message.

## Body data

The subprofile can have the following properties:

- **secret**: Secret code associated with subprofiles
- **profile**: ID of the profile the subprofile is associated with
- **fields**: Fields of the subprofile
- **collection**: ID of the collection the subprofile belongs to
- **created**: Timestamp of creation in YYYY-MM-DD hh:mm:ss format
- **modified**: Timestamp of last edit in YYYY-MM-DD hh:mm:ss format

## PHP example

The following PHP script demonstrates how the API method can be called.

```php
// dependencies
require_once('copernica_rest_api.php');
    
// change this into your access token
$api = new CopernicaRestApi("your-access-token");

// data to pass to the call, the new interests
$data = array(
    'profile' => '1234'
);
    
// do the call
$api->post("profile/1234/subprofiles/321", $data);
```

The example above requires the [CopernicaRestApi class](rest-php).
    
## More information

* [Overview of all REST API calls](rest-api)
* [PUT profile interests](rest-put-profile-interests)
* [POST database profile](rest-post-database-profiles)
* [GET subprofile](rest-get-subprofile)
* [POST profile subprofile](rest-post-profile-subprofiles)
