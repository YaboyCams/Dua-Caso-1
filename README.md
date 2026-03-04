# DUA Streamliner — Intelligent System for Automated DUA Generation

## Problem

The Single Customs Document (DUA) requires filling in multiple fields based on heterogeneous documents (invoices, packing lists, certificates, bills of lading, insurance policies, permits, etc.).
Today, this process is usually done manually; it is repetitive, error-prone, and heavily dependent on expert knowledge, which can lead to delays, fines, or rejections.

## Project Objective

Design a solution that, given a folder containing documents (Excel, Word, PDF, and scanned images), is able to:

1. Read and extract content from multiple formats (including OCR for scanned files).
2. Semantically identify relevant customs data.
3. Automatically map the data to the official DUA fields.
4. Apply basic consistency validations and flag ambiguities.
5. Generate a pre-filled DUA Word file (.docx) with confidence indicators:

   * Green: high confidence
   * Yellow: medium confidence
   * Red: requires review

## Scope (for now)

This repository contains the **design** of the system (architecture, data models, UX/UI, quality, deployment/CI-CD, security, observability, etc.).
It does not include a functional implementation at this stage.

## Frontend

**1.1 Technology Stack**
## 1.1 Technology stack

## 1.1 Technology stack

* **Application type:** Server-side rendering (SSR) web application
* **Web framework:** React.js `19.2`
* **Web server:** Node.js `21`
* **Coding language:** TypeScript `5.9.3`
* **Unit testing framework:** Jest `30.2.0`
* **Data validation framework:** Zod `4.3.6`
* **Code prettier framework:** Prettier `3.8.1`
* **Code style framework:** ESLint `10.0.2`
* **Integration testing tools:** Playwright `1.58.2`
* **Cloud service:** Azure Cloud Services
* **Hosted services within the cloud service:** Azure App Service
* **Code repositories service:** Azure DevOps Repos
* **Code automation task tool:** Husky `9.1.7`
* **CI/CD pipelines technology:** Azure DevOps Pipelines
* **Environments:** Development, Stage, Production
* **Environment deployments tools:** Azure DevOps Environments
* **Observability framework:** Azure Application Insights SDK
  
Frontend technologies, security technologies, third-party libraries, frameworks, and hosting solutions; all specified with their respective versions.

**1.2 UX / UI Analysis**
Includes the desired usability attributes of the application, a preliminary UX design in the form of wireframes, and evidence from UX testing with real users that validates the preliminary design.

**1.3 Component Design Strategy**
Defines the techniques and principles for frontend component design, how component reusability is achieved, how styles are centralized, as well as branding, internationalization (i18n), and responsiveness strategies.

**1.4 Security**
Technologies, techniques, and classes—along with their respective locations within the project structure—responsible for authentication, authorization, permission management, and session handling.

**1.5 Layered Design**
Design and explanation of the different layers of the frontend application.

**1.6 Design Patterns**
Class design with their respective locations in the project structure, where object-oriented design patterns are applied when necessary, such as for security, UI refresh, notification handling, state storage, API calls, asynchronous operations, session invalidation, event-driven programming, and object creation.

**1.7 Project Scaffold**
A folder within `/src` containing the project scaffold, generated based on the complete specification defined in sections **1.1** through **1.6**.

## Authors

* Camilo Allon Quesada
* José Pablo Chavarro Conde

## Initial References

* What is the DUA: [https://alianza-logistics.com/documento-unico-aduanero-2/](https://alianza-logistics.com/documento-unico-aduanero-2/)
* Official template (CR): [https://www.hacienda.go.cr/docs/Mensaje_TD_DUA-V3-17-12-03-2025.pdf](https://www.hacienda.go.cr/docs/Mensaje_TD_DUA-V3-17-12-03-2025.pdf)
* How to fill out the DUA (general guide): [https://gestionesenlinea.es/formulario-dua-documento-unico-administrativo/](https://gestionesenlinea.es/formulario-dua-documento-unico-administrativo/)
