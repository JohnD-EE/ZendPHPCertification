# Other

### Compression
* Compression isn't listed as a topic on the ZCE page, but seems to be part of the exam
* Gzip is an algorithm to compress and decompress data
* HTTP supports the use of Gzip
* Gzip is a [GNU project](https://www.gnu.org/software/gzip/) - hence the 'G' in Gzip.
* HTTP compression can be built into servers and clients to improve transfer speeds and bandwidth usage (up to 90% reduced file size).
* Compression is done dynamically, on the fly, so uses more resources to process
* When making a request, a compliant browser sends headers containing info about supported compression methods e.g. `Accept-Encoding: gzip, deflate` -
gzip and deflate are the most common compression methods
* See [Wikipediea: HTTP Compression](https://en.wikipedia.org/wiki/HTTP_compression)
* [Youtube Gzip Compression Explained](http://www.youtube.com/watch?v=Mjab_aZsdxw "Gzip")


```php
//Turn on output buffering
ob_start("ob_gzhandler");//Enables gzip compression. Returns FALSE if browser doesn't support gzip
```

php.ini settings for zlib:
* `zlib.output_compression = on`
* `zlib.output_compression_level = 9//set a level between 0 and 9 (most compression but most CPU usage). Default is -1`

[zlib](https://en.wikipedia.org/wiki/Zlib) is a software library used for data compression