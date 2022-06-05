# aws-cognito-pure-js-example

An example implementation of AWS Cognito with a Web Application using pure JavaScript (no SDK)

Please refer to the following BLOG entry for the detailed walk-through of this example code:

* Online: coming soon...
* GitHub: [Source for the blog post dated 2022-06-06](https://github.com/nicc777/nicc777-com-site/blob/main/site-src/docs/blog/2022/2022-06-06.md)

# Security Information

This code base is not suitable for production environments. 

Please note that the following known security issues exist:

* No verification of any of the JWT tokens is done
* The `state` is never validated within the flow
* No specific security measures have been taken to protect any private data
