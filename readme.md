# 💡 Vorschlag: Hashwerte im URL-Fragment zur Integritätsprüfung (SHA-256)

Dieses Repository dokumentiert einen technischen **Vorschlag zur standardisierten Einbettung von Hashwerten in URLs**, insbesondere im **Fragment (`#...`)** und optional im **Query-String (`?...`)**, zur einfachen **Integritätsprüfung von Dateien** – ohne Serverbeteiligung.

> 🧪 Dieses Konzept wurde am 19. September 2025 gemeinsam mit [ChatGPT (OpenAI)](https://openai.com/chatgpt) entwickelt – als **Experiment** im Rahmen eines offenen, kollaborativen Denkprozesses.

---

## 📘 Hintergrund

Die Idee basiert auf der bestehenden `integrity`-Spezifikation (Subresource Integrity, SRI), erweitert diese aber:

- Um Unterstützung für **hexadezimal kodierte Hashwerte** (neben base64)
- Um **klarere Syntax** wie `#sha256:abcdef...`
- Und um die Möglichkeit, diese Angaben **clientseitig auszuwerten**

Das ermöglicht Web-Clients, Dateien bei Bedarf **on the fly zu verifizieren**, ganz ohne Serverlogik oder Signaturprüfung.

---

## 🧩 Motivation

- Subresource Integrity ist limitiert (nur base64, nur bestimmte Kontexte)
- URL-Fragment (`#...`) wird nicht an den Server übermittelt – ideal für clientseitige Integrität
- Query-Parameter (`?sha256=...`) ergänzen die Möglichkeit um serverseitige Nutzung
- Eine einheitliche Syntax wie `sha256:...` macht Parsing und Validierung einfacher

---

## 🧪 Experimentstatus

> ⚠️ **Wichtiger Hinweis:**  
> Dieses Projekt ist ein **offenes Experiment**, das im Dialog mit ChatGPT entstanden ist.  
> **Der Text, das Konzept und der begleitende Code sind weder offiziell noch getestet.**  
> Es handelt sich um einen **Diskussionsbeitrag** zur Weiterentwicklung bestehender Webstandards.

---

## 🔍 Beispiel für eine URL mit Hash-Fragment

```text
https://example.com/image.png#sha256:b4c52d276e8e2f0c...