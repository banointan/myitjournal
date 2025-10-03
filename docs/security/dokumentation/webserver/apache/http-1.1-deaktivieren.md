# Apache
## Disable HTTP/1.1 and Enable Only HTTP/2 (h2)

This guide explains how to configure Apache so that **only HTTP/2 (h2)** is allowed, disabling HTTP/1.1 entirely. It includes all necessary steps, explanations, configuration examples, and verification commands based on the [official Apache documentation](https://httpd.apache.org/docs/2.4/howto/http2.html#basic-config). 

This setup applies to **Linux-based systems**, especially **Debian-based distributions** such as **Ubuntu**, where Apache is installed via package managers and modules are managed using `a2enmod`.  

It may also be adapted for other Unix-like systems (e.g. CentOS, Fedora, Arch), but paths and module management commands may differ slightly.

#### Prerequisites
- Apache version 2.4.17 or higher (required for HTTP/2 support)
- SSL certificate already configured
- Root access to your server

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
**Note:** This chapter is for informational purposes. If you are already familiar with Apache’s protocol negotiation and the Protocols directive, you may safely skip Step 2 or just read the [Apache Protocol Selection Overview](https://banointan.github.io/myitjournal/security/dokumentation/webserver/apache/http-1.1-deaktivieren/#apache-protocol-selection-overview).

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
This configuration enables only HTTP/1.1 globally but HTTP/2 plus HTTP/1.1 fallback on the `test.example.org` SSL host. If you want a particular site to use a different protocol setup, you can override the global settings within its `<VirtualHost>` block.

You can also add the ProtocolsHonorOrder directive together with Protocols, which controls whether Apache strictly enforces your preferred protocol order or allows clients to choose their preferred protocol.
```bash
Protocols http/1.1
ProtocolsHonorOrder off

<VirtualHost *:443>
    ServerName test.example.org
    Protocols h2
    ProtocolsHonorOrder On
</VirtualHost>
```

This configuration sets HTTP/2 and HTTP/1.1 as globally available protocols, with `ProtocolsHonorOrder off`, meaning Apache allows clients to choose their preferred protocol rather than strictly following the server’s order. In practice, this means a client that supports both HTTP/2 and HTTP/1.1 might still choose to use HTTP/1.1 globally — even if HTTP/2 is listed first.

However, for the virtual host `test.example.org`, the configuration explicitly enables only HTTP/2 and sets `ProtocolsHonorOrder On`. This instructs Apache to strictly enforce the server’s protocol preference for that host, ensuring that clients connecting to `test.example.org` will use HTTP/2 if they support it, regardless of their own preferences.

This setup is useful when you want to offer flexible protocol negotiation globally, while enforcing modern protocol usage like HTTP/2 for specific hosts or services.

#### Apache Protocol Selection Overview

To clarify how Apache selects the protocol based on your configuration, here’s a summary of common `Protocols` directive setups:

| Protocols Directive       | Behavior                                         |
|---------------------------|--------------------------------------------------|
| `Protocols h2 http/1.1`   | Prefers HTTP/2, allows fallback to HTTP/1.1     |
| `Protocols http/1.1 h2`   | Prefers HTTP/1.1, uses HTTP/2 only if client insists |
| `Protocols h2`            | Allows only HTTP/2, disables HTTP/1.1 completely |

The following table explains how the `ProtocolsHonorOrder` directive affects enforcement of your protocol preferences:

| ProtocolsHonorOrder       | Effect                                               |
|--------------------------|------------------------------------------------------|
| `ProtocolsHonorOrder On`     | Apache enforces your specified protocol order, ignoring client preferences |
| `ProtocolsHonorOrder Off`    | Client may override your order and choose a different protocol (e.g., HTTP/1.1) |

---

### Step 3: Disable HTTP/1.1 and Allow Only HTTP/2

