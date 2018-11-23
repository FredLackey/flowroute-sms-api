# Flowroute SMS API
Simple API for communicating with the Flowroute SMS API.

## Other Projects  
This project is only *part* of the entire Flowroute API.  Other projects are:

|  Project  |  Description  |
|-----------|---------------|
|  [`flowroute-sms-api`](https://github.com/FredLackey/flowroute-sms-api)  |  SMS Messaging  |
|  [`flowroute-mms-api`](https://github.com/FredLackey/flowroute-mms-api)  |  MMS Messaging  |
|  [`flowroute-messaging-api`](https://github.com/FredLackey/flowroute-messaging-api)  |  SMS & MMS Messaging  |

## Installation  
```
npm i --save flowroute-sms-api
```

## Example Usage  
```
const sms = require('flowroute-sms-api');
const params = require('./params.json');

const { from, to, body, callbackUrl, accessKey, secretKey } = params;

let id = '';
if (callbackUrl) {
  sms.send.withCallback(from, to, body, callbackUrl, accessKey, secretKey, (err, info) => {
    if (err) { throw err; }
    id = info.id;
  });
} else {
    sms.send.withoutCallback(from, to, body, accessKey, secretKey, (err, info) => {
    if (err) { throw err; }
    id = info.id;
  });
}

console.log(`Message ID: ${id}`);
```

## Author Info  
This project has been created for my personal use.  **It is maintained.**  Feel free to use it at your leisure.  If you need help, either open an [issue](https://github.com/FredLackey/flowroute-sms-api/issues) or get in touch directly:  

**Fred Lackey**  
[fred.lackey@gmail.com](mailto://fred.lackey@gmail.com)  
[www.fredlackey.com](http://www.fredlackey.com)