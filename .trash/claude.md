---

## tags: [meta, claude, obsidian, setup] status: in-progress erstellt: 2026-07-28

# 🗺️ Fahrplan: Claude sinnvoll für mich einrichten

> [!info] Ziel Claude nicht nur als Chat nutzen, sondern als verzahntes System: Skills, die automatisch greifen, eine Verbindung zu Obsidian als Wissensspeicher, und Notion als Tracking-Layer. Am Ende soll Claude "wissen", wie du arbeitest — ohne dass du es jedes Mal neu erklären musst.

---

## Phase 1 — Fundament: Skills verstehen & aufräumen

### ☐ 1.1 Bestehende Skills sichten

**Was tun:** Öffne deine Skills-Übersicht (in Claude.ai unter Einstellungen → Capabilities, oder wo du die `strukturiertes-lernen`- und `emotionale-reflexion`-Skills abgelegt hast) und lies dir jede `SKILL.md` einmal komplett durch. **Warum:** Du hast schon mehrere eigene Skills gebaut (u. a. aus GitHub importierte Priming-/Feynman-Skills). Bevor du neue baust, musst du wissen, was schon da ist — sonst entstehen Dopplungen, die sich gegenseitig ins Gehege kommen.

### ☐ 1.2 Trigger-Beschreibungen schärfen

**Was tun:** Prüfe bei jedem Skill die `description:` im Frontmatter — steht dort klar, _wann_ er greifen soll? Schreibe unscharfe Beschreibungen um (z. B. nicht "Lernhilfe" sondern "Trigger bei: 'ich möchte X lernen', 'erkläre mir X'…"). **Warum:** Skills werden nur automatisch geladen, wenn die Beschreibung eindeutig zur Nutzeranfrage passt. Eine vage Beschreibung heißt: Der Skill wird nie oder falsch getriggert.

### ☐ 1.3 Einen "IT-Arbeitsalltag"-Skill anlegen

**Was tun:** Baue (analog zu `strukturiertes-lernen`) einen neuen Skill `it-support-workflow`, der greift bei Formulierungen wie "Ticket zu X", "Problem bei Kunde/Kollege Y", "wie dokumentiere ich das in Zammad". Er sollte deinen Standard-Ablauf enthalten: Diagnose → Lösung → Zammad-Dokumentation → ggf. Obsidian-Wiki-Eintrag. **Warum:** Dein Alltag (Bareos, AutoCAD-Fehler, Zammad-Doku) wiederholt sich strukturell. Ein eigener Skill spart dir, den Kontext (richter.local, Zammad, dein Dokumentationsstil) jedes Mal neu mitzugeben.

---

## Phase 2 — Obsidian mit Claude verbinden

> [!warning] Wichtig zu wissen Claude Desktop kann dein Obsidian-Vault **nicht magisch "sehen"**. Die Verbindung läuft technisch über den sogenannten **MCP (Model Context Protocol) Filesystem-Server** — ein kleines Verbindungsstück, das Claude Desktop erlaubt, gezielt auf einen Ordner auf deiner Festplatte zuzugreifen (lesen, ggf. auch schreiben).

### ☐ 2.1 Claude Desktop installieren (falls noch nicht vorhanden)

**Was tun:** Lade Claude Desktop für Windows herunter und installiere es normal. **Warum:** Die Vault-Anbindung per MCP funktioniert aktuell nur über die Desktop-App, nicht über den Browser-Chat.

### ☐ 2.2 Node.js installieren

**Was tun:** Node.js (LTS-Version) von nodejs.org installieren, falls auf deinem Rechner noch nicht vorhanden (`node -v` in PowerShell prüfen). **Warum:** Der MCP-Filesystem-Server läuft technisch über `npx` (Node.js-Werkzeug) — ohne Node.js startet die Verbindung gar nicht erst.

### ☐ 2.3 Claude Desktop Konfigurationsdatei öffnen

**Was tun:** In Claude Desktop unter Einstellungen → Developer → "Edit Config" (öffnet `claude_desktop_config.json` in deinem Editor). **Warum:** Hier trägst du ein, welche externen "Werkzeuge" (MCP-Server) Claude zur Verfügung stehen sollen — die Datei ist quasi das Adressbuch für Verbindungen.

### ☐ 2.4 Filesystem-Server für dein Vault eintragen

**Was tun:** In die Config einen Eintrag für den Filesystem-Server mit dem Pfad zu deinem Obsidian-Vault ergänzen (Pfad z. B. `C:\\Users\\DeinName\\Documents\\ObsidianVault`). Danach Claude Desktop komplett neu starten. **Warum:** Erst mit dem korrekten Pfad weiß der Server, welchen Ordner er freigeben soll — ohne Neustart wird die Config nicht neu eingelesen.

### ☐ 2.5 Verbindung testen

**Was tun:** In Claude Desktop fragen: "Liste die Dateien in meinem Obsidian-Vault auf" oder "Lies meine Notiz zu XCP-ng." **Warum:** So bestätigst du sofort, ob die Verbindung wirklich steht, bevor du dich auf sie verlässt.

### ☐ 2.6 Schreibrechte bewusst entscheiden

**Was tun:** Überlege, ob Claude in dein Vault auch **schreiben** darf (z. B. neue Notizen aus Chats direkt ablegen) oder nur lesen soll. Falls schreiben: im gleichen Config-Eintrag den entsprechenden Modus setzen bzw. einen zweiten, klar benannten Unterordner (z. B. `_claude-inbox`) als Schreibziel angeben. **Warum:** Dein IT-Wiki ist strukturiert gewachsen — ungefilterte automatische Schreibzugriffe könnten diese Struktur durcheinanderbringen. Ein dedizierter Eingangsordner lässt dich Claude-Output bewusst einsortieren statt ihn blind vertrauen zu müssen.

---

## Phase 3 — Notion & Claude verzahnen

### ☐ 3.1 Notion-Connector in Claude.ai aktivieren

**Was tun:** In Claude.ai unter Einstellungen → Connectors prüfen, ob Notion schon verbunden ist; falls nicht, verbinden und den Workspace mit deiner `MyHabits`-Datenbank sowie dem Study-Dashboard freigeben. **Warum:** Damit kann Claude direkt aus dem Chat auf deine Notion-Datenbanken zugreifen, statt dass du Inhalte hin- und herkopierst.

### ☐ 3.2 Klare Aufgabenteilung Obsidian vs. Notion festlegen

**Was tun:** Schreib dir (z. B. ganz oben in dieser Notiz oder als eigene Notiz "System-Übersicht") eine feste Regel: Obsidian = Wissen/Dokumentation (IT-Wiki, Lernnotizen), Notion = Tracking/Status (Habits, Study-Dashboard, offene Aufgaben). **Warum:** Zwei Tools mit überlappendem Zweck führen sonst dazu, dass du nicht mehr weißt, wo etwas steht — die Trennung nach _Zweck_ statt nach Bauchgefühl hält beide Systeme sauber nutzbar.

### ☐ 3.3 Lernfortschritt aus `strukturiertes-lernen`-Sessions in Notion spiegeln

**Was tun:** Nach jeder Lern-Session (z. B. Networking, Intune) einen kurzen Eintrag im Study-Dashboard nachtragen — entweder manuell oder Claude direkt am Ende der Session bitten: "Trag das kurz in mein Notion Study-Dashboard ein." **Warum:** Deine Lernblöcke aus dem Self-Assessment sind über mehrere Sessions verteilt; ohne zentrale Statusübersicht verlierst du den Überblick, welche Lücken schon geschlossen sind.

---

## Phase 4 — Zammad-Wissen & Claude verbinden

### ☐ 4.1 Prüfen, ob ein Zammad-MCP-Connector existiert

**Was tun:** In Claude.ai unter Connectors nach "Zammad" suchen bzw. Claude direkt fragen, ob ein passender Connector im Verzeichnis verfügbar ist. **Warum:** Falls ja, kannst du Tickets direkt aus dem Chat abfragen/dokumentieren lassen, statt manuell zwischen Zammad und Claude zu wechseln — falls nein, bleibt der Weg über Copy-Paste oder E-Mail-Export.

### ☐ 4.2 Standard-Prompt-Vorlage für Zammad-Doku erstellen

**Was tun:** Leg dir in Obsidian eine Notiz "Prompt-Vorlagen" an mit einem Baustein wie: "Hier ist mein gelöstes Problem: [Beschreibung]. Formuliere mir daraus einen Zammad-Knowledge-Base-Artikel in meinem üblichen Stil (kurz, technisch, mit Schritt-für-Schritt-Lösung)." **Warum:** Du baust die Zammad-Wissensdatenbank bereits aktiv aus — eine feste Vorlage macht das für dich wiederholbar und für Claude konsistent, statt jedes Mal neu zu formulieren.

---

## Phase 5 — Feinschliff & Routine

### ☐ 5.1 Wöchentlichen Reflexions-Check einbauen

**Was tun:** Einmal pro Woche (z. B. Freitagnachmittag) kurz mit Claude durchgehen: Was lief gut, was war unklar, welcher Skill hat nicht wie erwartet getriggert. **Warum:** Skills und Verbindungen sind kein "einmal einrichten und fertig" — durch echte Nutzung zeigen sich Lücken erst, wenn du im Alltag damit arbeitest.

### ☐ 5.2 Skills bei Bedarf iterativ verbessern

**Was tun:** Wenn ein Skill falsch oder gar nicht triggert, direkt die `description:` im Frontmatter anpassen statt einen neuen Skill danebenzubauen. **Warum:** Viele überlappende Skills verwirren das Auto-Loading mehr, als sie helfen — ein gepflegter Skill schlägt drei halbfertige.

### ☐ 5.3 Diese Notiz selbst als lebendes Dokument pflegen

**Was tun:** Hake die Kästchen ab, sobald erledigt, und ergänze unten neue Punkte, die dir im Alltag auffallen. **Warum:** Der Fahrplan ist kein Einmal-Projekt, sondern wächst mit deinem Setup — genau wie dein IT-Wiki organisch gewachsen ist.

---

> [!tip] Reihenfolge-Empfehlung Phase 1 → Phase 2 → Phase 3 in dieser Reihenfolge abarbeiten. Phase 4 und 5 laufen nebenbei und dauerhaft mit.