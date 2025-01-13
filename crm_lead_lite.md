# API Formulario WEB

### Tipo de Documento
| Value | Odoo String | Web String |
|--|--|--|
| 5 | DNI |DNI|
| 3 | CE |CE|
###  ¿Qué tipo de negocio maneja?
| Value | Odoo String | Web String |
|--|--|--|
| 23 | Bodega | Bodega |
| 24 | Minimarket | Minimarket |
| 26 | Barbería | Barbería |
| 27 | Otros Negocios | Otro |
| 31 | Restaurante | Restaurant |
| 32 | Botica | Botica |
| 46 | Bar | Bar |
| 47 | Sportsbook | Sportsbook |
| 48 | Cabinas | Cabinas |
| 49 | Autolavado | Autolavado |
| 50 | Ferretería | Ferretería |

### Horarios
| Value | Odoo String | Web String |
|--|--|--|
| 51 | 10-12 | 10:00 - 12:00 |
| 52 | 12-14 | 12:00 - 14:00 |
| 53 | 14-16 | 14:00 - 16:00 |
| 54 | 16-18 | 16:00 - 18:00 |
| 55 | 18 a más | 18:00 - 18 a más:00 |


### API Information.

|Environment| Description | Value      |
| -----------| ------|----------|
|PRD| Endpoint(URL) | https://odoo.betgolperu.com/util/lead-lite |
|DEV| Endpoint(URL) | https://dev.betgolperu.com/util/lead-lite|
|| Method| POST |
|| (token)Authorization | We will send the token through a secure channel

#### JSON Values

|Key| Value | Description |
| --| --| --|
| name| Juan Perez | name entered in the form |
| l10n_latam_identification_type_id | 5 | selected in the form |
| vat | 45678987 | value entered in the form |
| phone| 999999999 | number entered in the form |
| email_from | example@example.com | email entered in the form |
|tag_ids | [46, 54] | array with values from "What kind of business do you run?"  and preferred time
| medium_id| 1 | Always use this value
| lang_id | 78 | Always use this value (Spanish language)

JSON 
```
{
    "name" : "Juan Perez",
    "l10n_latam_identification_type_id": "5",
    "vat": "45678987",
    "phone": "999999999",
    "email_from": "example@example.com",
    "tag_ids": [46, 54],
    "medium_id": 1,
    "lang_id": 78
}
```
