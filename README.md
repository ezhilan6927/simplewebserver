# EX01 Developing a Simple Webserver
## Date: 18.03.2023

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
               <caption> Top five revenue generating software companies</caption>
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
```

## OUTPUT:
![Screenshot (6)](https://github.com/ezhilan6927/simplewebserver/assets/160242249/8bac223d-3ead-4179-927b-5baa77c2a20e)
![313065118-d11407b9-6036-45b0-8173-8dbf9c912bfa](https://github.com/ezhilan6927/simplewebserver/assets/160242249/0bbb155f-f745-4974-98c6-5ca05e53f620)


## RESULT:
The program for implementing simple webserver is executed successfully.
