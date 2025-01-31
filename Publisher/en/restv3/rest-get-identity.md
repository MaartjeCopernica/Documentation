# REST API: GET identity

This method can be used if you want to find out the account that is linked to
an API access token. By sending a GET request to the following URL, you can
fetch the account information:

`https://api.copernica.com/v3/identity?access_token=xxxx`

This method can be useful if you have a lot of different access tokens to 
access many different accounts (this can happen if you built a 
[OAuth integration](./rest-oauth.md)). This method can then be used to find 
out to which account an access token belongs. If you use the REST API only
to access your own account, there is not so much value in this method, because
you already know the account to which you are linked.

## The returned data

This method returns a JSON object containing the following fields:

* **ID**: Unique numeric account identifier
* **name**: Account name
* **description**: Description of the account
* **company**: The name of the company that pays for the account

### JSON example

The output might look something like this:

```json
{  
   "id":"34",
   "name":"Development",
   "description":"This is an account to test with",
   "company":"Copernica BV"
}
```

## PHP example

The following PHP script calls this API method:

```php
// dependencies
require_once('copernica_rest_api.php');
    
// change this into your access token
$api = new CopernicaRestAPI("your-access-token", 3);

// do the call, and print result
print_r($api->get("identity"));
```

The example above requires the [CopernicaRestApi class](rest-php).

## More information

* [Overview of all API calls](./rest-api.md)
* [How to create OAuth2 integrations](./rest-oauth.md)
