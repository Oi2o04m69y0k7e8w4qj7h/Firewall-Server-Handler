# Firewall-Server-Handler
host = "localhost"
port = 8000
def block_request (self):
    print ("Blocking request")
def handle_request(self):
    self.send_response(200)
    self.send_header("content-type", "application/json")
    self.end_headers()
class ServerHandler(BaseHTTPRequestHandler):
    def do_GET(self):
    handle_request(self)
def do_POST(self):
    handle_request(self)
if __name__ == "__main__":
   server = HTTPServer((host, port), ServerHandler)
   print("[+] Firewall Server")
   print("[+] HTTP Web Server running on: %s:%s" % (host,  port))
try:
    server.server_forever()
except KeyboardInterrupt:
    pass
