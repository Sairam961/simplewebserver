# EX01 Developing a Simple Webserver
## Date:03-10-2025

## AIM:
To develop a simple webserver to serve html pages and display the Device Specifications of your Laptop.

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
<!DOCTYPE html>
<html>
<head>
<title>Laptop Configuration</title>
<style> 
body {font-family: Arial, sans-serif;}
table {width: 60%}
th,td {border: 1 px solid #aaa;padding: 10px;}
th {background-color: #f2f2f2;}
</style>
</head>
<body>
<center>
<h1>Device Specifications</h1>
<table>
<tr><th>Specifications</th>
<th>Details</th></tr>
<tr>
<td>Brand</td>
<td>Lenovo</td>
</tr><tr>
<td>Model</td>
<td>Legion Pro 5</td>
</tr><tr>
<td>Processor</td>
<td>AMD Ryzen 9 7945 HX </td>
</tr><tr>
<td>RAM</td>
<td> 16 gb DDR5</td>
</tr><tr>
<td>Storage</td>
<td>1 TB SSD</td>
</tr><tr>
<td>Graphics Card</td>
<td>Nvidia GEFORCE RTX 4060</td>
</tr><tr>
<td>Operating System</td>
<td>Windows 11 Home</td>
</tr><tr>
<td>Screen Size</td>
<td> 16 inches </td>
</tr>
</table>
</center>
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
print("my webserver is running...")
httpd.serve_forever()

```


## OUTPUT:
![alt text](<Screenshot 2025-10-03 154642.png>)


![alt text](<Screenshot 2025-10-03 154742.png>)


## RESULT:
The program for implementing simple webserver is executed successfully.
