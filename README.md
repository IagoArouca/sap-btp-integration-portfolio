# sap-btp-integration-portfolio# 🚀 SAP BTP Integration Portfolio & Architecture

[![SAP BTP](https://img.shields.io/badge/SAP%20BTP-Integration%20Suite-008FD3?style=for-the-badge&logo=sap)](https://cloudplatform.sap.com)


Este repositório é dedicado ao **desenho, documentação e implementação de cenários complexos de integração no SAP BTP (Integration Suite / CPI)**. O objetivo principal é construir soluções de arquitetura voltadas a desafios reais de mercado, conectando ecossistemas SAP (S/4HANA, HDSF, etc.) e sistemas de terceiros através de padrões consolidados de mensageria, conectividade REST/OData e governança de dados.

---

## 📐 Padrões de Arquitetura & Tecnologias
* **Integration Patterns:** Event-Driven Architecture (EDA), Asynchronous Inbound/Outbound, Content-Based Router, Message Transformation, Feedback Loop (Cross-Reference Update).
* **Protocols & Formats:** REST, OData v2/v4, FHIR (Fast Healthcare Interoperability Resources), HTTPS, XML, JSON.
* **SAP BTP Components:** SAP Integration Suite (CPI), Cloud Connector, Security Material, Event Mesh.

---

## 📚 Tabela de Projetos & Cenários de Integração

| # | Projeto / Cenário de Integração | Tecnologias & Protocolos | Foco da Solução | Link da Documentação |
|---|---|---|---|---|
| **01** | Sincronização de Pacientes (FHIR) para S/4HANA Business Partner | SAP CPI, REST/FHIR, OData, SAP S/4HANA, HDSF | Orquestração com roteamento condicional, transformação de modelo de saúde para ERP e atualização de ID secundário (Feedback Loop). | [Ver Projeto 01](./01-fhir-to-s4hana-patient-replication/) |
| **02** | *Em breve* | *--* | *Novo padrão de integração em desenvolvimento.* | `--` |

---

## 🗂️ Estrutura do Repositório

```text
.
├── README.md                                  <-- Visão geral do portfólio
├── images/                                    <-- Repositório central de diagramas e arquiteturas
│   └── integracao-fhir-to-s4hana.png
│
└── 01-fhir-to-s4hana-patient-replication/     <-- Cenário 01: FHIR to S/4HANA BP
    └── README.md                              <-- Detalhamento técnico do iFlow
