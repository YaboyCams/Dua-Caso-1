# DUA Streamliner — Intelligent System for Automated DUA Generation

## Problem

The Single Customs Document (DUA) requires filling in multiple fields based on heterogeneous documents (invoices, packing lists, certificates, bills of lading, insurance policies, permits, etc.).
Today, this process is usually done manually; it is repetitive, error-prone, and heavily dependent on expert knowledge, which can lead to delays, fines, or rejections.

---

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

---

## Scope (for now)

This repository contains the **design** of the system (architecture, data models, UX/UI, quality, deployment/CI-CD, security, observability, etc.).
It does not include a functional implementation at this stage.

---

## Frontend

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

---

## **1.2 UX / UI Analysis**


## Core Business Process


### Login

1. The user provides their login credentials and one-time authentication token.
2. The system validates the credentials with the authentication provider.
3. If the authentication fails, the system informs the user that the credentials are invalid.
4. If the authentication succeeds, the user session is created and the system allows access to the application.

---

### Configure the Generator

1. The user selects a folder path that contains the source documents.
2. The system scans the folder and identifies compatible documents such as Excel, Word, PDF, and images.
3. The user selects the official DUA template that will be used to generate the final document.
4. The system validates that the selected template matches the expected DUA structure.
5. Once configuration is confirmed, the system prepares the document processing pipeline.

---

### Monitor Processing Progress

1. The user starts the automated DUA generation process.
2. The system begins reading and interpreting all documents in the selected folder.
3. The system performs document parsing, semantic extraction, and validation of the detected information.
4. The system continuously updates the progress status of the process.
5. The user can observe the progress until the generation process is completed.

---

### Obtain Result / Export

1. After the process finishes, the system generates a completed DUA document based on the official template.
2. The system marks each extracted field with a confidence level.
3. The user reviews the generated information and verifies the extracted data.
4. The user exports the generated DUA document for external usage.

---

### Logout

1. The user ends the session.
2. The system invalidates the active authentication token.
3. The user session is terminated and access to the system is closed.

---

## Wireframes

## Login Screen

**Description**

The user authenticates using the Microsoft authentication service before accessing the system.

**Image**

<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/58455e4e-494b-43a1-b705-4856f480ccf8" />

---

## Folder Selection Screen

**Description**

The user provides the folder path that contains all source documents required to generate the DUA.

**Image**

<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/7d39f418-dc41-485b-bfff-10d8a04c970b" />

---

## DUA Template Selection Screen

**Description**

The user selects the official DUA template that will be used as the structure for the generated document.

**Image**

<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/e1509220-0f48-4622-9e9a-90c8c99e652e" />

---

## Processing Monitoring Screen

**Description**

The user observes the progress of the document processing pipeline while the system reads, analyzes, and extracts the required information from the source files.

**Image**

<img width="1408" height="768" alt="image" src="https://github.com/user-attachments/assets/97659bf0-9825-47e8-9567-645212063026" />

---

## Generated DUA Result Screen

**Description**

The user reviews the generated DUA document and verifies the extracted information before exporting the final document.

**Image**

<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/b1e91a7f-1011-4561-ac0f-e657fedd41e4" />

---

----------------------------------------------------------------------
## Testing Results

| Screen | Avg Duration | Success Rate | Drop-off Rate | Misclick Rate | Responses | Ease of Task (Avg) |
|------|------|------|------|------|------|------|
| Login Screen | 14.6s | 100% | 0% | 66.7% | 3 | 8.3 |
| Folder Selection (Provide Path) | 4.8s | 100% | 0% | 50.0% | 3 | 9 |
| Folder Selection (Scan & Detect Files) | 3.0s | 100% | 0% | 40.0% | 3 | 9 |
| Folder Selection (Confirm Folder) | 5.7s | 100% | 0% | 36.4% | 3 | 9 |
| DUA Template Selection | 5.4s | 100% | 0% | 62.5% | 3 | 9.3 |
| Processing Monitoring | 4.9s | 100% | 0% | 0% | 3 | 10 |
| Generated DUA Result | 11.0s | 100% | 0% | 81.3% | 3 | 9 |


----------------------------------------------------------------------
## 1.3 Component Design Strategy**
Defines the techniques and principles for frontend component design, how component reusability is achieved, how styles are centralized, as well as branding, internationalization (i18n), and responsiveness strategies.

## 1.4 Security**
Technologies, techniques, and classes—along with their respective locations within the project structure—responsible for authentication, authorization, permission management, and session handling.

## 1.5 Layered Design**
Design and explanation of the different layers of the frontend application.

## 1.6 Design Patterns**
Class design with their respective locations in the project structure, where object-oriented design patterns are applied when necessary, such as for security, UI refresh, notification handling, state storage, API calls, asynchronous operations, session invalidation, event-driven programming, and object creation.

## 1.7 Project Scaffold**
A folder within `/src` containing the project scaffold, generated based on the complete specification defined in sections **1.1** through **1.6**.

## Authors

* Camilo Allon Quesada
* Jose Pablo Chavarro Conde

## Initial References

* What is the DUA: [https://alianza-logistics.com/documento-unico-aduanero-2/](https://alianza-logistics.com/documento-unico-aduanero-2/)
* Official template (CR): [https://www.hacienda.go.cr/docs/Mensaje_TD_DUA-V3-17-12-03-2025.pdf](https://www.hacienda.go.cr/docs/Mensaje_TD_DUA-V3-17-12-03-2025.pdf)
* How to fill out the DUA (general guide): [https://gestionesenlinea.es/formulario-dua-documento-unico-administrativo/](https://gestionesenlinea.es/formulario-dua-documento-unico-administrativo/)
