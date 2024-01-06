### Document For Betgol App

## Data Dictionary

| Field Name            | Type      | Is Required | Comments / Format                                                                          | Value Example                        | Original Field Name          |
| --------------------- | --------- | ----------- | ------------------------------------------------------------------------------------------ | ------------------------------------ | ---------------------------- |
| GUID                  | String    | Yes         | GUID is used to search for records in Odoo to determine if insert or update                | 00000000-00DC-AAAA-BBBB-D30E301B001F | PLAYER_GUID                  |
| first_name            | String    | Yes         |                                                                                            | First Name Example                   | FIRST_NAME                   |
| last_name             | String    | Yes         |                                                                                            | Last Name Example                    | LAST_NAME                    |
| street                | String    | No          |                                                                                            | Street Example                       | ADDRESS                      |
| city                  | String    | No          | Send only text city, controller search the id code if not exists value this set to null    | lima                                 | ADDRESS_CITY                 |
| country_id            | String    | No          | Send only text country, controller search the id code if not exists value this set to null | Peru                                 | ADDRESS_COUNTRY              |
| zip                   | String    | No          |                                                                                            | 27015                                | ADDRESS_POSTAL_CODE          |
| birthdate             | Date      | No          | format: '%Y-%m-%d'                                                                         | 2010-07-25                           | BIRTHDATE                    |
| mobile                | String    | Yes         | send country code after "+" and separate with space the country code of mobile number      | +51 956 896 478                      | MOBILE_PHONE                 |
| vat                   | String    | Yes         | send DNI field that it is populate from the registry form in betgol.com                    | 42132132                             |                              |
| email                 | String    | Yes         |                                                                                            | example@gmail.com                    | EMAIL                        |
| device                | String    | No          |                                                                                            | android                              | DEVICE                       |
| origin_website        | String    | No          |                                                                                            | m.tubetgol.com                       | REGISTERED_ON_WEBSITE        |
| reg_bonus_type        | String    | No          |                                                                                            | ¡BONO DE BIENVENIDA 100%!            | REGISTRATION_BONUS_TYPE      |
| account_number        | String    | No          |                                                                                            | 110001100022                         | ACCOUNT_NUMBER               |
| account_activation    | Date Time | No          | format : '%Y-%m-%d %H:%M:%S'                                                               | 2023-10-05 23:20:00                  | ACCOUNT_ACTIVATION_TIME      |
| account_invalidation  | Date Time | No          | format : '%Y-%m-%d %H:%M:%S'                                                               | 2023-10-05 23:20:00                  | INVALIDATION_TIME            |
| bonus_sports          | Bool      | No          |                                                                                            | true                                 | CONVERTED_BONUS_SPORTS       |
| bonus_casino          | Bool      | No          |                                                                                            | false                                | CONVERTED_BONUS_CASINO       |
| bets_aggregate_num    | Integer   | No          |                                                                                            | 5                                    | BETS_AGGREGATE_TOTAL_NUM     |
| bets_aggregate_amount | Float     | No          |                                                                                            | 100                                  | BETS_AGGREGATE_TOTAL_AMOUNT  |
| bets_last_date        | Date Time | No          | format : '%Y-%m-%d %H:%M:%S'                                                               | 2024-01-03 23:20:00                  | BETS_AGGREGATE_LAST_DATETIME |
| deposit_total_num     | Integer   | No          |                                                                                            | 10                                   | DEPOSIT_TOTAL_NUM            |
| deposit_total_amount  | Float     | No          |                                                                                            | 120.55                               | DEPOSIT_TOTAL_AMOUNT         |
| last_deposit          | Date Time | No          | format : '%Y-%m-%d %H:%M:%S'                                                               | 2024-01-01 15:45:45                  | DEPOSIT_LAST_DATETIME        |
| first_deposit         | Date Time | No          | format : '%Y-%m-%d %H:%M:%S'                                                               | 2023-09-09 09:09:09                  | DEPOSIT_1ST_DATETIME         |
| second_deposit        | Date Time | No          | format : '%Y-%m-%d %H:%M:%S'                                                               | 2023-10-10 10:10:10                  | DEPOSIT_2ND_DATETIME         |
| third_deposit         | Date Time | No          | format : '%Y-%m-%d %H:%M:%S'                                                               | 2023-12-12 12:12:12                  | DEPOSIT_3RD_DATETIME         |
| bets_sports           | Bool      | No          |                                                                                            | true                                 | BETS_SPORTS                  |
| bets_casino           | Bool      | No          |                                                                                            | true                                 | BETS_CASINO                  |
| bets_horse_riding     | Bool      | No          |                                                                                            | true                                 | BETS_HORSE_RIDING            |
| bets_virtual          | Bool      | No          |                                                                                            | false                                | BETS_VIRTUAL                 |

## How to Send Data

#This example is for Dev environment 


- Set API Endpoint 
```
https://dev.betgolperu.com/betgol_app/player/
```
- Add Authorization bearer token
```
f26c489d7cb337bdb86dd461e2513c276451eaae
```
- JSON body Example
```
{
    "tubetgol": {
        "GUID": "00000000-00DC-AAAA-BBBB-D30E301B001F",
        "first_name": "First Name Example",
        "last_name": "Last Name Example",
        "street": "Street Example",
        "city": "lima",
        "country_id": "Peru",
        "zip": "27015",
        "birthdate": "2010-07-25",
        "mobile": "+51 956 896 478",
        "vat": "42132132",
        "email": "example@gmail.com",
        "device": "android",
        "origin_website": "m.tubetgol.com",
        "reg_bonus_type": "¡BONO DE BIENVENIDA 100%!",
        "account_number": "110001100022",
        "account_activation": "2023-10-05 23:20:00",
        "account_invalidation": null,
        "bonus_sports": "true",
        "bonus_casino": "false",
        "bets_aggregate_num": 5,
        "bets_aggregate_amount": 100.58,
        "bets_last_date": "2024-01-03 23:20:00",
        "deposit_total_num": 10,
        "deposit_total_amount": "120.55",
        "last_deposit": "2024-01-01 15:45:45",
        "first_deposit": "2023-09-09 09:09:09",
        "second_deposit": "2023-10-10 10:10:10",
        "third_deposit": "2023-12-12 12:12:12",
        "bets_sports": "true",
        "bets_casino": "true",
        "bets_horse_riding": "true",
        "bets_virtual": "false"
    }
}
```

* Postman File for import [Example Postman](./dev_Betgol.postman_collection.json)
* Important!: if date, datetime, float or intger is empty send send null in JSON format like an "account_invalidation" that is inside of JSON example, for string just send ""





