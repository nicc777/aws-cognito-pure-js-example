# aws-cognito-pure-js-example

An example implementation of AWS Cognito with a Web Application using pure JavaScript (no SDK)

Please refer to the following BLOG entry for the detailed walk-through of this example code:

* Online: [Published 2022-06-06](https://www.nicc777.com/blog/2022/2022-06-06.html)
* GitHub: [Source for the blog post dated 2022-06-06](https://github.com/nicc777/nicc777-com-site/blob/main/site-src/docs/blog/2022/2022-06-06.md)

# Security Information

This code base is not suitable for production environments. 

Please note that the following known security issues exist:

* No verification of any of the JWT tokens is done
* The `state` is never validated within the flow
* No specific security measures have been taken to protect any private data

# Local Testing Quick Start

Basic steps:

_**Step 1**_: Update your Cognito configuration in `webapp.js`

```javascript
var awsRegion = "PLEASE-SET-ME";            // Example: eu-central-1
var cognitoUserPoolId = "PLEASE-SET-ME";    // Example: eu-central-1_XXXXXXXXX (this example does not point to a real ID)
var cognitoClientId = "PLEASE-SET-ME";      // Example: 1234567890abcdefghijklomnp (this example does not point to a real ID)
var cognitoAuthDomain = "PLEASE-SET-ME";    // Example: https://your-subdomain.auth.eu-central-1.amazoncognito.com
```

Please note that the above information is not considered "_secret_" as it is used in the configuration of the web application, which will run in potentially any user's browser and it is therefore visible to potentially any user of the web application.

Depending on how you configured your user pool and application, _**DO NOT**_ save a client secret here - it is not used in web applications. [Read more here...](https://www.oauth.com/oauth2-servers/client-registration/client-id-secret/)

_**Step 2**_: Start an Nginx Docker Instance

```shell
docker run --rm -p 8080:80 -v $(pwd):/usr/share/nginx/html nginx:latest
```

_**Step 3**_: Point your browser to http://localhost:8080/index.html
