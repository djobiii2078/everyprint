# Available file
An available file refers to files that could be useful for the customers. When creating an available file, customers are notified and they can manifest their wish to keep a copy for them.
## Save an available file

An available file binds a printer. When creating the available file, we need the printer's id and we launch a notification to all customers.

### HTTP Request
> To test  :

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl
	-d
		"printer_id='EEX'&name='FICHE TD MECANIQUE 3 NIVEAU 1'&file_url='xxxxxx.com/direct.pdf'"
	-X POST
	"http://3islabs.com/everyprint/api/avail_file/save"

```

```javascript
$.POST{}

let api = kittn.authorize('meowmeowmeow');
```

`POST data http://3islabs.com/everyprint/api/avail_file/save`

### Query Parameters

Parameter | Validation | Description
--------- | ---------- | -----------
printer_id | alphanumeric string | The id of the printer creating the file
name | alphanumeric string | The name of the file : The name should contain details about the document
file_url | alphanumeric string | The file url of the document: hosted on GCP or EC2


### Return Code

> The above command should return :

```json
{
  "avail_file_id" : "EYD6",
  "return_code" : "111"
}
```

<aside class="warning">
Not yet implemented !!!!!
</aside>


## Increase reservation / Reset reservation
This endpoint should be used to increment the number of reservations. We notify the printer for each multiple of 5 reservations i.e 5, 10  15, 20, etc ..... This endpoint should also be used for reseting the number of reservation to zero.

### HTTP Request
> To test  :

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl
	-d
		"avail_id='EYD6'&reset=0"
	-X POST
	"http://3islabs.com/everyprint/api/avail_file/reserve"

```

```javascript
$.POST{}

let api = kittn.authorize('meowmeowmeow');
```

`POST data http://3islabs.com/everyprint/api/avail_file/reserve`

### Query Parameters

Parameter | Validation | Description
--------- | ---------- | -----------
avail_id | alphanumeric string | The id of the available file
reset | binary : 0 or 1 | If 0 increase the number of reservation by 1 else reset the number of reservation to zero



### Return Code

> The above command should return :

```json
{
  "return_code" : "111"
}
```

<aside class="warning">
Not yet implemented !!!!!
</aside>
## Get number of reservations
This endpoint should be used to retrieve the number of reservation for a given available file.

### HTTP Request
> To test  :

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl
	-d
		"avail_id='EDY6'"
	-X GET
	"http://3islabs.com/everyprint/api/avail_file/reserve/number"

```

```javascript
$.POST{}

let api = kittn.authorize('meowmeowmeow');
```

`GET data http://3islabs.com/everyprint/api/avail_file/reserve/number`

### Query Parameters

Parameter | Validation | Description
--------- | ---------- | -----------
avail_id | alphanumeric string | The id of the command


### Return Code

> The above command should return :

```json
{
  "reserve" : "7",
  "return_code" : "111"
}
```

<aside class="warning">
Not yet implemented !!!!!
</aside>
