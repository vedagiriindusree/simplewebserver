# EX01 Developing a Simple Webserver
## Date:22.02.2025

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
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
<head>
<title>Top five software companies in revenue</title>
</head>
<body>
<h1 align="center">
TOP FIVE SOFTWARE COMPANIES IN REVENUE</h1>
<table align="center" border="2" cellspacing="5" cellpadding="5" width="800" height="500">
<tr>
<th>RANK</th>
<th>COMPANY NAME</th>
<th>REVENUE</th>
</tr>
<tr>
<td>1</td>
<td>Apple(AAPL)</td>
<td>$385.70 B </td>
</tr>
<tr>
<td>2</td>
<td>Alphabet(Google)</td>
<td>$307.39 B</td>
</tr>
<tr>
<td>3</td>
<td>Microsoft</td>
<td>$227.58 B</td>
</tr>
<tr>
<td>4</td>
<td>Ibm</td>
<td>$61.85 B</td>
</tr>
<tr>
<td>5</td>
<td>Oracle</td>
<td>$51.62 B</td>
</tr>
</table>
</body>
</html>

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

![image](https://github.com/user-attachments/assets/241e582c-d21f-49a7-9cfe-f7ea2ef10655)


## RESULT:
The program for implementing simple webserver is executed successfully.
