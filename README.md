# EX01 Developing a Simple Webserver
## Date:

## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<h1>Welcome</h1>
</body>
</html>
'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```
## OUTPUT:
![Screenshot 2024-05-09 144551](https://github.com/dr-pvijayan/simplewebserver/assets/144979077/6d1b2e4a-f1dd-4625-b02a-2efb3d932b96)

![Screenshot 2024-03-15 134301](https://github.com/dr-pvijayan/simplewebserver/assets/144979077/0845cc18-cc9b-46a9-91f0-1c59fe655bc7)

## RESULT:
The program for implementing simple webserver is executed successfully.
