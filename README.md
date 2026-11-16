# EX01 Developing a Simple Webserver
## Date: 16 /  11 / 2026
## Register Number : 26009606

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
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>TCP/IP — Simple Guide</title>
  <style>
    * { box-sizing: border-box; }

    body {
      margin: 0;
      padding: 40px 16px;
      background: #0b1020;
      color: #eef3ff;
      font: 16px/1.55 system-ui, sans-serif;
    }

    main {
      max-width: 760px;
      margin: 0 auto;
    }

    header { text-align: center; }

    h1 {
      margin: 8px 0;
      color: #65e1ef;
      font-size: 3.5rem;
    }

    header p, .layer p, .footer { color: #aab6cc; }

    .note, .layer {
      margin: 16px 0;
      padding: 16px;
      border: 1px solid #2a3650;
      border-radius: 12px;
      background: #151d31;
    }

    .note strong { color: #65e1ef; }

    .layer h2 {
      margin: 0;
      font-size: 1.1rem;
    }

    .layer p { margin: 5px 0 10px; }

    .protocol {
      display: inline-block;
      margin: 3px;
      padding: 3px 8px;
      border: 1px solid #34425c;
      border-radius: 7px;
      color: #ccecf1;
      font: 13px ui-monospace, monospace;
    }

    .footer {
      margin-top: 22px;
      text-align: center;
      font-size: 14px;
    }
  </style>
</head>
<body>
  <main>
    <header>
      <h1>TCP/IP</h1>
      <p>
        TCP/IP is a set of rules computers use to send information
        across the internet. It has four layers.
      </p>
    </header>

    <div class="note">
      <strong>Think of sending a package:</strong>
      write the message, pack it, address it, then deliver it.
      Each layer handles one part.
    </div>

    <section class="layer">
      <h2>4. Application — what you use</h2>
      <p>Helps apps browse websites, send email, and find addresses.</p>
      <span class="protocol">HTTP / HTTPS</span>
      <span class="protocol">DNS</span>
      <span class="protocol">SMTP</span>
      <span class="protocol">DHCP</span>
    </section>

    <section class="layer">
      <h2>3. Transport — how data is delivered</h2>
      <p>Moves information between apps. TCP checks delivery; UDP favors speed.</p>
      <span class="protocol">TCP</span>
      <span class="protocol">UDP</span>
      <span class="protocol">QUIC</span>
    </section>

    <section class="layer">
      <h2>2. Internet — where data goes</h2>
      <p>Addresses and routes data between networks.</p>
      <span class="protocol">IP (IPv4 / IPv6)</span>
      <span class="protocol">ICMP</span>
      <span class="protocol">IPsec</span>
    </section>

    <section class="layer">
      <h2>1. Link — how data travels nearby</h2>
      <p>Carries data over a local connection, such as Wi-Fi or Ethernet.</p>
      <span class="protocol">Wi-Fi</span>
      <span class="protocol">Ethernet</span>
      <span class="protocol">ARP</span>
    </section>

    <p class="footer">
      A website request travels down these layers. The reply comes back up.
    </p>
  </main>
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
server_address = ('',880)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```

## OUTPUT:
<img width="1915" height="938" alt="Screenshot 2026-11-14 160609" src="https://github.com/user-attachments/assets/a5f5680b-794c-4a40-8e96-5852d383f634" />
<img width="1282" height="282" alt="Screenshot 2026-11-14 160624" src="https://github.com/user-attachments/assets/16376626-bdee-4e5d-9162-559163e02274" />


## RESULT:
The program for implementing simple webserver is executed successfully.

