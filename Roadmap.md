# Roadmap

Die Roadmap hat bewusst kein Startdatum. Alle Zeitangaben sind relativ zum Start (**T0**), z.B. «T+3 Monate» = drei Monate nach Start. Die Dauern sind Vorschläge und werden angepasst, sobald klar ist, wie viele Leute mitarbeiten.

## Übersicht

| Phase | Zeitraum | Ziel | Meilenstein |
|---|---|---|---|
| 0 – Fundament | T0 bis T+1 Monat | Arbeitsfähige Community | Landing Area und Working Groups stehen |
| 1 – Regeln | T+1 bis T+3 Monate | Spielregeln der Partei festlegen | Entwurf Constitution und Voting-System |
| 2 – Auftritt | T+3 bis T+6 Monate | Sichtbar werden, Mitglieder gewinnen | Website online, erste Abstimmung via Proposal |
| 3 – DAO | T+6 bis T+12 Monate | Ende der Aufbauphase, Übergang zur DAO | Verein gegründet, Swiss DePa läuft als DAO |
| 4 – Politische Wirkung | T+12 bis T+24 Monate | In der Politik mitwirken | Erste Kandidatur bzw. erste Initiative/Referendum |
| 5 – Technisches System | ab T+24 Monate | Eigene dezentrale Infrastruktur | Proof of Concept Subnet Governance Network |

## Phase 0 – Fundament (T0 bis T+1 Monat)

- **Landing Area** auf Discord: Rules festlegen, automatisierte Moderation einrichten
- **Grundprinzip** festhalten: Discord als internes Kommunikations-Tool, DAO als zukünftiges Ideal
- **Working Groups** bilden (Prinzip, Identitätsfeststellung, Strukturierung, PR, Community Building)
- **Leads** pro Department bestimmen; Wahl nach Kollegialitätsprinzip, Amtsdauer begrenzt (Trial Phase)
- **Dokumentation** nur noch in den Repos; OneNote-Notizbuch archivieren

## Phase 1 – Regeln (T+1 bis T+3 Monate)

Arbeitet die [Kategorien](Kategorien.md) aus.

- **Voting System**
  - Kriterien festlegen
  - Delegiersystem (Liquid Democracy) definieren, siehe [Funktionsweise](README.md#funktionsweise-von-swiss-depa)
  - Abstimmungslogik ausformulieren. **Entschieden:** Multi-Option-Logik mit Stichfrage gemäss [Subnet Governance Network](https://github.com/Swiss-DePa/technical-system/blob/main/Subnet%20Governance%20Network.md), Abschnitt 4.2 (Typ 1: Ja / Nein mit Überarbeitung / Nein mit Status quo; Typ 2: konkurrierende Vorschläge mit Stichfrage)
- **Identitätsvalidierung**: Tag System, wer darf was voten, wo schreiben, was lesen
- **Anerkennungs-System**: Reputation, Trial Phase, Vertrauen als Grundsatz
- **Constitution** (Entwurf) und Regeln zur Spaltung bzw. Dachorganisation
- **DAO-Plattform neu wählen**: Soonaverse wurde 2024 eingestellt (siehe [Hinweis im Konzept](README.md#dao)). Anforderungen aus den Kategorien ableiten, Alternativen vergleichen, entscheiden

## Phase 2 – Auftritt (T+3 bis T+6 Monate)

- **Website**: Domain, Inhalte, Verlinkungen (siehe [Puplic-Relation](https://github.com/Swiss-DePa/Puplic-Relation))
- **Social Media Management**: festlegen, wer was wie betreut
- **Kommunikation nach Aussen**, Grafik/Design
- **Community Building** und **Onboarding** neuer Mitglieder (Discord-Vorstellung, Beitritt auf der DAO-Plattform)
- **Erste Proposals** als Testlauf für das Voting System

## Phase 3 – DAO (T+6 bis T+12 Monate)

- **Übergang zur DAO**: Ende der Aufbauphase, Entscheidungen laufen über Proposals und Liquid-Democracy-Voting
- **Rollen und Aufgaben** dezentralisieren; Leads der Aufbauphase durch gewählte Rollen ablösen
- **Verein gründen** als Rechtsträger (Statuten, Gründungsversammlung); die DAO regelt die internen Entscheide
- **Finanzierung** klären: Community Token, NFT oder andere Modelle
- **Identität**: IOTA-DID-Integration evaluieren (siehe [Identity-Verification](https://github.com/Swiss-DePa/Identity-Verification))

## Phase 4 – Politische Wirkung (T+12 bis T+24 Monate)

- **Repräsentanten**: Ratskandidaten bestimmen, Namen auf Liste
- **Initiativen / Referenden**: Initiierung, Gründung, Finanzierung
- **Dachorganisation**, falls sich Gruppen abspalten
- Kandidaturen, Listen und Initiativen laufen über den Verein (siehe Phase 3), da eine DAO allein in der Schweiz kein Rechtsträger ist.

## Phase 5 – Technisches System (ab T+24 Monate)

Langfristig, unabhängig von den Phasen 0 bis 4. Grundlage sind die «Next Steps» im [Subnet Governance Network](https://github.com/Swiss-DePa/technical-system/blob/main/Subnet%20Governance%20Network.md) (Abschnitt 9).

- Spezifikation ausarbeiten: Bridge-Sicherheit, Cluster-Governance, ZK-Identität, Voting-Protokoll
- Proof of Concept: ein einzelnes Subnet plus Base-Protocol-Registry
- Kontakt zur Schweizer E-Voting-Forschung (Post, ETH Zürich, Uni Bern)
