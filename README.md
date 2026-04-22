# Echoserver
Echo server and client using python socket
# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

HTML content creation is done

### Step 2:

Design of webserver workflow

### Step 3:

Implementation using Python code

### Step 4:

Serving the HTML pages.

### Step 5:

Testing the webserver

## PROGRAM:
```python
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<h1>Top Five Web Application Development Frameworks</h1>
<h2>1.Django</h2>
<h2>2. MEAN Stack</h2>
<h2>3. React </h2>
</body>
</html>'''


class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('keerthi',2323)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```
##  Architecture Diagram

```bash
+--------------------------+
|  User's Web Browser      |
|  (Client: Chrome/Firefox)|
+-----------+--------------+
            |
            |  HTTP Request (GET /)
            v
+-----------+--------------+
|   Python Web Server      |
| (http.server + Handler)  |
| - Listens on Port 8000   |
| - Handles GET Requests   |
| - Sends HTML Response    |
+-----------+--------------+
            |
            |  HTML Response
            v
+--------------------------+
|  User Sees Rendered Page |
|  <h1>Hello Web Server</h1>|
+--------------------------+
```


## OUTPUT:
### SERVER OUTPUT:
#### Code 
<img width="761" height="484" alt="Screenshot 2026-04-22 093927" src="https://github.com/user-attachments/assets/75035d1b-858e-4ab8-8c51-158646f3f12d" />


#### Output
<img width="730" height="64" alt="Screenshot 2026-04-22 094001" src="https://github.com/user-attachments/assets/2349444f-adfc-438c-a800-272e0bae499b" />

### CLIENT OUTPUT:
#### Code 
<img width="769" height="348" alt="Screenshot 2026-04-22 093939" src="https://github.com/user-attachments/assets/cbd0d960-8b97-4b7d-9545-2be5729eb971" />

#### Output
<img width="733" height="97" alt="Screenshot 2026-04-22 094012" src="https://github.com/user-attachments/assets/b4918c52-74c2-4db1-ba72-cdb19e8e8930" />

## RESULT:
The program is executed succesfully
