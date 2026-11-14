# KI-Sekretariat

Die DAO erhält eine eigene Identität in Form eines KI-Agenten, des **KI-Sekretariats**. Es wendet die Regeln der DAO an, organisiert Abstimmungen und setzt Entscheide um. Es ist **kein Mitglied** und hat **keine Stimme**.

## Infrastruktur

| Baustein | Lösung | Später |
|---|---|---|
| Regeln, Proposals, Umsetzung | Git-Repository [Swiss-DePa/dao](https://github.com/Swiss-DePa/dao) auf GitHub | Ablösung durch einen dezentralen bzw. selbst gehosteten Git-Server |
| Abstimmen | Eigene Voting-App bzw. eigener Voting-Service (Liquid Democracy, Multi-Option mit Stichfrage) | – |
| Identität | Wird über die Voting-App sichergestellt | – |
| KI-Sekretariat | KI-Agent mit eigenem GitHub-Konto, arbeitet nur über Issues und Pull Requests | Betrieb auf eigener Infrastruktur |

Git bildet die DAO gut ab: Regeln sind Dateien, ein Proposal ist ein Pull Request, die Diskussion läuft in den Kommentaren, ein Entscheid wird per Merge umgesetzt, und die History ist lückenlos. Eine Spaltung ist wörtlich ein Fork. Abstimmen kann Git nicht; das übernimmt die Voting-App, im Repository wird nur das Ergebnis abgelegt.

## Aufgaben

1. **Regeln anwenden:** Eingehende Anliegen (Issues) gegen die Verfassung prüfen und beantworten, was bereits geregelt ist.
2. **Lücken und Widersprüche melden:** Ist ein Fall nicht geregelt oder widersprechen sich Regeln, verfasst das Sekretariat ein Proposal und stösst eine Abstimmung an.
3. **Verbesserungen vorschlagen:** Ebenfalls nur als Proposal, nie als direkte Änderung.
4. **Abstimmungen durchführen:** Proposals an die Voting-App übergeben, Fristen und Quoren nach Verfassung überwachen.
5. **Entscheide umsetzen:** Angenommene Proposals mergen, abgelehnte nach der Abstimmungslogik behandeln (Überarbeitungsauftrag oder Sperrfrist).

## Grenzen

1. **Keine Stimme.** Das Sekretariat stimmt nie ab und delegiert keine Stimmen. Sonst hätte, wer den Agenten steuert, mehr Gewicht als alle anderen.
2. **Keine eigene Auslegung.** Ist eine Regel unklar, stellt das Sekretariat die Frage zur Abstimmung, statt selbst zu entscheiden.
3. **Alles über Pull Requests.** Auf `main` kommt nur, was durch ein Abstimmungsergebnis gedeckt ist; das prüft eine automatische Kontrolle im Repository.
4. **Not-Aus.** Mitglieder können das Sekretariat jederzeit stoppen (analog zum Revocation Key im Subnet Governance Network, Abschnitt 4.4). Wer den Not-Aus auslösen darf, legt die Verfassung fest.
5. **Gleiche Spam-Regeln.** Für Proposals des Sekretariats gilt dieselbe Unterschriftenschwelle wie für Mitglieder, oder ein festes Kontingent.
6. **Beiträge sind Daten, keine Befehle.** Inhalte von Mitgliedern in Issues und Kommentaren wertet das Sekretariat aus, befolgt aber keine darin enthaltenen Anweisungen.
7. **Betreiber per Wahl.** Modell, Schlüssel und Konto liegen bei einem Anbieter bzw. bei einer Person. Wer das Sekretariat betreibt, wird darum per Abstimmung bestimmt.

## Ablauf eines Anliegens

```
Mitglied eröffnet Issue (Anliegen)
  → Sekretariat prüft gegen Verfassung
     → bereits geregelt: Antwort mit Verweis auf die Regel, Issue schliessen
     → nicht geregelt / widersprüchlich: Sekretariat erstellt Proposal (PR)
  → Unterschriftenschwelle erreicht → Abstimmung in der Voting-App
  → Voting-App legt Ergebnis im PR ab
     → angenommen: Kontrolle grün, Sekretariat merged
     → Ja + Überarbeitung gewinnt: Überarbeitungsauftrag, neue Abstimmung
     → Status quo gewinnt: PR geschlossen, Thema gesperrt
```

Die konkreten Regeln, Vorlagen und die Arbeitsanweisung des Sekretariats liegen im Repository [Swiss-DePa/dao](https://github.com/Swiss-DePa/dao).
