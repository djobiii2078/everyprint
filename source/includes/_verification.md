# Verification endpoints

This section describes all the endpoints designed to interact with the bot for verification tasks.

## Verify if a file is a pdf
In order to verify is a file input given by a customer is a pdf file, you pass
by this endpoint. You pass the name of the file given to you by chatfuel to this url with the fileName parameter. If the file given is a ".pdf", it responds yes otherwise no

### HTTP Request
> To test  :


```python
import urllib.parse
import urllib.request

url = 'https://qav5het0s2.execute-api.us-east-1.amazonaws.com/dev/test/ispdf'
values = {'fileName' : 'toto.pdf'}
data = urllib.parse.urlencode(values)
data = data.encode('ascii')
req = urllib.request.Request(url, data)
with urllib.request.urlopen(req) as response:
   print response.read()

```

```shell
# With shell, you can just pass the correct header with each request
curl
	-G
    "https://qav5het0s2.execute-api.us-east-1.amazonaws.com/dev/test/ispdf?fileName=toto.pdf"

```

```javascript
$.get("https://qav5het0s2.execute-api.us-east-1.amazonaws.com/dev/test/ispdf?fileName=toto.pdf",
function(result){
  console.log(result)
})

```
GET  `https://qav5het0s2.execute-api.us-east-1.amazonaws.com/dev/test/ispdf?fileName=toto.pdf`



### Query Parameters

Parameter | Validation | Description
--------- | ---------- | -----------
fileName | alphanumeric string | The name of the file to verify

> The above command should return :

```json
{
  "yes"
}
```
<aside class="success">
  Operational
</aside>
