# EX01 Developing a Simple Webserver
## Date: 13.03.2024

## AIM:
To develop a simple webserver to serve html pages.

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
 content = """
 <!DOCTYPE html>
 <html>
     <title> Image Map </title>
     <body>
          <table border = "2" cellspacing = "10" cellpading = "6">
               <caption> Top five revenue generating software companies</cap
               <tr>
                    <th>Rank</th>
                    <th>Company</th>
                    <th>Revenue</th>
                    <th>FY</th>
               </tr>
               <tr>
                    <td>1</td>
                    <td>Microsoft</td>
                    <td>$86.8</td>
                    <td>2014</td>
               </tr>
               <tr>
                    <td>2</td>
                    <td>Oracle</td>
                    <td>$37.1</td>
                    <td>2013</td>
               </tr>
               <tr>
                    <td>3</td>
                    <td>SAP</td>
                    <td>$20.9</td>
                    <td>2013</td>
               </tr>
               <tr>
                    <td>4</td>
                    <td>Symantec</td>
                    <td>$6.8</td>
                    <td>2013</td>
               </tr>
               <tr>
                    <td>5</td>
                    <td>VMware</td>
                    <td>$5.2  </td>
                    <td>2013</td>
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
 </html>
```
## OUTPUT:
<img width="957" alt="Screenshot-1" src="https://github.com/sreevarshad/simplewebserver/assets/128129573/900d8c8c-5aa8-42f8-a77d-a76716f9a01d">

<img width="949" alt="Screenshot-2" src="https://github.com/sreevarshad/simplewebserver/assets/128129573/dbc45a4c-41df-4257-a70f-a6c5b3ade75e">


## RESULT:
The program for implementing simple webserver is executed successfully.
