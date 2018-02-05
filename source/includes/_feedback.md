# Feedback

This is the section concerning how we manage feedbacks.

## Save a feedback

Takes a review score between 1 and 5, the comment left by the customer and the customer messenger's id and stores in the table `Feedback`. This table is
analysed later for more insights on customer's appreciation of the application.

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
	"{"review_score=5&review_comment='GOOD'&customer_id=43219XDF"
	-X POST
	 "http://3islabs.com/everyprint/api/feedback/save"

```

```javascript
$.POST{}

let api = kittn.authorize('meowmeowmeow');
```

`POST http://3islabs.com/everyprint/api/feedback/save`

### Query Parameters

Parameter | Validation | Description
--------- | ------- | -----------
review_score | Between 1 and 5 | The rating given by the customer
review_comment | Trim with no special char | Additional comment done by the customer
customer_id | Series of char and int | The customer messenger's id

### Return Code

> The above command should return :

```json
{
  "return_code" : "111"
}
```

Code | Meaning
-----| -------
111 | Feedback saved successfully
222 | Parameters validation failed
333 | Error with the backend. Just wait and retry


<aside class="warning">
Not yet implemented !!!!!
</aside>

## Average feedback score

In order to get the overall feeback rating, the customers issued us. In order to achieve that, we make an `average operation` on the overall ratings we obtained and process it back to the endpoint who issued the command. We also return the `date and time` in order to indicate the period where we achieved the retrieved average score.

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
	"http://3islabs.com/everyprint/api/feedback/average"

```

```javascript
$.POST{}

let api = kittn.authorize('meowmeowmeow');
```



`GET http://3islabs.com/everyprint/api/feedback/average`

### Return Code

> The above command should return the average score in a json and a code to process backend return message :

```json
{
  "average_score" : "4.44",
  "datetime" : "21/04/2018 18:00:00",
  "return_code" : "111"
}
```

Code | Meaning
-----| -------
111 | Information retrieval successful
222 | Bad endpoint or untrested request
333 | The backend didn't respond. Try later

<aside class="warning">
Not yet implemented !!!!!
</aside>
