# Apache

Könntest du dich bitte einmal an dieser Anleitung versuchen: 
- https://httpd.apache.org/docs/2.4/howto/http2.html#basic-config (Basic Configuration)

In der Anleitung findest du an mehreren Stellen die Angabe "Protocols h2 http/1.1". Du wirst sehen, dass die Reihenfolge(http/1.1 h2 oder h2 http/1.1) unterschiedlich ist. Der Grund dafür wird in der Anleitung erklärt.

Für uns ist es jedoch wichtig, dass überall ausschliesslich  **"Protocols h2"** steht – also nicht "http/1.1" und auch nicht in Kombination wie "h2 http/1.1". 

Das bedeutet: überall, wo in der Anleitung etwas zu "Protocols ..." steht, bitte durch **"Protocols h2"** ersetzen.

Am Ende der Anleitung findest du ausserdem den Befehl  "ProtocolsHonorOrder Off". Diesen bitte durch **"ProtocolsHonorOrder On"** ersetzen.

So sollte die Anpassung am Ende etwa aussehen (kann von Konfiguration zu Konfiguration unterschiedlich sein:

```bash
Protocols h2
ProtocolsHonorOrder On 

<VirtualHost ...>
    ServerName test.example.org
    Protocols h2
    ProtocolsHonorOrder On 
</VirtualHost>
