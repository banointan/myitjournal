# Apache
## Disable HTTP/1.1 and Enable Only HTTP/2 (h2)

This guide explains how to configure Apache so that **only HTTP/2 (h2)** is allowed, disabling HTTP/1.1 entirely. It includes all necessary steps, explanations, configuration examples, and verification commands based on the [official Apache documentation](https://httpd.apache.org/docs/2.4/howto/http2.html#basic-config). This setup applies to **Linux-based systems**, especially **Debian-based distributions** such as **Ubuntu**, where Apache is installed via package managers and modules are managed using `a2enmod`.  

It may also be adapted for other Unix-like systems (e.g. CentOS, Fedora, Arch), but paths and module management commands may differ slightly.

---

### Step 1: Verify if `mod_http2` is Installed and Enabled

Apache requires the `mod_http2` module to support HTTP/2. To check if it’s enabled, open a terminal on your server and run:

```bash
apache2ctl -M | grep http2
```

If you see `http2_module (shared)`, it means the module is active.

If there is **no** output, enable the module with:
```bash
sudo a2enmod http2
```
```bash
sudo systemctl restart apache2
```
After activation, it is important to verify once more that the http2_module is correctly loaded by running the above check command again. This ensures that the module was successfully enabled and Apache restarted properly.

On Ubuntu/Debian systems, enabling the module via a2enmod automatically loads it, so you don’t need to manually add the LoadModule line. However, for reference, the module is loaded via:
```bash
LoadModule http2_module modules/mod_http2.so
```
---

### Step 2: Understand the `Protocols` Directive
**Note:** This chapter is for informational purposes. If you are already familiar with Apache’s protocol negotiation and the Protocols directive, you may safely skip Step 2.

Apache’s Protocols directive controls which HTTP versions your server supports and in which order. 

The official documentation often shows configurations like:
```bash
Protocols h2 http/1.1
```
This means the server supports both HTTP/2 (h2) and HTTP/1.1, with HTTP/2 preferred. The order is important: the first protocol is the preferred one.

You might also see:
```bash
Protocols h2 h2c http/1.1
```
which enables all HTTP/2 variants (secure h2 and cleartext h2c) plus HTTP/1.1 fallback.

You can place the Protocols directive globally or inside specific virtual hosts. For example:
```bash
Protocols http/1.1

<VirtualHost *:443>
    ServerName test.example.org
    Protocols h2 http/1.1
</VirtualHost>
```
This configuration enables only HTTP/1.1 globally but HTTP/2 plus HTTP/1.1 on the `test.example.org` SSL host.

#### Apache Protocol Selection Overview

To clarify how Apache selects the protocol based on your configuration, here’s a summary of common `Protocols` directive setups:

| Protocols Directive        | Behavior                                         |
|---------------------------|--------------------------------------------------|
| `Protocols h2 http/1.1`   | Prefers HTTP/2, allows fallback to HTTP/1.1     |
| `Protocols http/1.1 h2`   | Prefers HTTP/1.1, uses HTTP/2 only if client insists |
| `Protocols h2`            | Allows only HTTP/2, disables HTTP/1.1 completely |

The following table explains how the `ProtocolsHonorOrder` directive affects enforcement of your protocol preferences:

| ProtocolsHonorOrder       | Effect                                               |
|--------------------------|------------------------------------------------------|
| `ProtocolsHonorOrder On`                     | Apache enforces your specified protocol order, ignoring client preferences |
| `ProtocolsHonorOrder Off`                    | Client may override your order and choose a different protocol (e.g., HTTP/1.1) |


---

### Step 3: Disable HTTP/1.1 and Allow Only HTTP/2
