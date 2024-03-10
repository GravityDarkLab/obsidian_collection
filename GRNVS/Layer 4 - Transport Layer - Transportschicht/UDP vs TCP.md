[[Transportschicht (Transport Layer)]].
[[UDP (User Datagram Protocol)]].
[[TCP (Transmission Control Protocol)]].

# UDP : 
- Verbindungslose Protokol -> kein overhead ->sehrt gut für broadcast und Multicast.
- Garentiert kein erflogreiche Übermittlung.
- Schwache Fehlererkennung (CRC).
- Schneller und Einfacher.
- Keine Sequenzierung.
- Verloren gegangene Pakete werden nicht nochmals übertragen.
- Header = 8 B
- DHCP , DNC , VoIP , TFTP , RIP
- bei streaming, multiplayer Spiele, Netflix zb.


# TCP: 
- Verbindungsorientierte Protokol --> verbindung aufbauen bevor schicken.
- Garantiert ein erfolgreiche Übermittlung.
- Umfangreiche Fehlererkennung.
- Sequenzierung -> richtige reihenfolge.
- Verloren gegangene Pakete werden nochmals übertragen.
- Header = 20 B
- HTTP ; HTTPS ; FTP ; TLNET
- E-mails , Nachrichten , Herunterladen zb.