# Customers

A customer here is someone who will interact with the chatbot in order to order printing commands. He will then pay passing his command and will be notified if his command is done. He also has the ability to chat with the printer he chose in order to improve the quality of his document. His balance is set by default to 0 in the table `Balance`.



## Save a customer
During the first interaction with the bot, we use by this endpoint in order to save the customer in the database `customer`.

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
		"messenger_id=58918EJS&last_name='lil kim'&gender='Male'"
	-X POST
	"http://3islabs.com/everyprint/api/customer/save"

```

```javascript
$.POST{}

let api = kittn.authorize('meowmeowmeow');
```

`POST data http://3islabs.com/everyprint/api/customer/save`

This has the effect to save the customer in the database mysql in the table Customer.

### Query Parameters

Parameter | Validation | Description
--------- | ---------- | -----------
messenger_id | alphanumeric string | The id of the customer given by `Chatfuel`
last_name | String maxlength : 50 | The last name used by the customer on fb given by `Chatfuel`
gender | Male or Female -> 0 or 1 | The gender of the customer given by `Chatfuel`

### Return Code

> The above command should return :

```json
{
  "return_code" : "111"
}
```

Code | Meaning
-----| -------
111 | Customer saved successfully
222 | Parameters validation failed
333 | Error with the backend. Just wait and retry


<aside class="warning">
Not yet implemented !!!!!
</aside>

## Get customer's Balance
This enable us to retrieve the balance for a given customer. We take in the `messenger_id` of the customer and retrieve its balance from the table `Balance`

## HTTP Request
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
		"messenger_id=58918EJS"
	-X GET
	"http://3islabs.com/everyprint/api/customer/balance"

```

```javascript
$.POST{}

let api = kittn.authorize('meowmeowmeow');
```

`GET data http://3islabs.com/everyprint/api/customer/balance`

### Query Parameters

Parameter | Validation | Description
--------- | ---------- | -----------
messenger_id | alphanumeric string | The id of the customer given by `Chatfuel`

### Return Code

> The above command should return :

```json
{
	"balance" : "5000",
  "return_code" : "111"
}
```

The balance is in the currency XOF.

<aside class="warning">
Not yet implemented !!!!!
</aside>
