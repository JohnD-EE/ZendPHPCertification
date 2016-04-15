# EGPCS
The ZCE headings refer only to Get and Post Data.  But it's worth covering all super global arrays known collectively
as EGPCS:
* $_ENV
* $_GET
* $_POST
* $_COOKIE
* $_SERVER

* Super Globals can be accessed from anywhere, scope doesn't matter
* `variables_order` is a php.ini directive used to specify the order that these super globals are loaded during the
execution of a PHP script
* The default php.ini setting is "EGPCS". If set to "CS" instead then COOKIE and SERVER super globals are loaded,
leaving the others empty.

### $_ENV - An Array of Environment data e.g. variables set on the server
ENV variables can be set in the following ways:

1. Directly in PHP: `bool putenv ( string $setting )`
* putenv() temporarily sets the environment variable for the life of this request only
* `$setting` syntax would be like "myVar=value", setting the ENV variable myVar to `value`
2. .htaccess: SetEnv myVar value
3. Apache httpd.conf: SetEnv myVar value

ENV variables can be retrieved by `$_ENV['myVar']` or `get_env('myVar')`

* $_GET - Collects form data by reading values from the _query string_ part of the URL
* Different Browsers and servers put different limits on URL size and hence query string size
* $_POST -



### RESTful principles
As a footnote it's probably worth clarifying how a RESTful architectures use GET and POST operations:
* GET is used for _safe_ and _idempotent_ operations.  An idempotent operation has no additional effect when called
multiple times with the same input parameters
* GET is therefore used for things like retrieving a resource.
* POST is for _unsafe_ or _non-impotent_ operations only and in REST it is for creating only. (REST uses PUT for editing
and DELETE for deleting)
* Should therefore not use GET operation for a request which changes data
* Think of GET as retrieving or viewing only, POST is for creating or editing
