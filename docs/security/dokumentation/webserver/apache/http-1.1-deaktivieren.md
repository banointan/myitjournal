# Apache
## Disable HTTP/1.1 and Enable Only HTTP/2 (h2)

This guide explains how to configure Apache so that **only HTTP/2 (h2)** is allowed, disabling HTTP/1.1 entirely. It includes all necessary steps, explanations, configuration examples, and verification commands based on the [official Apache documentation](https://httpd.apache.org/docs/2.4/howto/http2.html#basic-config).

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

On Ubuntu/Debian systems, enabling the module via a2enmod automatically loads it, so you don’t need to manually add the LoadModule line. However, for reference, the module is loaded via:
```bash
LoadModule http2_module modules/mod_http2.so
```
---

