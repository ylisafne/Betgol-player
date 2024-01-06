### Document For Betgol App

## Data Dictionary

| Original Field Name          | Field2                | Type / Format               | Value required | Value Example                        | Comments                                                                                   |
| ---------------------------- | --------------------- | --------------------------- | -------------- | ------------------------------------ | ------------------------------------------------------------------------------------------ |
| PLAYER_GUID                  | GUID                  | String                      | Yes            | 00000000-00DC-AAAA-BBBB-D30E301B001F | GUID is used to search for records in Odoo to determine if insert or update                |
| FIRST_NAME                   | first_name            | String                      | Yes            | First Name Example                   |                                                                                            |
| LAST_NAME                    | last_name             | String                      | Yes            | Last Name Example                    |                                                                                            |
| ADDRESS                      | street                | String                      | No             | Street Example                       |                                                                                            |
| ADDRESS_CITY                 | city                  | String                      | No             | lima                                 | Send only text city, controller search the id code if not exists value this set to null    |
| ADDRESS_COUNTRY              | country_id            | String                      | No             | Peru                                 | Send only text country, controller search the id code if not exists value this set to null |
| ADDRESS_POSTAL_CODE          | zip                   | String                      | No             | 27015                                |                                                                                            |
| BIRTHDATE                    | birthdate             | Date / %Y-%m-%d             | No             | 2010-07-25                           |                                                                                            |
| MOBILE_PHONE                 | mobile                | String                      | Yes            | +51 956 896 478                      | send country code after "+" and separate with space the country code of mobile number      |
|                              | vat                   | String                      | Yes            | 42132132                             | send DNI field that it is populate from the registry form in betgol.com                    |
| EMAIL                        | email                 | String                      | Yes            | example@gmail.com                    |                                                                                            |
| DEVICE                       | device                | String                      | No             | android                              |                                                                                            |
| REGISTERED_ON_WEBSITE        | origin_website        | String                      | No             | m.tubetgol.com                       |                                                                                            |
| REGISTRATION_BONUS_TYPE      | reg_bonus_type        | String                      | No             | ¡BONO DE BIENVENIDA 100%!            |                                                                                            |
| ACCOUNT_NUMBER               | account_number        | String                      | No             | 110001100022                         |                                                                                            |
| ACCOUNT_ACTIVATION_TIME      | account_activation    | Date Time %Y-%m-%d %H:%M:%S | No             | 2023-10-05 23:20:00                  |                                                                                            |
| INVALIDATION_TIME            | account_invalidation  | Date Time %Y-%m-%d %H:%M:%S | No             | 2023-10-05 23:20:00                  |                                                                                            |
| CONVERTED_BONUS_SPORTS       | bonus_sports          | Bool                        | No             | true                                 |                                                                                            |
| CONVERTED_BONUS_CASINO       | bonus_casino          | Bool                        | No             | false                                |                                                                                            |
| BETS_AGGREGATE_TOTAL_NUM     | bets_aggregate_num    | Integer                     | No             | 5                                    |                                                                                            |
| BETS_AGGREGATE_TOTAL_AMOUNT  | bets_aggregate_amount | Float                       | No             | 100                                  |                                                                                            |
| BETS_AGGREGATE_LAST_DATETIME | bets_last_date        | Date Time %Y-%m-%d %H:%M:%S | No             | 2024-01-03 23:20:00                  |                                                                                            |
| DEPOSIT_TOTAL_NUM            | deposit_total_num     | Integer                     | No             | 10                                   |                                                                                            |
| DEPOSIT_TOTAL_AMOUNT         | deposit_total_amount  | Float                       | No             | 120.55                               |                                                                                            |
| DEPOSIT_LAST_DATETIME        | last_deposit          | Date Time %Y-%m-%d %H:%M:%S | No             | 2024-01-01 15:45:45                  |                                                                                            |
| DEPOSIT_1ST_DATETIME         | first_deposit         | Date Time %Y-%m-%d %H:%M:%S | No             | 2023-09-09 09:09:09                  |                                                                                            |
| DEPOSIT_2ND_DATETIME         | second_deposit        | Date Time %Y-%m-%d %H:%M:%S | No             | 2023-10-10 10:10:10                  |                                                                                            |
| DEPOSIT_3RD_DATETIME         | third_deposit         | Date Time %Y-%m-%d %H:%M:%S | No             | 2023-12-12 12:12:12                  |                                                                                            |
| BETS_SPORTS                  | bets_sports           | Bool                        | No             | true                                 |                                                                                            |
| BETS_CASINO                  | bets_casino           | Bool                        | No             | true                                 |                                                                                            |
| BETS_HORSE_RIDING            | bets_horse_riding     | Bool                        | No             | true                                 |                                                                                            |
| BETS_VIRTUAL                 | bets_virtual          | Bool                        | No             | false                                |                                                                                            |



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
        "account_invalidation": "2023-10-05 23:20:00",
        "bonus_sports": "true",
        "bonus_casino": "false",
        "bets_aggregate_num": "5",
        "bets_aggregate_amount": "100",
        "bets_last_date": "2024-01-03 23:20:00",
        "deposit_total_num": "10",
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

#



