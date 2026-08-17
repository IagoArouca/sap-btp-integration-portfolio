# 🏥 SAP BTP Integration Suite — Replicate Patients (FHIR) to SAP S/4HANA Business Partner

![SAP BTP](https://img.shields.io/badge/SAP%20BTP-Integration%20Suite-008FD3?style=flat&logo=sap)
![Architecture](https://img.shields.io/badge/Architecture-Event--Driven%20%7C%20REST%20%7C%20OData-green)

## 📌 Visão Geral da Solução
Este repositório contém a arquitetura e implementação de uma integração desenvolvida no **SAP Integration Suite (CPI)**. O objetivo é sincronizar automaticamente cadastros de pacientes vindos de um sistema de saúde compatível com o padrão **FHIR** (*SAP Health Data Services for FHIR*) com o **SAP S/4HANA**, criando o respectivo **Business Partner (BP)** e devolvendo a referência cruzada de IDs.

---

## 🏢 Contexto de Negócio
Em grandes redes hospitalares, laboratórios e operadoras de saúde, o atendimento ao paciente ocorre em sistemas clínicos especializados (HIS/LIS). No entanto, para fins financeiros, de faturamento, faturamento de convênios e suprimentos, o cadastro do paciente precisa existir no **SAP S/4HANA** como um **Business Partner**.

### Benefícios da Integração:
* **Eliminação de Duplicidade:** Evita o cadastro manual do paciente no ERP.
* **Consistência Fiscal e Financeira:** Vincula a ficha médica do paciente diretamente às transações do S/4HANA.
* **Sincronização Bi-direcional:** Mantém o ID do Business Partner gravado na ficha do paciente no sistema de saúde.

---

![Arquitetura do iFlow](./images/integracao-fhir-to-s4hana.png)

## 📐 Arquitetura do iFlow (Pipeline)

```text
[Evento HTTPS]
      │
      ▼
[Extract Patient ID]
      │
      ▼
[Check Interaction] ────(Default / Não-Criar)────► [End Event]
      │
 (Patient Create)
      │
      ▼
[GET Patient Data (HDSF)]
      │
      ▼
[Set BP Grouping & Payload]
      │
      ▼
[POST Business Partner (S/4HANA OData)]
      │
      ▼
[Extract BP ID]
      │
      ▼
[POST Patient Update (HDSF - Feedback Loop)]
      │
      ▼
  [End]


