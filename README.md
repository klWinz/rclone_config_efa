# Ein Google Team Drive mit rclone verbinden (ohne Client ID und Client Secret)

Diese Anleitung zeigt, wie man ein Google Team Drive mit rclone verbindet, ohne eine eigene Client ID oder Client Secret zu verwenden. Du kannst dich mit deinen **Google Account-Anmeldedaten** anmelden, auch wenn du die **Multi-Faktor-Authentifizierung (MFA)** aktiviert hast.

## 1. rclone konfigurieren

1. Starte die rclone-Konfiguration:
    ```bash
    rclone config
    ```

2. Wähle `n` für eine **neue Konfiguration**.

3. Gib einen Namen für das Remote ein, z. B. `gdrive`.

4. Wähle den Cloud-Anbieter aus. Gib `18` für **Google Drive** ein.

5. Bei der Eingabe der **client_id**: Lasse das Feld **leer** und drücke **Enter**.

6. Bei der Eingabe des **client_secret**: Lasse das Feld ebenfalls **leer** und drücke **Enter**.

7. Wähle den Zugriffstyp:
    - Gib `1` für **vollen Zugriff** (empfohlen) ein.
    - Gib `2` für **nur lesenden Zugriff** ein.

8. Wenn du den gesamten Google Drive synchronisieren möchtest, lasse das **Root-Ordner**-Feld leer.

9. Bei der Frage nach **Erweiterte Konfiguration** gib `n` für **Nein** ein.

10. Bei der Frage, ob die **automatische Konfiguration** genutzt werden soll, gib `y` für **Ja** ein.

11. Kopiere den angezeigten **Link** und öffne ihn in deinem Browser. Melde dich bei Google an und erteile die entsprechenden Berechtigungen.

12. Jetzt wird gefragt, ob ein **Shared Drive** (Team Drive) konfiguriert werden soll. Gib `y` für **Ja** ein.

13. Wähle das entsprechende Team Drive aus der angezeigten Liste anhand der Nummer.

14. Bestätige, dass du das eben erstellte **Remote** behalten möchtest, indem du `y` eingibst.

15. Mit `q` kannst du dann den Konfigurationmodus wieder verlassen.

## 2. Test der Konfiguration

1. Überprüfe, ob die Verbindung funktioniert, indem du folgenden Befehl ausführst:
    ```bash
    rclone lsd <Remote Name>:
    ```
    Ersetze `<Remote Name>` mit dem von dir vergebenen Namen, z. B. `gdrive`.

2. Du solltest nun die Ordnerstruktur deines Google Drive oder Team Drives sehen.
