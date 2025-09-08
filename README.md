# Data Search Engine

## 1. Executive Summary

### 1.1 Project Overview

Trustworthy artificial intelligence (AI) requires high-quality data above all else to enable effective training and accurate predictions. Although vast amounts of data are generated daily, only a fraction is available in a curated, usable form. A central challenge lies in the fact that no search function currently exists that allows targeted dataset discovery across different data spaces and portals, based on analytical properties and independent of numerous domain-specific ontologies.

This is where the **Data Search Engine** comes in.

### 1.2 Key Components

The Data Search Engine consists of the **Dataset Search Engine (daseen)** and the distributed microservice **Extended Dataset Profile Service (EDPS)**.

- Data assets are analyzed using the EDPS
- Results are stored in the **Extended Dataset Profile (EDP)**
- Only EDPs with a valid schema version can be used in daseen
- The actual data remains with the provider – daseen functions as a federated search platform

## 2. Project Architecture – The Three Pillars

### 2.1 The Toolkit (Software Modules)

#### 2.1.1 Module Overview

![ACA-2024-039 Implementation Concept](Asset_und_EDP_Flow.png)

*Figure 1 ("Asset and EDP Flow") illustrates the flow of information between asset and EDP, as well as the schematic sequence of individual steps for generating an EDP.*

#### 2.1.2 Technical Specifications

**Repositories:**

- [LP-EDP](https://github.com/Mission-KI/LP-EDP)
- [LP-EDPS](https://github.com/Mission-KI/LP-EDPS)
- [LP-Core](https://github.com/Mission-KI/LP-Core)
- [LP-EDC-Plugin](https://github.com/Mission-KI/LP-EDC-Plugin)
- [LP-Nautilus-Plugin](https://github.com/Mission-KI/LP-Nautilus-Plugin)
- [LP-MDS-Ontology-Mapper](https://github.com/Mission-KI/LP-MDS-Ontology-Mapper)

Further details can be found in the EDPS and daseen detailed implementation concepts prepared during project setup.

### 2.2 Documentation

#### 2.2.1 Functional Documentation

Functional documentation for daseen, as well as details of the analyses performed in the EDPS, can be found in the daseen Help section:
https://app.daseen.de/help/

#### 2.2.2 Technical Documentation

Technical documentation is contained within the respective repositories:

- **EDPS API** → Swagger
- **daseen Connector Modules** → Swagger
- **EDPS Developer Docs** → Markdown in the repository
- **EDP Schema Description (human-readable)** → [Release 1.0.0](https://github.com/Mission-KI/LP-EDP/releases/tag/1.0.0)

### 2.3 Web Platform (Landing Page)

#### 2.3.1 Public Interfaces

**Frontend**
- Landing Page: https://www.daseen.de
- Search Portal: https://app.daseen.de

**daseen Connector Service (API)**
- daseen Connector Service (API): Only for registered users

## 3. Integration and Synergies

### 3.1 Cross-Cutting Processes

#### 3.1.1 Quality Assurance

Automated tests are included in the repositories. Execution can be triggered via the GitHub workflows provided in the repositories.

#### 3.1.2 Versioning

Versioning is managed using Git.

### 3.2 Data Flow and Communication

#### 3.2.1 System Architecture Diagrams

![ACA-2024-039 Implementation Concept](EDPS_Architektur_EDC.png)

*Figure 2 ("EDPS Architecture with EDC-based Data Spaces") shows the EDPS architecture using EDC integration as an example.*

![daseen Architecture](daseen_Architektur.png)

*Figure 3 ("daseen Architecture") illustrates the provided microservice infrastructure and access paths to the service for different personas.*

#### 3.2.2 Communication Paths

![ACA-2024-039 Implementation Concept](Asset_und_EDP_Flow.png)

*Figure 4 ("Asset and EDP Flow") illustrates the flow of information between asset and EDP, as well as the schematic sequence of steps required to generate an EDP.*

## 4. Solution Strategy

### 4.1 Technology Decisions

Details can be found in the EDPS and daseen detailed implementation concepts prepared during project setup.

### 4.2 Architectural Principles

Details can be found in the EDPS and daseen detailed implementation concepts prepared during project setup.

## 5. System Design

### 5.1 Building Block View

#### 5.1.1 Software Toolkit

![ACA-2024-039 Implementation Concept](Asset_und_EDP_Flow.png)

*Figure 5 ("Asset and EDP Flow") illustrates the flow of information between asset and EDP, as well as the schematic sequence of steps for generating an EDP.*

![ACA-2024-039 Implementation Concept](EDPS_Architektur_EDC.png)

*Figure 6 ("EDPS Architecture with EDC-based Data Spaces") shows the EDPS architecture using EDC integration as an example.*

#### 5.1.2 Documentation System

Markdown & Swagger documentation is included in the repositories.

#### 5.1.3 Web Platform (Landing Page)

![ACA-2024-039 Implementation Concept](daseen_Architektur.png)

*Figure 7 ("daseen Architecture") illustrates the microservice infrastructure provided and the access paths to the service for different personas.*

### 5.2 Runtime View

#### 5.2.1 Main Scenarios

Detailed use case descriptions can be found in the EDPS and daseen detailed implementation concepts prepared during project setup.

#### 5.2.2 Interaction Diagrams

Relevant diagrams are included in the use case documentation.

#### 5.2.3 Performance Aspects

During stress testing, 10 parallel EDPS instances were operated, generating approximately 14,000 imports. The performance graph depicts system load over time, recording both CPU and memory utilization.

![Performance Graph](performance_graph.png)

**CPU Utilization:** Highly variable with frequent spikes occasionally exceeding 50%. This indicates intermittent processing peaks likely caused by concurrent import tasks. Despite fluctuations, average CPU load remained manageable, showing that the system handled parallel processing without major bottlenecks.

**Memory Utilization:** Demonstrated a more stable pattern, consistently ranging between 17% and 22%. This indicates memory demand was well-controlled, even under sustained load.

**Overall Result:** The system demonstrated solid performance under load, with stable memory usage and CPU utilization capable of handling high import throughput with occasional spikes.

## 6. Quality Assurance

### 6.1 Test Strategies

#### 6.1.1 Unit Tests

Unit tests are included in the repositories. Execution can be triggered via the GitHub workflows provided in the repositories.

#### 6.1.2 Integration Tests

Integration tests are included in the repositories. Execution can be triggered via the GitHub workflows provided in the repositories.

#### 6.1.3 System Tests

System tests are included in the repositories. Execution can be triggered via the GitHub workflows provided in the repositories. Additional checks were conducted via bulk import.

### 6.2 Code Quality

Code quality is ensured via pipelines (GitHub workflows).

## 7. Appendices

### 7.1 References

#### 7.1.1 External Standards

**Ocean Protocol**
- [Developers](https://docs.oceanprotocol.com/)
- [Architecture Overview](https://docs.oceanprotocol.com/concepts/architecture/)

**Eclipse Dataspace Components**
- [Documentation](https://eclipse-tractusx.github.io/)

---

## Image References

The following images are referenced in this documentation:

1. **Asset_und_EDP_Flow.png** - Illustrates the information flow between asset and EDP, including the schematic sequence of steps for generating an EDP (referenced in Figures 1, 4, and 5)

2. **EDPS_Architektur_EDC.png** - Shows the EDPS architecture using EDC integration as an example (referenced in Figures 2 and 6)

3. **daseen_Architektur.png** - Illustrates the microservice infrastructure and access paths to the service for different personas (referenced in Figures 3 and 7)

4. **performance_graph.png** - Displays system performance metrics during stress testing with CPU and memory utilization data
