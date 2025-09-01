# EX01 Developing a Simple Webserver
## Date:

## AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

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
content="""
<html>
    <head>
        <title> My web server</title>
    </head>
    <body>
        <table border="1" align="center" cellpadding="10"bgcolor="yellow">
            <caption><center><h1>LIST OF PROTOCOLS IN TCP/IP PROTOCOL SUITE</h1></center></caption>
            <tr>
                <th>S.NO.</th><th>NAME OF THE LAYER</th><th>NAME OF THE PROTOCOL</th>
            </tr>
            <tr>
                <td>1</td>
                <td>Application Layer</td>
                <td>HTTP,FTP,DNS,Telnet & SSH</td>
            </tr>
            <tr>
                <td>2</td>
                <td>Transport Layer </td>
                <td>TCP & UDP</td>
            </tr>
            <tr>
                <td>3</td>
                <td>Network Layer</td>
                <td>IPV4/IPV6</td>
            </tr>
            <tr>
                <td>4</td>
                <td>Network Interface Layer</td>
                <td>Ethenet,Token ring,ATM </td>
            </tr>

        </table>
    </body>
</html>
class Myserver(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200)
        self.send_header("content-type","text/html")
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver")

server_address=('',8000)
httpd=HTTPServer(server_address,Myserver)
httpd.serve_forever()
```
## OUTPUT:
<img width="1907" height="1135" alt="Screenshot 2025-09-01 083102" src="https://github.com/user-attachments/assets/af666a39-cfb1-4f12-84ef-581d015e317a" />




## RESULT:
The program for implementing simple webserver is executed successfully.
