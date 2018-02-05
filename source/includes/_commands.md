# Commands

A command here refers to a printing order issued by a customer. A command binds a `customer` and a `printer`. The front-end constantly retrieves commands to update the printer's dashboard and notifies a customer whenever a command state changes.


## Save a command
When saving a command, you pass by this url. Note that by default, the state of the command is `pending`.
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
		"messenger_id='58918EJS'
    &printer_id='toto54'
    &file_url='https://scontent-cdg2-1.xx.fbcdn.net/v/t1.0-9/26994109_188757791718329_1373693944142395534_n.png?oh=77317a94f574bfc34a0db6ef49908deb&oe=5B117BCD'
    &pages_to_print='7-18,12-32'
    &color=1
    &binding=1
    &paper_format=1"
	-X POST
	"http://3islabs.com/everyprint/api/customer/save"

```

```javascript
$.POST{}

let api = kittn.authorize('meowmeowmeow');
```

`POST data http://3islabs.com/everyprint/api/commands/save`

This saves the commands in the table and triggers notification on the destined printer for treatment.

### Query Parameters

Parameter | Validation | Description
--------- | ---------- | -----------
messenger_id | alphanumeric string | The id of the customer given by `Chatfuel`
printer_id | alphanumeric string : 50 | The printer's id chosen by the customer to treat his/her command
file_url | alphanumeric string : 150 | The file url (hosted on facebook) a .docx , .odt, .pdf given by the customer to treat
pages_to_print | varchar : 10 | The pages to print : All means all the pages, "2-5, 7-18" means the second to the fith page and the seventh to the eighteenth page
color | binary : 0,1 | 0 means gray printing and 1 means color printing
binding | int : 0, 1, 2 , 3 | 0 means no binding, 1 means rayure, 2 means cerdeau
paper_format | int : 0, 1, 2, 3 | 0 means A3, 1 means A4, 2 means A5
amount | float | Financial value of command

### Return Code

> The above command should return :

```json
{
  "return_code" : "111"
}
```

Code | Meaning
-----| -------
111 | Command saved successfully
222 | Parameters validation failed
333 | Error with the backend. Just wait and retry


<aside class="warning">
Not yet implemented !!!!!
</aside>


## Set status command
A command has four states : pending, abort, complete, retrieved. This endpoint changes the state of a command.

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
		"command_id='lml21'&status=0"
	-X POST
	"http://3islabs.com/everyprint/api/command/status/set"

```

```javascript
$.POST{}

let api = kittn.authorize('meowmeowmeow');
```

`POST data http://3islabs.com/everyprint/api/command/status/set`

### Query Parameters

Parameter | Validation | Description
--------- | ---------- | -----------
command_id | alphanumeric string | The id of the command
status | int : 0, 1, 2, 3 | The id of the status we wish the command to have, 0 for pending, 1 for abort, 2 for complete and 3 for retrieved.

<aside class="notice">
  Each time a status changes to complete, we use to `message API` to notify the customer who issued the command.
</aside>

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

## Get a command status
Retrieve the status of a command.

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
		"command_id='lml21'"
	-X GET
	"http://3islabs.com/everyprint/api/command/status/get"

```

```javascript
$.POST{}

let api = kittn.authorize('meowmeowmeow');
```

`GET data http://3islabs.com/everyprint/api/command/status/get`

### Query Parameters

Parameter | Validation | Description
--------- | ---------- | -----------
command_id | alphanumeric string | The id of the command


### Return Code

> The above command should return :

```json
{
  "status" : "1",
  "return_code" : "111"
}
```

<aside class="warning">
Not yet implemented !!!!!
</aside>
