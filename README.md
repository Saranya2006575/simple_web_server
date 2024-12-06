# EX01 Developing a Simple Webserver

# Date:05.10.24
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
from http.server import HTTPServer,BaseHTTPRequestHandler
content = """
<html lang="en">
<body>
<heading>
<h1><b>saranya</b></h1>
<h2>CONFIGURATION:24900574</h2>
<ol> 
 <li>Device name	DESKTOP-MOHHBTU</li>
 <li>Processor	13th Gen Intel(R) Core(TM) i5-1335U   1.30 GHz</li>
 <li>Installed RAM	16.0 GB (15.7 GB usable)</li>
 <li>Device ID	15EEA3B2-7EF5-4DEC-903D-577382C3C005</li>
 <li>Product ID	00342-42709-15956-AAOEM</li>
 <li><i>System type	64-bit operating system, x64-based processor</i></li>
 <li>Pen and touch	No pen or touch input is available for this display</li>
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
```
# OUTPUT:
![Screenshot 2024-12-06 212201](https://github.com/user-attachments/assets/e2d932e3-d355-487f-b724-1e815167cd34)

![Screenshot 2024-12-06 212246](https://github.com/user-attachments/assets/55b3211d-9a65-4b89-85ac-6d88255f529e)


# RESULT:
The program for implementing simple webserver is executed successfully.
