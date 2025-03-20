# EX01 Developing a Simple Webserver
## Date:18/03/2025

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.


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

content=""""
<html>
<head>
</head>
<body>
    <h1>LAPTOP CONFIGURATION</h1>
    <table border="2" cellpadding="10">
        <tr>
            <th>Property</th>
            <th>Details</th>
        </tr>
        <tr>
            <td>Device Name</td>
            <td>LAPTOP-P37ETSJO</td>
        </tr>
        <tr>
            <td>Processor</td>
            <td>AMD Ryzen 3 5300U with Radeon Graphics 2.60 GHz</td>
        </tr>
        <tr>
            <td>Installed RAM</td>
            <td>8.00 GB (7.33 GB usable)</td>
        </tr>
        <tr>
            <td>Device ID</td>
            <td>16508CEF-59BF-4873-8E6B-AE9FF5548F38</td>
        </tr>
        <tr>
            <td>Product ID</td>
            <td>00356-24755-03521-AAOEM</td>
        </tr>
        <tr>
            <td>System Type</td>
            <td>64-bit operating system, x64-based processor</td>
        </tr>
        <tr>
            <td>Pen and Touch</td>
            <td>No pen or touch input is available for this display</td>
        </tr>
    </table>
</body>
</html>

"""

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
!![alt text](<Screenshot 2025-03-18 210720.png>)
![alt text](<Screenshot 2025-03-18 210618.png>)




## RESULT:
The program for implementing simple webserver is executed successfully.
