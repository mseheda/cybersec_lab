
# Python Web Server with IP Filtering

## What I Have Done

1. **Set up a Python web server**:
   - Created a Python script using Flask to serve a simple web page.
   - Configured the web server to run on port `8080`.

2. **Configured `iptables` for prerouting**:
   - Redirected incoming traffic on port `80` to the Python web server running on port `8080` using `iptables` NAT table.

3. **Implemented IP filtering**:
   - Allowed access to the web server only from specific IP addresses.
   - Blocked all other IPs from accessing the server.

## What It Does

- The Python web server displays a simple message when accessed through the browser.
- `iptables` rules ensure that:
  - Traffic on port `80` is redirected to the web server on port `8080`.
  - Only the specified IP addresses can access the web server, while all others are blocked.

## How to Test

### 1. Verify the Web Server
- Ensure the Python web server is running on port `8080`:
  ```bash
  curl http://127.0.0.1:8080
  ```
- The output should display the message served by the web server.

### 2. Test IP Filtering
- Access the web server from an **allowed IP**:
  - Open a browser and navigate to `http://<your_server_ip>`. The web page should load successfully.
- Access the web server from a **blocked IP**:
  - Open a browser from a non-allowed IP and navigate to `http://<your_server_ip>`. The connection should be blocked.

### 3. Verify `iptables` Rules
- View the configured `iptables` rules:
  ```bash
  sudo iptables -L -v -n
  sudo iptables -t nat -L -v -n
  ```
- Ensure the prerouting and filtering rules are in place.

## Commands Used

### Setting Up the Web Server
```bash
python web_server.py
```

### Configuring `iptables` Rules
- Redirect traffic from port `80` to `8080`:
  ```bash
  sudo iptables -t nat -A PREROUTING -p tcp --dport 80 -j REDIRECT --to-port 8080
  ```
- Allow specific IPs:
  ```bash
  sudo iptables -A INPUT -p tcp -s <allowed_ip1> --dport 80 -j ACCEPT
  sudo iptables -A INPUT -p tcp -s <allowed_ip2> --dport 80 -j ACCEPT
  ```
- Block all other IPs:
  ```bash
  sudo iptables -A INPUT -p tcp --dport 80 -j DROP
  ```

---

By following this setup, the web server is secure, accessible only to specified IPs, and functional for testing.
