# EX01 Developing a Simple Web Server
## Date:

## AIM:
To develop a simple web server to serve HTML pages and display the list of protocols in the TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of web server workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
```
DEVELOPED BY: B R SWETHA NIVASINI
REG NO:212224040345
```


```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
    <head>
        <style>
            table{
                border-top: 10;
                border-bottom: 10;
                border-left: 10;
                border-right: 10;
                border-color: black;
            }
            td{
                background-color: aqua;
                font-size: medium;
            }
            th{
                background-color: lightblue;
                font-size: 20;
            }
        </style>
    </head>
    <body bgcolor="lightgray">
        <h1 style="color:darkgreen;text-align: center">TCP/IP Protocols - 24901190</h1>
        <table align="center" border="10" cellpadding="15" cellspacing="0" width=700>
            <tr">
                <th style="color:blue">Layer</th>
                <th style="color:blue">Protocol</th>
            </tr>
            <tr>
                <td>Application Layer</td>
                <td>HTTP, HTTPS, FTP, SMTP, DNS</td>
            </tr>
            <tr>
                <td>Transport Layer</td>
                <td>TCP, UDP, SCTP</td>
            </tr>
            <tr>
                <td>Internet Layer</td>
                <td>IP (IPv4, IPv6), ICMP, ARP</td>
            </tr>
            <tr>
                <td>Network Access Layer</td>
                <td>Ethernet, Wi-Fi, MAC, PPP</td>
            </tr>
            </th>
        </table>
    </body>
</html>

"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('Content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('', 8000)
httpd = HTTPServer(server_address, myhandler)
print("my webserver is running...")
httpd.serve_forever()
```


## OUTPUT:

![Screenshot 2025-05-27 210742](https://github.com/user-attachments/assets/6f76a47e-a30a-4e08-b846-a80ef66300ba)


![Screenshot 2025-05-27 210805](https://github.com/user-attachments/assets/67c2c169-2e77-44d2-af0d-80037a89fecb)





## RESULT:
The program for implementing a simple web server is executed successfully.
