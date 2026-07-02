# fortigate-katalog

Oeffentlicher Modellkatalog fuer den FortiGate Firewall- & Bundle-Berater.

Inhalt:
- `fortigate_models.json` - Geraetespezifikationen (Durchsatz, Tunnel, Interfaces, Formfaktor). Quelle: Fortinet Product Matrix.
- `fortigate_models.json.sig` - ECDSA-P-256-Signatur (SHA-256, Base64) ueber die Bytes von `fortigate_models.json`.

Dieses Repo enthaelt bewusst KEINE Preise und KEINE vertraulichen Daten - nur oeffentliche Spezifikationen.

Die Berater-App laedt `fortigate_models.json` ueber die Roh-URL und verifiziert die Signatur gegen einen
eingebetteten oeffentlichen Schluessel (WebCrypto), bevor der Katalog uebernommen wird. Nur vom Betreiber
signierte Daten werden akzeptiert; bei fehlender/ungueltiger Signatur bleibt der eingebaute Katalog erhalten.

Roh-URL:
https://raw.githubusercontent.com/ProjectPepper/fortigate-katalog/main/fortigate_models.json