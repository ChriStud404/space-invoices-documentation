# Payments

Payments are stored for each invoice. Each invoice can have multiple payments that can also sum up to more that the invoice's total value. Payments are in the Currency of the document.

## Create New Payment

```shell
curl "https://api.spaceinvoices.com/v1/documents/5a3683ea12d5a67dd0ef2f4d/payments" \
  -H "Authorization: LAUNCH_CODE" \
  -d type="bank" \
  -d date="2018-01-01" \
  -d amount=1000
```

```javascript
spaceInvoices.payments.create(documentId, {
  type: "bank",
  date: "2018-01-01",
  amount: 1000
})
.then(function(payment) {
  console.log(payment);
})
```

```php
<?php
  Spaceinvoices\Payments::create("DOCUMENT_ID", array(
    "type" => "bank",
    "date" => "2018-01-01",
    "amount" => 1000
  ));
?>
```

> Returns:

```json
{
  "id": "5a3683ea12d5a67dd0ef2f4c",
  "documentId": "5a3683ea12d5a67dd0ef2f4d",
  "organizationId": "5a3683ea12d5a67dd0ef2f4e",
  "type": "bank",
  "date": "2018-01-01",
  "amount": 1000
}
```

This endpoint creates a new Payment.

### HTTP Request

`POST https://api.spaceinvoices.com/v1/documents/:id/payments`

#### Query parameters

|      |     |
| ---: | --- |
| id **required** | ID of Document for which we are creting the Payment. |

#### Arguments

|      |     |
| ---: | --- |
| type **required** | Type of payment, one of `bank` / `online` / `paypal` / `cash` / `crypto` / `other`. |
| date **required** | Date of payment. |
| amount **required** | Amount of Payment. |
| description | Description of Payment. |

### HTTP Response

#### Arguments

|      |     |
| ---: | --- |
| id | Unique ID of model instance. |


## Update Payment

```shell
curl -X PUT "https://api.spaceinvoices.com/v1/payments/5a3683ea12d5a67dd0ef2f4c" \
  -H "Authorization: LAUNCH_CODE" \
  -d type="bank" \
  -d documentId="5a3683ea12d5a67dd0ef2f4d" \
  -d date="2018-01-01" \
  -d amount=1000
```

```javascript
spaceInvoices.payments.edit(paymentId, {
  type: "bank",
  documentId: documentId,
  date: "2018-01-01",
  amount: 1000
})
.then(function(payment) {
  console.log(payment);
})
```


```php
<?php
  Spaceinvoices\Payments::edit("PAYMENT_ID", array(
    "type" => "bank",
    "documentId" => "DOCUMENT_ID"
    "date" => "2018-01-01",
    "amount" => 1000,
  ));
?>
```

> Returns:

```json
{
  "id": "5a3683ea12d5a67dd0ef2f4c",
  "documentId": "5a3683ea12d5a67dd0ef2f4d",
  "organizationId": "5a3683ea12d5a67dd0ef2f4e",
  "type": "bank",
  "date": "2018-01-01",
  "amount": 1000
}
```

This endpoint updates a Payment by ID.

### HTTP Request

`PUT https://api.spaceinvoices.com/v1/payments/:id`

#### Query parameters

|      |     |
| ---: | --- |

#### Arguments

|      |     |
| ---: | --- |
| type **required** | Type of payment, one of `bank` / `online` / `paypal` / `cash` / `crypto` / `other`. |
| documentId **required** |	ID of Document for which we are updating the Payment. |
| date **required** | Date of payment. |
| amount **required** | Amount of Payment. |
| description | Description of Payment. |

### HTTP Response

#### Arguments

|      |     |
| ---: | --- |


## Delete Payment

```shell
curl -X DELETE "https://api.spaceinvoices.com/v1/payments/5a3683ea12d5a67dd0ef2f4c" \
  -H "Authorization: LAUNCH_CODE"
```

```javascript
spaceInvoices.payments.delete(paymentId)
.then(function(count) {
  console.log(count);
})
```

```php
<?php
  Spaceinvoices\Payments::delete("PAYMENT_ID");
?>
```

> Returns:

```json
{
  "count": 1
}
```

This endpoint deletes a Payment by ID.

### HTTP Request

`DELETE https://api.spaceinvoices.com/v1/payments/:id`

#### Query parameters

|      |     |
| ---: | --- |
| id **required** | ID of Payment to delete. |

### HTTP Response

#### Arguments

|      |     |
| ---: | --- |
| count | Number of successfuly deleted payments. |


## List Payments

```shell
curl "https://api.spaceinvoices.com/v1/organizations/5a3683ea12d5a67dd0ef2f4d/payments" \
  -H "Authorization: LAUNCH_CODE"
```

```javascript
spaceInvoices.payments.list(organizationId)
.then(function(payments) {
  console.log(payments);
})
```

```php
<?php
  Spaceinvoices\Payments::find("ORGANIZATION_ID");
?>
```

> Returns:

```json
[
  {
    "id": "5a3683ea12d5a67dd0ef2f4c",
    "documentId": "5a3683ea12d5a67dd0ef2f4d",
    "organizationId": "5a3683ea12d5a67dd0ef2f4e",
    "type": "bank",
    "date": "2018-01-01",
    "amount": 1000
  }
]
```

This endpoint lists Organization's Payments.

### HTTP Request

`GET https://api.spaceinvoices.com/v1/organizations/:id/payments`

#### Query parameters

|      |     |
| ---: | --- |
| id **required** | ID of Organization. |
| filter | Object containing query filters. See [Filters](#filters) section for more details. |

### HTTP Response

#### Arguments

|      |     |
| ---: | --- |
| type | Type of payment. |
| date | Date of payment. |
| amount | Amount of Payment. |
| description | Description of Payment. |


## List a Document's Payments

```shell
curl "https://api.spaceinvoices.com/v1/documents/5a3683ea12d5a67dd0ef2f4d/payments" \
  -H "Authorization: LAUNCH_CODE"
```

```javascript
```

```php
```

> Returns:

```json
[
  {
    "id": "5a3683ea12d5a67dd0ef2f4c",
    "documentId": "5a3683ea12d5a67dd0ef2f4d",
    "organizationId": "5a3683ea12d5a67dd0ef2f4e",
    "type": "bank",
    "date": "2018-01-01",
    "amount": 1000
  }
]
```

This endpoint lists Document's Payments.

### HTTP Request

`GET https://api.spaceinvoices.com/v1/documents/:id/payments`

#### Query parameters

|      |     |
| ---: | --- |
| id **required** | ID of Document. |
| filter | Object containing query filters. See [Filters](#filters) section for more details. |

### HTTP Response

#### Arguments

|      |     |
| ---: | --- |
| type | Type of payment. |
| date | Date of payment. |
| amount | Amount of Payment. |
| description | Description of Payment. |