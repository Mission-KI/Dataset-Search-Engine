# Federated Data Scout

## Executive Summary

### Projektüberblick

Vertrauenswürdige künstliche Intelligenz („KI“) benötigt für effektives Training und präzise Vorhersagen vor allem qualitativ hochwertige Daten. Obwohl täglich enorme Datenmengen entstehen, liegt nur ein Teil davon in verwertbarer, kuratierter Form vor. 

Eine zentrale Herausforderung besteht darin, dass bisher keine Suchfunktion existiert, mit der man über verschiedene Datenräume und -portale hinweg gezielt nach Datensätzen anhand von analytischen Eigenschaften und unabhängig von zahlreichen domänenspezifischen Ontologien suchen kann.

Hier setzt der **Federated Data Scout** an.

### Schlüsselkomponenten

Der Federated Data Scout besteht aus zwei Hauptkomponenten:

- **Dataset Search Engine (daseen)**  
- **Extended Dataset Profile Service (EDPS)**

Der EDPS analysiert Daten möglichst nahe an der Quelle und erstellt ein **Extended Dataset Profile (EDP)** mit standardisierten, maschinenlesbaren Metadaten. Diese Profile sind erweiterbar, z. B. um Beschreibungen, Verarbeitungsstatus oder Lizenzinformationen.

Nur EDPs, die einer offiziellen Schema-Version entsprechen, werden von daseen unterstützt. Nach Freigabe durch den Datenanbieter kann ein EDP veröffentlicht und über daseen gefunden werden – datenraum- und portalübergreifend. Das zugrundeliegende Daten-Asset verbleibt dabei stets beim Anbieter.

---

## 1. Projektarchitektur – Die drei Säulen

### 1.1 Der Bausatz (Softwaremodule)

#### Übersicht der Module

Diagramm: **Asset und EDP Flow**  
*(siehe Abbildung 1 im Umsetzungskonzept ACA-2024-039)*

#### Technische Spezifikationen

Repositories:

- [LP-EDP](https://github.com/Mission-KI/LP-EDP)
- [LP-EDPS](https://github.com/Mission-KI/LP-EDPS)
- [LP-Core](https://github.com/Mission-KI/LP-Core)
- [LP-EDC-Plugin](https://github.com/Mission-KI/LP-EDC-Plugin)
- [LP-Nautilus-Plugin](https://github.com/Mission-KI/LP-Nautilus-Plugin)
- [LP-MDS-Ontology-Mapper](https://github.com/Mission-KI/LP-MDS-Ontology-Mapper)

---

### 1.2 Dokumentation

#### Funktionale Dokumentation

- daseen Hilfe: [https://app.daseen.de/help/](https://app.daseen.de/help/)

#### Technische Dokumentation

- **EDPS API** → Swagger
- **daseen Connector Module** → Swagger
- **EDPS Developer Docs** → Markdown im Repository
- **EDP Schema Beschreibung (menschenlesbar)** → [Release 1.0.0](https://github.com/Mission-KI/LP-EDP/releases/tag/1.0.0)

---

### 1.3 Web-Plattform (Landing Page)

- Landing Page: [https://www.daseen.de](https://www.daseen.de)
- Suchportal: [https://app.daseen.de](https://app.daseen.de)
- daseen Connector API: nur für registrierte Nutzer

---

## 2. Integration und Synergien

### 2.1 Übergreifende Prozesse

- **Tests**: Automatisiert via GitHub Workflows
- **Versionierung**: via Git

### 2.2 Systemarchitektur & Kommunikation

- **EDPS Architektur (EDC)** *(Abbildung 2)*
- **daseen Architektur** *(Abbildung 3: `daseen_architecture.png`)*
- **Asset und EDP Flow** *(Abbildung 1)*

---

## 3. Lösungsstrategie

### 3.1 Technologieentscheidungen

- Details in den Umsetzungskonzepten (EDPS & daseen)

### 3.2 Architekturprinzipien

- Details in den Umsetzungskonzepten (EDPS & daseen)

---

## 4. Systemdesign

### 4.1 Bausteinsicht

- Diagramme: **Asset und EDP Flow**, **EDPS Architektur**, **daseen Architektur**

### 4.2 Laufzeitsicht

- Hauptszenarien & Interaktionsdiagramme: siehe Umsetzungskonzepte
- Performance-Test:

    - 10 parallele EDPS-Instanzen
    - ~14.000 Datenimporte
    - CPU-Spitzen >50%, dennoch stabil
    - Speicherverbrauch stabil bei 17–22 %
    - Grafik: `image-20250415-110802.png`

---

## 5. Qualitätssicherung

### 5.1 Teststrategien

- **Unit-, Integrations- und Systemtests** via GitHub Workflows

### 5.2 Code-Qualität

- Automatisiert geprüft durch CI-Pipelines
- Coding-Standards via GitHub Workflows sichergestellt

---

## 6. Anhänge

### 6.1 Referenzen

#### Externe Standards

- **Ocean Protocol**
  - [Developers](https://docs.oceanprotocol.com/)
  - [Architecture Overview](https://docs.oceanprotocol.com/concepts/architecture/)

- **Eclipse Dataspace Components**
  - [Documentation](https://eclipse-tractusx.github.io/)

---
