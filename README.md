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
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>Top 5 Revenue Company</title>
</head>
<body>
<h1><u>Top 5 Revenue Company</u><h1>
<ul>
<li>Apple</li>
<li>Microsoft</li>
<li>Mi</li>
<li>BlueBerry</li>
<li>Google</li>
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
```
  
  ## OUTPUT:


  ![image](https://github.com/22003197/simplewebserver/assets/124332243/f6712453-c37c-43f2-809e-84643706ce66)
  ![image](https://github.com/22003197/simplewebserver/assets/124332243/042c2a18-f653-422b-9635-bba78ba09169)






## RESULT:
The program for implementing simple webserver is executed successfully.
