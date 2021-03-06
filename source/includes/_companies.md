# Companies

Companies is a searchable collection of companies and organization we maintain and is available to simplify issuing documents.

It is recommended to use this database for user interfaces as a search while you type feature but to limit searches to specific countries based on user's origin.

We are adding to this database slowly country by country.
The database is updated regularly as frequently as we can query the data for each country.

Current status:
- [x] Slovenia (test API, production in 1 month)

Accepting votes and data sources for other countries.


## List Companies

```shell
curl "https://api.spaceinvoices.com/v1/companies" \
  -H "Authorization: LAUNCH_CODE"
```

```javascript
spaceInvoices.companies.list()
.then(function(companies) {
  console.log(companies);
})
```
```csharp
SpaceCompanyService companyService = new SpaceCompanyService();
List<SpaceCompany> companies = companyService.List();
```

```php
<?php
  Spaceinvoices\Companies::find();
?>
```

> Returns:

```shell
[
  {
    "id": "5a3683ea12d5a67dd0ef2f4c",
    "name": "Space Exploration Technologies corp",
    "address": "Rocket Road",
    "city": "Hawthorne",
    "zip": "CA 90250",
    "country": "USA",
    "taxNumber": "",
    "taxSubject": true,
    "companyNumber": "123456789"
  }
]
```
```javascript
[
  {
    "id": "5a3683ea12d5a67dd0ef2f4c",
    "name": "Space Exploration Technologies corp",
    "address": "Rocket Road",
    "city": "Hawthorne",
    "zip": "CA 90250",
    "country": "USA",
    "taxNumber": "",
    "taxSubject": true,
    "companyNumber": "123456789"
  }
]
```
```csharp
List<SpaceCompany> 

public class SpaceCompany
{
  [JsonProperty("id")]
  public string Id { get; set; }

  [JsonProperty("name")]
  public string Name { get; set; }

  [JsonProperty("address")]
  public string Address { get; set; }

  [JsonProperty("city")]
  public string City { get; set; }

  [JsonProperty("zip")]
  public string Zip { get; set; }

  [JsonProperty("country")]
  public string Country { get; set; }

  [JsonProperty("taxNumber")]
  public string TaxNumber { get; set; }

  [JsonProperty("taxSubject")]
  public bool TaxSubject { get; set; }

  [JsonProperty("companyNumber")]
  public string CompanyNumber { get; set; }
}
```
```php
<?php
  [
    {
      "id": "5a3683ea12d5a67dd0ef2f4c",
      "name": "Space Exploration Technologies corp",
      "address": "Rocket Road",
      "city": "Hawthorne",
      "zip": "CA 90250",
      "country": "USA",
      "taxNumber": "",
      "taxSubject": true,
      "companyNumber": "123456789"
    }
  ]
?>
```

This endpoint lists Companies.

### HTTP Request

`GET https://api.spaceinvoices.com/v1/companies`

#### Query parameters

|      |     |
| ---: | --- |
| filter | Object containing query filters. See [Filters](#filters) section for more details. |

### HTTP Response

#### Arguments

|      |     |
| ---: | --- |
| id | Unique ID of Company model instance. |
| name | Name of Company. |
| address | Address of Company. |
| address2 | Address line two of Company. |
| city | City of Company. |
| zip | ZIP / post code of Company. |
| country | Country of Company. |
| taxNumber | Tax number of Company. |
| taxSubject | Boolean if Company is subject to VAT / GST / sales tax or other tax. |
| companyNumber | Company or other organization registration number. |


## Search Companies

```shell
curl "https://api.spaceinvoices.com/v1/companies/search?term=Space" \
  -H "Authorization: LAUNCH_CODE"
```

```javascript
spaceInvoices.companies.search('space')
.then(function(companies) {
  console.log(companies);
})
```
```csharp
SpaceCompanyService companyService = new SpaceCompanyService();
List<SpaceCompany> companies = companyService.Search("space");
```

```php
<?php
  Spaceinvoices\Companies::search('space');
?>
```

> Returns:

```shell
[
  {
    "id": "5a3683ea12d5a67dd0ef2f4c",
    "name": "Space Exploration Technologies corp",
    "address": "Rocket Road",
    "city": "Hawthorne",
    "zip": "CA 90250",
    "country": "USA",
    "taxNumber": "",
    "taxSubject": true,
    "companyNumber": "123456789"
  }
]
```
```javascript
[
  {
    "id": "5a3683ea12d5a67dd0ef2f4c",
    "name": "Space Exploration Technologies corp",
    "address": "Rocket Road",
    "city": "Hawthorne",
    "zip": "CA 90250",
    "country": "USA",
    "taxNumber": "",
    "taxSubject": true,
    "companyNumber": "123456789"
  }
]
```
```csharp
List<SpaceCompany> 

public class SpaceCompany
{
  [JsonProperty("id")]
  public string Id { get; set; }

  [JsonProperty("name")]
  public string Name { get; set; }

  [JsonProperty("address")]
  public string Address { get; set; }

  [JsonProperty("city")]
  public string City { get; set; }

  [JsonProperty("zip")]
  public string Zip { get; set; }

  [JsonProperty("country")]
  public string Country { get; set; }

  [JsonProperty("taxNumber")]
  public string TaxNumber { get; set; }

  [JsonProperty("taxSubject")]
  public bool TaxSubject { get; set; }

  [JsonProperty("companyNumber")]
  public string CompanyNumber { get; set; }
}
```
```php
<?php
  [
    {
      "id": "5a3683ea12d5a67dd0ef2f4c",
      "name": "Space Exploration Technologies corp",
      "address": "Rocket Road",
      "city": "Hawthorne",
      "zip": "CA 90250",
      "country": "USA",
      "taxNumber": "",
      "taxSubject": true,
      "companyNumber": "123456789"
    }
  ]
?>
```

This endpoint searches for Companies.

### HTTP Request

`GET https://api.spaceinvoices.com/v1/companies/search?term=:term`

#### Query parameters

|      |     |
| ---: | --- |
| term **required** | String term to search for in Company properties. |
| filter | Object containing query filters. See [Filters](#filters) section for more details. |

### HTTP Response

#### Arguments

|      |     |
| ---: | --- |
| id | Unique ID of Company model instance. |
| name | Name of Company. |
| address | Address of Company. |
| address2 | Address line two of Company. |
| city | City of Company. |
| zip | ZIP / post code of Company. |
| country | Country of Company. |
| taxNumber | Tax number of Company. |
| taxSubject | Boolean if Company is subject to VAT / GST / sales tax or other tax. |
| companyNumber | Company or other organization registration number. |
