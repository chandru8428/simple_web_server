# EX01 Developing a Simple Webserver

# Date:10-11-2024
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

      <!doctype html>
     <html>
     <head>
     <title> Web Server</title>
     </head>
     <body style="background-color: rgba(200, 162, 115, 0.756);">
      <h1><center>My Laptop Configuration Details</center></h1>
    <table border="1" cellpadding="10" align="center" style="font-style: inherit;font-family: fantasy;color: rgb(10, 46, 46);background-color: azure;">
        <tr style="font-family: sans-serif;">
            <th bgcolor="blue">Specification</th>
            <th bgcolor="gray"">Details</th>
        </tr>
        <tr>
            <td>Model</td>
            <td>Lenovo ThinkPad E16 Gen-1</td>
        </tr>
        <tr>
            <td>Processor</td>
            <td>13th Gen Intel(R) Core(TM) i5-1335U  1.30 GHz</td>
        </tr>
        <tr>
            <td>RAM</td>
            <td>16GB</td>
        </tr>
        <tr>
            <td>Storage</td>
            <td>512GB SSD</td>
        </tr>
        <tr>
            <td>Graphics card</td>
            <td>NVIDIA Geforce mx550</td>
        </tr>
        <tr>
            <td>Display</td>
            <td>16-inch FHD (1920 x 1080)</td>
        </tr>
        <tr>
            <td>Operating System</td>
            <td>Windows 11 Home </td>
        </tr>
        <tr>
            <td>System type</td>
            <td>64-bit operating system, x64-based processor</td>
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
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```


# OUTPUT:
![alt text](<Screenshot 2024-12-06 170610.png>)

![alt text](<Screenshot 2024-12-06 170644.png>)

# RESULT:
The program for implementing simple webserver is executed successfully.
