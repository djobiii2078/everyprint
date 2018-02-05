# Broadcast

This section deals with notifications sent to a set of customers, to all customers or to the given customer.

## Broadcast a message to all customers
This endpoint should be used to pass a message to every customer. Should be used to broadcast ads or important notifications for our app.

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
		"message='This is a prank'"
	-X POST
	"http://3islabs.com/everyprint/api/broadcast"

```

```javascript
$.POST{}

let api = kittn.authorize('meowmeowmeow');
```

`POST data http://3islabs.com/everyprint/api/broadcast`

### Query Parameters

Parameter | Validation | Description
--------- | ---------- | -----------
message | alphanumeric string | The message to be sent


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


## Send a message to a customer
This endpoint should be used to send a message to a particular customer. This could be used for a chat between the printer and the customer.

<aside class="notice">
During this conversational pattern, the customer subscribe to a sequence in chatfuel where each of his messages are sent to an endpoint API which notifies the printer of the customer's response to the chat.
</aside>

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
		"customer_id='EDY6dsLD'&message='No footer in your document, are you aware ?'"
	-X GET
	"http://3islabs.com/everyprint/api/broadcast/customer"

```

```javascript
$.POST{}

let api = kittn.authorize('meowmeowmeow');
```

`GET data http://3islabs.com/everyprint/api/broadcast/customer`

### Query Parameters

Parameter | Validation | Description
--------- | ---------- | -----------
customer_id| alphanumeric string | The messenger_id of the customer
message | alphanumeric string | The message to be sent to the customer


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


## Broadcast a message to a set of customers
This endpoint should be used to send a message to a group of customers. Could be used for A/B testing or to send targeted ads depending on customers caracteristics.

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
		"group='Yaounde Students'&message='This is a prank'"
	-X POST
	"http://3islabs.com/everyprint/api/broadcast/group"

```

```javascript
$.POST{}

let api = kittn.authorize('meowmeowmeow');
```

`POST data http://3islabs.com/everyprint/api/broadcast/group`

### Query Parameters

Parameter | Validation | Description
--------- | ---------- | -----------
group | alphanumeric string | The group of users arranged on chatfuel
message | alphanumeric string | The message to be sent to the group


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
