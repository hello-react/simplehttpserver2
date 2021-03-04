# simplehttpserver2: Simple HTTP Server

Base on simplehttpserver (https://github.com/tikonen/blog/tree/master/simplehttpserver), add reverse proxy feature. 

'simpehttpserver' is an simple imitation of Python's SimpleHTTPServer and is intended for testing, development and debugging purposes

# Install globally

Install using `npm`

     npm install simplehttpserver2 -g
     
or using `yarn`

     yarn global add simplehttpserver2

# Usage

Run simplehttpserver2 by a command

     simplehttpserver2 [directory]

`[directory]` is used as a web root. Default is the current working directory.
Server listens the port 8000. Open browser to http://localhost:8000 to view.

**Security Consideration**. simplehttpserver2 does not care if symbolic links point outside the web root directory.

# Custom port

    simplehttpserver2 [directory] -p 8080
    
# Reverse proxy

    simplehttpserver2 -r /api=http://localhost:3001
    
Support multi proxies setting, seperate by comma.
    
    simplehttpserver2 -r /api/v1=http://localhost:3001,/api/v2=http://localhost:3002
    
# Custom MIME types

Additional MIME types can be defined by command line arguments.

     simplehttpserver2 --mime.text/mytype=my,my2 --mime.font/woff2=woff2 .
