# EX01 Developing a Simple Webserver

# Date:27-3-25
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """ 
<html>
<head>
    <title>Top Software Industries</title>
</head>
<body>
    <table border="2" cellspacing="10" cellpadding="6">
        <caption>Top 5 Revenue generating Software Companies</caption>
        <tr>
            <th>S. No</th>
            <th>Companies</th>
            <th>Revenue</th>
        </tr>
        <tr>
            <th>1</th>
            <th>Microsoft</th>
            <th>65 billion</th>
        </tr>
        <tr>
            <th>2</th>
            <th>Oracle</th>
            <th>29.6 billion</th>
        </tr>
        <tr>
            <th>3</th>
            <th>IBM</th>
            <th>29.1 billion</th>
        </tr>
        <tr>
            <th>4</th>
            <th>SAP</th>
            <th>6.4 billion</th>
        </tr>
        <tr>
            <th>5</th>
            <th>Symantec</th>
            <th>5.6 billion</th>
        </tr>
    </table>
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

server_address = ('', 8000)
httpd = HTTPServer(server_address, myhandler)
print("My webserver is running...")
httpd.serve_forever()
```


# OUTPUT:
![alt text](<Screenshot 2025-03-27 214909.png>)
![alt text](<Screenshot 2025-03-27 215057.png>)


# RESULT:
The program for implementing simple webserver is executed successfully.
