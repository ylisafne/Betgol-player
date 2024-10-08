# Landing Page Integration 

## Steps

1. In the button "¡Hablemos!" add function to show a modal (pop-up) with the form  like this (reference image)
![reference image](src/img/modal.png "Modal Example")

2. When user click in the SUBMIT button that it's in modal(pop-up). The information must be sent to the API ODOO CRM and the WhatsApp URL("https://api.whatsapp.com/send?phone=51990527400") we suggest use html tag target="_blank"

## API ODOO CRM
We have two environments, Developer (DEV) and Production (PRD) use the values ​​as appropriate

### API Information.

|Environment| Description | Value      |
| -----------| ------|----------|
|PRD| Endpoint(URL) | https://odoo.betgolperu.com/util/lead/red |
|DEV| Endpoint(URL) | https://dev.betgolperu.com/util/lead/red |
|| Method| POST |
|| (token)Authorization | We will send the token through a secure channel

#### JSON Values

|Key| Value | Description |
| --| --| --|
| name| Juan Perez | name entered in the form
| phone| 999999999 | number entered in the form  
| medium_id| 20 | Always use this value
| source_id| 319 |  This value is for the current URL "dev.betgol.biz". For new pages, it is necessary to request the new value 
| lang_id| 78 | Always use this value (Spanish language)

JSON Example
```
{
    "name": "Juan Perez",
    "phone": "999999999",
    "medium_id": 20,
    "source_id": 319,
    "lang_id": 78
}
```


Example Code **cURL** to DEV 
```
curl --location 'https://dev.betgolperu.com/util/lead/red' \
--header 'Content-Type: application/json' \
--header 'Authorization: token_here' \
--data '{
    "name": "Juan Perez",
    "phone": "999999999",
    "medium_id": 20,
    "source_id": 319,
    "lang_id": 78
}'
```
Example Code **JavaScript - fetch**  to DEV 
```
const myHeaders = new Headers();
myHeaders.append("Content-Type", "application/json");
myHeaders.append("Authorization", "••••••");

const raw = JSON.stringify({
  "name": "Juan Perez",
  "phone": "999999999",
  "medium_id": 20,
  "source_id": 319,
  "lang_id": 78
});

const requestOptions = {
  method: "POST",
  headers: myHeaders,
  body: raw,
  redirect: "follow"
};

fetch("https://dev.betgolperu.com/util/lead/red", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.error(error));
```
#### Response Example:
```
{
    "jsonrpc": "2.0",
    "id": null,
    "result": {
        "success": true,
        "id": 999
    }
}
```


