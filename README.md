# Sprecherprotokoll – zentrale Stammdaten

Dieses Repository stellt die **veröffentlichten Stammdaten** für die Anwendung
„Sprecherprotokoll“ bereit (öffentlich lesbar, kein GitHub-Konto nötig).

## Inhalt

| Datei | Bedeutung |
|---|---|
| `stammdaten.json` | Signierter Stammdatenstand (Gremien, Mitgliedschaften und Funktionen). Kontaktdaten sind darin nur **verschlüsselt** enthalten und nur mit dem vertraulich weitergegebenen Freischaltcode lesbar. Wird ausschließlich über „Änderungen veröffentlichen“ in der Anwendung geschrieben. |
| `bearbeitungszugang.json` | **Verschlüsseltes** Bearbeitungspaket für die berechtigten Personen. Ohne gemeinsames Passwort **und** den auf dem eingerichteten Rechner gespeicherten Einrichtungsschlüssel nicht lesbar. |
| `passwortstatus.json` | Signierte **Versionsnummer** des gemeinsamen Passworts – enthält kein Passwort und keinen Prüfwert (entsteht erst bei einer Passwortänderung). |

Solange hier noch keine `stammdaten.json` liegt, arbeitet jede Installation mit
ihrer lokalen Besetzung weiter.

## Was hier nie im Klartext gespeichert wird

Sitzungsprotokolle, persönliche Notizen, E-Mail-Adressen und andere Kontaktdaten,
Passwörter, Prüfwerte, Tokens, private Schlüssel, Wiederherstellungsdateien,
Sicherungen oder nicht freigegebene lokale Änderungen. Die Anwendung veröffentlicht
technisch nur Felder einer festen Positivliste und verweigert jede Veröffentlichung,
die eine unverschlüsselte E-Mail-Adresse enthielte.

## Sicherheit

- Jede Veröffentlichung ist signiert; das Zertifikat stammt vom eingebauten
  Signaturschlüssel der Anwendung. Installationen übernehmen nur gültig signierte,
  vollständige Stände mit steigender Versionsnummer.
- Schreiben ist nur aus der Anwendung im geöffneten Bearbeitungsbereich möglich
  (gemeinsames Passwort und eingerichteter Rechner).
- Die Versionshistorie (Git) ist die Veröffentlichungshistorie.
