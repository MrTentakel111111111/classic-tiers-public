# CLASSIC TIERS – öffentliche Mod (Minecraft 1.21.11, Fabric)

Zeigt Tiers direkt vor dem Namen an (z. B. **HT3|Sword**, grün auf dem schwarzen Nametag).
- **Taste J** (änderbar unter Optionen → Steuerung → Tastenbelegung → CLASSIC TIERS): wechselt durch Auto → Sword → Spear → Mace → UHC → SMP → Crystal → Pot → Cart. „Auto“ zeigt den höchsten Tier.
- **/atiers**: Fenster mit allen getesteten Spielern, Namenssuche oben links.
- Alle Befehle laufen nur im Mod und funktionieren auf jedem Server.
Voraussetzung: Fabric Loader und Fabric API für 1.21.11.

**Wichtig:** Der Tier-Server (Cloudflare Worker) wird im Paket „CLASSIC-TIERS-Tester“ im Ordner `worker` eingerichtet (Anleitung dort). Seine URL kommt in diese Mod.

## JAR-Datei bauen lassen (kostenlos über GitHub, ohne Java auf deinem PC)
1. Auf github.com ein Konto anlegen und ein **neues öffentliches-Repository** erstellen.
2. Den Inhalt dieses Ordners hochladen (**Add file → Upload files**, alles hineinziehen). Fehlt danach der versteckte Ordner `.github`, lege die Datei selbst an: **Add file → Create new file**, Name `.github/workflows/build.yml`, und füge den Inhalt von `build-workflow.yml` ein.
3. Trage im Browser (Stift-Symbol) ein:
   - `src/main/java/de/classictiers/Settings.java`: bei `API_URL` deine Worker-URL (`https://classic-tiers.DEINNAME.workers.dev`).
4. Oben auf **Actions** klicken. Der Bau startet automatisch (sonst „Mod bauen“ → **Run workflow**) und dauert wenige Minuten.
5. Wenn der Lauf grün ist, findest du die fertige **`classic-tiers-3.0.0.jar`** unter **Releases** (rechts auf der Startseite des Repositorys) zum direkten Herunterladen. Alternativ im Lauf unter **Artifacts**.
6. Wird der Lauf rot: auf den roten Schritt klicken und mir die Fehlermeldung schicken.

## Auf Modrinth hochladen (diese Datei ist dafür gedacht)
1. Auf modrinth.com ein Konto anlegen → **Create a project → Mod**.
2. Name **CLASSIC TIERS**, Zusammenfassung z. B.: „PvP-Tiers (z. B. HT3|Sword) im Nametag, mit Kit-Wechsel per Taste und /atiers-Liste.“ Als Icon `src/main/resources/assets/classictiers/icon.png` (grünes CT) verwenden.
3. Einstellungen: **Environment: Client-side required, Server-side unsupported**, Lizenz nach Wunsch (z. B. „All Rights Reserved“).
4. **Versions → Create version:** die JAR-Datei `classic-tiers-3.0.0.jar` hochladen, Loader **Fabric**, Spielversion **1.21.11**, Abhängigkeit **Fabric API (required)**, Versionsnummer `3.0.0`.
5. Zur Prüfung einreichen. Erwähne in der Beschreibung, dass die Mod Tier-Daten von einem eigenen Server lädt.

Nicht öffentlich weitergeben: die Tester-Mod (`classic-tiers-tester`), denn sie enthält das Tester-Passwort.

## Hinweise
- Nur für **1.21.11**. Neuere Versionen (z. B. 26.1) brauchen eine eigene Anpassung.
- Das Tier steht im selben Nametag vor dem Namen (wie bei anderen Tier-Mods), nicht als eigene Zeile. Server mit eigenen Namensschildern zeigen es nicht an.
- Der Code wurde nicht in Minecraft getestet.
