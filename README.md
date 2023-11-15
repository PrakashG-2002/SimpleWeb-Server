# Developing a Simple Webserver
## DATE: 01:10:2023
## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation
### Step 2:
Design of webserver workflow
### Step 3:
Implementation using Python code
### Step 4:
Serving the HTML pages.
### Step 5:
Testing the webserver

## PROGRAM:
    from http.server import HTTPServer, BaseHTTPRequestHandler
    content = """
    <!DOCTYPE html>
    <html>
    <head>
    <title>My webserver</title>
    </head>
    <body>
    <h1>Top 5 Revenue Generating Companies<h1>
    <UL TYPE=“circle”>
    <LI> Amazon </LI>		
    <LI> Apple </LI>
    <LI> Tata </LI>
    <LI> ONGC </LI>
    <LI> Reliance Industries Limited </LI>
    </UL>
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

## OUTPUT:
<img width="960" alt="Screenshot 2023-09-09 093259" src="https://github.com/PrakashG-2002/SimpleWeb-Server/assets/144507749/e933c2db-65c5-4a0c-ad71-b4e40fa6430a">
<img width="960" alt="Screenshot 2023-09-09 093002" src="https://github.com/PrakashG-2002/SimpleWeb-Server/assets/144507749/c3b3349c-6bf1-4809-b595-23f95b3881db">

## RESULT:
The program for implementing simple webserver is executed successfully.
