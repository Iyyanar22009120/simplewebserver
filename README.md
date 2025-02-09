# Developing a Simple Webserver
## AIM:
Develop a webserver to display about top five web application development frameworks.

## DESIGN STEPS:
### Step 1: 
HTML content creation
### Step 2:
Design of webserver workflow
### Step 3:
Implementation using Python code
### Step 4:
Serving the HTML pages.
### Step 5:
Testing the webserver

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler

content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1>Top five web application development frameworks.</h1>
<ol style="font-size:25px;">
<li>React JS</li>
<li>Django</li>
<li>Node JS</li>
<li>Larvarel</li>
<li>Angular JS</li>
</ol>
</body>
</html>
"""

class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
#python3 simplewebserver.py
```
## OUTPUT:
![GitHub Logo](webpage.png)

## RESULT:
Thus a webserver developed to display about top five web application development frameworks
