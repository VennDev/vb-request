# Info
- This is the package used to balance the volume of requests from clients for your software.

# Example
```js
const vbrequest = require('vb-request');

const test = async () =>
{
    const response = await vbrequest.get('servers1', '/')
    console.log(response);
}

test();

const test2 = async () =>
{
    const response = await vbrequest.get('servers2', '/controllerName/methodName', {
        Headers: {
            'Content-Type': 'application/json',
            'Authorization': 'Bearer %token%' 
        },
        Query: {
            'param1': 'value1',
            'param2': 'value2'
        },
    })
    console.log(response);
}

test2();
```

# Config
```yml
groups:
  servers1:
    server-choosing: 2
    servers:
      '1':
        url: http://google.com
        token: token
      '2':
        url: http://localhost:3001
        token: token
  servers2:
    server-choosing: 1
    servers:
      '1':
        url: http://localhost:3000
        token: token
      '2':
        url: http://localhost:3001
        token: token
```

# Why?
<image src="https://github.com/VennDev/Data-Folder/blob/main/images/image.jpg">