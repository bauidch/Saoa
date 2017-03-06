# Grapp a API 

## QML

## Python

``` python
import pyotherside
import urllib
from urllib.request import urlopen
import urllib.request
import json

def getData():
    req = urllib.request.Request(url='http://yourAPIurl.com', method='GET')
    res = urllib.request.urlopen(req)
    res_body = res.read()
    j = json.loads(res_body.decode("utf-8"))

    results = j['result']
    pyotherside.send('result',results)
```
