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

## [1.1 Technology stack](src/)

### Technology Stack

* **Application type:** Server-side rendering (SSR) web application
* **Web framework:** React.js `19.2`
* **Web server:** Node.js `21`
* **Coding language:** TypeScript `5.9.3`
* **State management:** Redux `5.0.1`
* **Unit testing framework:** Jest `30.2.0`
* **Integration testing tools:** Playwright `1.58.2`
* **Data validation framework:** Zod `4.3.6`
* **Code formatting framework:** Prettier `3.8.1`
* **Code style framework:** ESLint `10.0.2`
* **Code automation tasks:** Husky `9.1.7`
* **Cloud service:** Azure Cloud Services
* **Hosted services within the cloud:** Azure App Service
* **Code repository service:** Azure DevOps Repos
* **CI/CD pipelines technology:** Azure DevOps Pipelines
* **Environments:** Development, Stage, Production
* **Environment deployment tools:** Azure DevOps Environments
* **Observability framework:** Azure Application Insights SDK

---

## **[1.2 UX / UI Analysis](src/app)**


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

## Heatmaps for misclicks and drop-offs:

### Login Screen
<img width="1054" height="561" alt="image" src="https://github.com/user-attachments/assets/f9fbc9da-3d1c-409e-94d3-89e6ba9a6e44" />

### Folder Selection (Provide Path)
<img width="1068" height="580" alt="image" src="https://github.com/user-attachments/assets/9e4e8d35-c6e4-47f3-bd9c-fa40d8ae1ada" />

### Folder Selection (Scan & Detect Files)
<img width="886" height="567" alt="image" src="https://github.com/user-attachments/assets/06e31b75-fecd-4508-8332-61684484faea" />

### Folder Selection (Confirm Folder)
<img width="1112" height="614" alt="image" src="https://github.com/user-attachments/assets/fcca9534-5564-4398-9159-afe625ae45be" />

### DUA Template Selection
<img width="1117" height="620" alt="image" src="https://github.com/user-attachments/assets/4ff3dcd5-5d9d-40e0-a4f5-546a045698ae" />

### Processing Monitoring
<img width="1114" height="618" alt="image" src="https://github.com/user-attachments/assets/5003cd4a-0df2-4476-b7c0-2ec70d11e7e2" />

### Generated DUA Result
<img width="1107" height="612" alt="image" src="https://github.com/user-attachments/assets/dcfe437a-8b18-442e-8902-81559801fbb6" />

## Interviewees 

   - Felipe Bianchi Piedra // Lawyer
     
   - Ana María Chavarro Conde // Performance Analyst // https://estudianteccr-my.sharepoint.com/:v:/g/personal/jchavarro_estudiantec_cr/IQBCCIPmRKNUQItT_mE6pBeGAdeeQ2xYX6oNUpMMDdNW7dU?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=hNWbe5
     
   - Francisco Javier Chavarro Conde // Developer // https://estudianteccr-my.sharepoint.com/:v:/g/personal/jchavarro_estudiantec_cr/IQAKhMaJHWX9RIm7gFHuGdD0AZhXRi9ffmbFsEAiWdBOkbo?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=eZzLqk


----------------------------------------------------------------------
## **[1.3 Component Design Strategy](src/components)**

### Component Design Strategy

**Name of the strategy:**
Atomic Design

**Reutilization by:**
Components are organized hierarchically as **atoms, molecules, organisms, templates, and pages**.
Basic elements are created once and reused across the application to ensure consistency and reduce duplication.

**Internationalization by:**
Internationalization is implemented using **i18next**, with centralized translation files in [`src/i18n/`](src/i18n/).
Components reference translation keys instead of hardcoded text.

**Responsiveness by:**
Responsiveness is implemented using **TailwindCSS responsive utilities**, allowing layouts to adapt to different screen sizes such as desktop, tablet, and mobile devices.

### Visual Component Architecture

| Level | Folder | Key Files |
|---|---|---|
| Atoms | [`src/components/atoms/`](src/components/atoms/) | [`Button/`](src/components/atoms/Button/Button.tsx) · [`Input/`](src/components/atoms/Input/Input.tsx) · [`Label/`](src/components/atoms/Label/Label.tsx) · [`ConfidenceIndicator/`](src/components/atoms/ConfidenceIndicator/ConfidenceIndicator.tsx) |
| Molecules | [`src/components/molecules/`](src/components/molecules/) | [`FileUploader/`](src/components/molecules/FileUploader/FileUploader.tsx) · [`FormField/`](src/components/molecules/FormField/FormField.tsx) |
| Organisms | [`src/components/organisms/`](src/components/organisms/) | [`DuaForm/`](src/components/organisms/DuaForm/DuaForm.tsx) · [`Navbar/`](src/components/organisms/Navbar/Navbar.tsx) |
| Templates | [`src/components/templates/`](src/components/templates/) | [`MainLayout/`](src/components/templates/MainLayout/MainLayout.tsx) |
| Pages | [`src/components/pages/`](src/components/pages/) | [`pages.css/`](src/components/pages/pages.css) |

## [**1.4 Security**](src/auth)

Technologies, techniques, and classes—along with their respective locations within the project structure—responsible for authentication, authorization, permission management, and session handling.

### Authentication Configuration

| File | Description |
|---|---|
| [`src/auth/authConfig.ts`](src/auth/authConfig.ts) | MSAL configuration: `clientId`, `authority`, `redirectUri`, OAuth scopes for Dua and Users APIs |
| [`src/auth/roles.ts`](src/auth/roles.ts) | `RoleDefinitions` map — associates each `RoleType` with its allowed `PermissionCodes` |
| [`src/auth/permissions.ts`](src/auth/permissions.ts) | `hasPermission()` and `getPermissionsForRole()` — runtime RBAC enforcement helpers |
| [`src/auth/index.ts`](src/auth/index.ts) | Barrel export for the auth layer |

## Multi-Factor Authentication (MFA)
MFA supported: Yes

Supported MFA methods:
- Microsoft Authenticator App
- Time-based OTP (TOTP)
- SMS One-Time Password
- Voice Call OTP

## Single Sign-On (SSO)

SSO supported: Yes
Users authenticate using their Microsoft Entra organizational accounts, allowing centralized identity management and security policy enforcement.

# Social Authentication

| Provider | Supported |
|---|---|
| Google Authentication | No |
| Facebook Authentication | No |

**Reason**

The system processes sensitive operational documents.  
Authentication is restricted to **corporate identity providers** to ensure governance, traceability, and security compliance.


## RBAC Roles

| Role Name | Description |
|---|---|
| `SYS_ADMIN` | Full system administrator with access to security, configuration, roles, permissions, and observability features. |
| `CUSTOMS_SPECIALIST` | Main operational user responsible for configuring the generation process, starting processing, reviewing extracted data, and exporting the generated DUA. |
| `CUSTOMS_REVIEWER` | Business reviewer responsible for validating extracted information, correcting ambiguous fields, and approving generated DUA documents. |
| `AUDITOR` | Read-only user responsible for auditing, traceability, and historical review of system activity and generated DUA processes. |
| `SUPPORT_OPERATOR` | Technical support user with access to monitoring and diagnostics, but without permission to approve or export sensitive business documents. |

---

## Permissions by Role

### `SYS_ADMIN`

| Permission Code | Description |
|---|---|
| `AUTH_LOGIN` | Login to the system |
| `AUTH_LOGOUT` | Logout from the system |
| `DASHBOARD_VIEW` | View the main dashboard |
| `FOLDER_SELECT` | Select the source document folder |
| `DOCUMENT_SCAN_START` | Start document scanning |
| `DOCUMENT_LIST_VIEW` | View detected documents |
| `DUA_TEMPLATE_SELECT` | Select the official DUA template |
| `PROCESS_START` | Start the automated generation process |
| `PROCESS_MONITOR` | Monitor processing progress |
| `PROCESS_CANCEL` | Cancel an active process |
| `DUA_RESULT_VIEW` | View the generated DUA |
| `DUA_RESULT_EDIT` | Edit extracted DUA fields |
| `DUA_RESULT_APPROVE` | Approve the generated DUA |
| `DUA_RESULT_EXPORT` | Export the final DUA document |
| `HISTORY_VIEW` | View processing history |
| `AUDIT_LOG_VIEW` | View audit logs |
| `USER_ADMIN` | Manage users |
| `ROLE_ADMIN` | Manage roles and permissions |
| `SYSTEM_CONFIG` | Manage system configuration |
| `OBSERVABILITY_VIEW` | View monitoring and observability data |

### `CUSTOMS_SPECIALIST`

| Permission Code | Description |
|---|---|
| `AUTH_LOGIN` | Login to the system |
| `AUTH_LOGOUT` | Logout from the system |
| `DASHBOARD_VIEW` | View the main dashboard |
| `FOLDER_SELECT` | Select the source document folder |
| `DOCUMENT_SCAN_START` | Start document scanning |
| `DOCUMENT_LIST_VIEW` | View detected documents |
| `DUA_TEMPLATE_SELECT` | Select the official DUA template |
| `PROCESS_START` | Start the automated generation process |
| `PROCESS_MONITOR` | Monitor processing progress |
| `DUA_RESULT_VIEW` | View the generated DUA |
| `DUA_RESULT_EDIT` | Edit extracted DUA fields |
| `DUA_RESULT_EXPORT` | Export the final DUA document |
| `HISTORY_VIEW` | View processing history |

### `CUSTOMS_REVIEWER`

| Permission Code | Description |
|---|---|
| `AUTH_LOGIN` | Login to the system |
| `AUTH_LOGOUT` | Logout from the system |
| `DASHBOARD_VIEW` | View the main dashboard |
| `DOCUMENT_LIST_VIEW` | View detected documents |
| `PROCESS_MONITOR` | Monitor processing progress |
| `DUA_RESULT_VIEW` | View the generated DUA |
| `DUA_RESULT_EDIT` | Edit extracted DUA fields |
| `DUA_RESULT_APPROVE` | Approve the generated DUA |
| `DUA_RESULT_EXPORT` | Export the final DUA document |
| `HISTORY_VIEW` | View processing history |
| `AUDIT_LOG_VIEW` | View audit logs |

### `AUDITOR`

| Permission Code | Description |
|---|---|
| `AUTH_LOGIN` | Login to the system |
| `AUTH_LOGOUT` | Logout from the system |
| `DASHBOARD_VIEW` | View the main dashboard |
| `DOCUMENT_LIST_VIEW` | View detected documents |
| `PROCESS_MONITOR` | Monitor processing progress |
| `DUA_RESULT_VIEW` | View the generated DUA |
| `HISTORY_VIEW` | View processing history |
| `AUDIT_LOG_VIEW` | View audit logs |

### `SUPPORT_OPERATOR`

| Permission Code | Description |
|---|---|
| `AUTH_LOGIN` | Login to the system |
| `AUTH_LOGOUT` | Logout from the system |
| `DASHBOARD_VIEW` | View the main dashboard |
| `PROCESS_MONITOR` | Monitor processing progress |
| `HISTORY_VIEW` | View processing history |
| `OBSERVABILITY_VIEW` | View monitoring and observability data |

---

## ACL

**ACL supported:** Yes

**ACL service name:** `ACLService`

**Purpose of ACL:**
- Restrict access to specific DUA processes or generated documents
- Allow only the owner or assigned reviewer to modify a record
- Enforce read-only access for auditors
- Prevent support users from accessing sensitive export actions

---

## PBAC Policies

**PBAC supported:** Yes

**Policy service name:** `PolicyService`

| Policy Code | Policy Name | Definition |
|---|---|---|
| `POL-001` | `ExportOnlyWhenReviewed` | A DUA can only be exported after the process is completed and the document has been reviewed or approved by an authorized role. |
| `POL-002` | `EditOnlyBeforeApproval` | DUA fields can only be edited before the document is approved. |
| `POL-003` | `OwnerOrReviewerAccess` | Only the process owner, an assigned reviewer, or a system administrator can edit a DUA process. |
| `POL-004` | `AuditReadOnly` | Users with the `AUDITOR` role have read-only access to documents, history, and audit records. |
| `POL-005` | `SupportNoSensitiveExport` | Support users cannot approve, export, or modify business-sensitive DUA content. |

---

## Secure Store

**Secure store service:** `Azure Key Vault`

**Used for storing:**
- Environment variables
- API keys
- OAuth client secrets
- Database credentials
- Encryption keys
- Other sensitive application configuration

---

## Authenticator Server Name

**Authenticator server name:** `Microsoft Entra ID`


MFA management:
Handled by Microsoft Entra ID security policies.

## **[1.5 Layered Design](src/)**

The frontend performs **SSR (Server-Side Rendering)** using **React.js and Node.js** hosted in **Azure App Service**.

If there is no authenticated session, the **Authentication Layer** is invoked.

If authentication succeeds, the requested resource is rendered through the **Components Layer**.

The **Components Layer** follows **Atomic Design** principles (atoms, molecules, organisms, templates, and pages).

Inside components, a **Hooks Layer** connects component actions with the **Services Layer**.

The **Services Layer** contains the business operations of the application such as:

* document processing requests
* DUA generation orchestration
* export operations

Services may require access to the **Utils**, **ApiClients**, and **Settings** layers.

The **ApiClients Layer** contains classes responsible for calling external APIs such as document processing or backend services.

The **Settings Layer** reads environment variables and configuration values during runtime, including credentials stored in **Azure Key Vault**.

ApiClients retrieve API URLs, credentials, and tokens from the **Settings Layer**.

All ApiClient requests and responses are represented using classes in the **Models Layer**, which are validated using **Zod** in the **DataValidation Layer**.

The **State Management Layer** manages shared frontend state using **Redux**.

All layers may access the following shared layers:

* Models
* Utils
* State Management

The **NotificationService Layer** allows components and services to subscribe to asynchronous events.

Long-running processes such as document analysis return results through **callback notifications** handled by the NotificationService.

The **Logs Layer** records system events and sends telemetry data to **Azure Application Insights**.

The **ExceptionHandling Layer** provides centralized error management shared across all layers.

## Architecture Overview

```
          +----------------------+
          |      User Browser    |
          +----------+-----------+
                     |
                     v
          +----------------------+
          |    Azure App Service |
          |  NodeJS + React SSR  |
          +----------+-----------+
                     |
           SSR Request Handling
                     |
              Authentication
                     |
          +----------------------+
          |   Components Layer   |
          | Atomic Design UI     |
          | Atoms → Pages        |
          +----------+-----------+
                     |
                   Hooks
                     |
               Services Layer
                     |
   +----------------+----------------+
   |                |                |
 Utils          ApiClients        Settings
                                      |
                              Azure Key Vault
                                      |
                               Secrets / Config
ApiClients → External APIs External APIs → Notification Service (Callbacks)

Shared Layers:
Models
Zod Validation
Redux State Management
Exception Handling
Logs → Azure Application Insights

CI/CD:
Azure DevOps Repo → Pipelines → Dev / Stage / Prod → Azure App Service
```

---

## **[1.6 Design Patterns](src/documentProcessors)**

Use **Builder Pattern** and **Strategy Pattern** to create different document processors for formats such as **.docx, .xlsx, .pdf, .jpg, .png**.

Notification subscriptions are implemented through the **Observer Pattern** using the **NotificationService**, allowing components and services to receive processing status updates.

Use the **Adapter Pattern** to map extracted data into the official **DUA Word template**, using **FormatAdapters** and concrete formats such as **Paragraph, Table, Label, Amount**.

Use the **Factory Pattern** to instantiate the correct document processor depending on the detected file type.

Use **Singleton Pattern** for shared services:

* ExceptionHandling
* Utils
* StateManagement (Redux)
* ApiClients
* Settings classes

Use the **Pub/Sub pattern** through **Redux State Management** to propagate application state updates across components.

### Pattern Implementation

| Pattern | File(s) |
|---|---|
| Builder + Factory | [`src/documentProcessors/DocumentProcessorBuilder.ts`](src/documentProcessors/DocumentProcessorBuilder.ts) |
| Strategy — Interface | [`src/documentProcessors/strategies/IDocumentStrategy.ts`](src/documentProcessors/strategies/IDocumentStrategy.ts) |
| Strategy — Word | [`src/documentProcessors/strategies/WordStrategy.ts`](src/documentProcessors/strategies/WordStrategy.ts) |
| Strategy — Excel | [`src/documentProcessors/strategies/ExcelStrategy.ts`](src/documentProcessors/strategies/ExcelStrategy.ts) |
| Strategy — PDF | [`src/documentProcessors/strategies/PdfStrategy.ts`](src/documentProcessors/strategies/PdfStrategy.ts) |
| Strategy — Image | [`src/documentProcessors/strategies/ImageStrategy.ts`](src/documentProcessors/strategies/ImageStrategy.ts) |
| Adapter — Interface | [`src/documentProcessors/formatAdapters/IFormatAdapter.ts`](src/documentProcessors/formatAdapters/IFormatAdapter.ts) |
| Adapter — Paragraph | [`src/documentProcessors/formatAdapters/ParagraphAdapter.ts`](src/documentProcessors/formatAdapters/ParagraphAdapter.ts) |
| Adapter — Bullets | [`src/documentProcessors/formatAdapters/BulletsAdapter.ts`](src/documentProcessors/formatAdapters/BulletsAdapter.ts) |
| Adapter — Table | [`src/documentProcessors/formatAdapters/TableAdapter.ts`](src/documentProcessors/formatAdapters/TableAdapter.ts) |
| Adapter — Label | [`src/documentProcessors/formatAdapters/LabelAdapter.ts`](src/documentProcessors/formatAdapters/LabelAdapter.ts) |
| Adapter — Amount | [`src/documentProcessors/formatAdapters/AmountAdapter.ts`](src/documentProcessors/formatAdapters/AmountAdapter.ts) |
| Observer (Pub/Sub) | [`src/notificationService/NotificationService.ts`](src/notificationService/NotificationService.ts) |
| Singleton — State | [`src/state/store.ts`](src/state/store.ts) · [`src/state/StoreProvider.tsx`](src/state/StoreProvider.tsx) |
| Singleton — Settings | [`src/settings/Settings.ts`](src/settings/Settings.ts) |
| Singleton — Logger | [`src/logs/Logger.ts`](src/logs/Logger.ts) |
| Singleton — ExceptionHandler | [`src/exceptionHandling/ExceptionHandler.ts`](src/exceptionHandling/ExceptionHandler.ts) |

---

## [1.7 `/src` Project Scaffold](src/)

### `/src` folder structure

```
src/
├── app/                            → SSR routes and pages
│   ├── layout.tsx
│   ├── page.tsx
│   ├── globals.css
│   ├── login/
│   │   └── page.tsx
│   ├── dashboard/
│   │   └── page.tsx
│   ├── dua/
│   │   ├── page.tsx
│   │   └── [id]/
│   ├── reports/
│   │   └── page.tsx
│   ├── templates/
│   │   └── page.tsx
│   └── users/
│       └── page.tsx
│
├── components/                     → Atomic Design UI
│   ├── atoms/
│   │   ├── Button/
│   │   ├── ConfidenceIndicator/
│   │   ├── Input/
│   │   ├── Label/
│   │   └── atoms.css
│   ├── molecules/
│   │   ├── FileUploader/
│   │   ├── FormField/
│   │   └── molecules.css
│   ├── organisms/
│   │   ├── DuaForm/
│   │   ├── Navbar/
│   │   └── organisms.css
│   ├── templates/
│   │   ├── MainLayout/
│   │   └── templates.css
│   └── pages/
│       └── pages.css
│
├── hooks/                          → UI to service connection
│   ├── useAuth.ts
│   ├── useDua.ts
│   ├── useFileUpload.ts
│   └── useNotification.ts
│
├── services/                       → Application operations
│   ├── AuthService.ts
│   ├── DuaService.ts
│   ├── FileService.ts
│   ├── UserService.ts
│   └── index.ts
│
├── apiClients/                     → External API access
│   ├── BaseApiClient.ts
│   ├── AuthApiClient.ts
│   ├── DuaApiClient.ts
│   ├── FileApiClient.ts
│   ├── UserApiClient.ts
│   └── index.ts
│
├── auth/                           → Authentication and authorization
│   ├── authConfig.ts
│   ├── permissions.ts
│   ├── roles.ts
│   └── index.ts
│
├── documentProcessors/             → Builder + Strategy + Adapters
│   ├── DocumentProcessorBuilder.ts
│   ├── strategies/
│   │   ├── IDocumentStrategy.ts
│   │   ├── WordStrategy.ts
│   │   ├── ExcelStrategy.ts
│   │   ├── PdfStrategy.ts
│   │   └── ImageStrategy.ts
│   ├── formatAdapters/
│   │   ├── IFormatAdapter.ts
│   │   ├── ParagraphAdapter.ts
│   │   ├── BulletsAdapter.ts
│   │   ├── TableAdapter.ts
│   │   ├── LabelAdapter.ts
│   │   ├── AmountAdapter.ts
│   │   └── index.ts
│   └── index.ts
│
├── notificationService/            → Observer / callback notifications
│   └── NotificationService.ts
│
├── models/                         → Shared data models
│   ├── ApiResponse.ts
│   ├── Dua.ts
│   ├── FileUpload.ts
│   ├── Permission.ts
│   ├── Role.ts
│   ├── User.ts
│   └── index.ts
│
├── validation/                     → Zod validation layer
│   ├── duaSchema.ts
│   ├── fileSchema.ts
│   ├── userSchema.ts
│   └── index.ts
│
├── state/                          → State management
│   ├── StoreProvider.tsx
│   ├── hooks.ts
│   ├── store.ts
│   └── slices/
│       ├── authSlice.ts
│       ├── duaSlice.ts
│       └── fileSlice.ts
│
├── settings/                       → Configuration / Key Vault access
│   └── Settings.ts
│
├── logs/                           → Logging layer
│   └── Logger.ts
│
├── exceptionHandling/              → Shared exception handling
│   └── ExceptionHandler.ts
│
├── utils/                          → Reusable helpers
│   ├── constants.ts
│   ├── formatters.ts
│   └── index.ts
│
├── i18n/                           → Internationalization
│   ├── config.ts
│   └── locales/
│       ├── en.json
│       └── es.json
│
├── __tests__/                      → Unit and e2e tests
│   ├── setup.ts
│   ├── unit/
│   │   ├── auth/
│   │   ├── documentProcessors/
│   │   ├── notificationService/
│   │   └── services/
│   └── e2e/
│       └── dua.spec.ts
│
├── __mocks__/                      → Test mocks
│   └── styleMock.ts
│
├── types/                          → Type declarations
├── instructions.md                 → Project notes / scaffold instructions
├── package.json
├── tsconfig.json
├── jest.config.ts
├── playwright.config.ts
├── next.config.ts
├── .env.example
├── .eslintrc.json
├── .prettierrc
├── .lintstagedrc.json
└── .husky/
    └── pre-commit                                           
```

---

### [State Management](src/state/)

Redux is used for shared frontend state via the **Pub/Sub pattern**. The store is composed of three slices:

| File | Description |
|---|---|
| [`src/state/store.ts`](src/state/store.ts) | Configures the Redux store with `auth`, `dua`, and `file` reducers |
| [`src/state/StoreProvider.tsx`](src/state/StoreProvider.tsx) | Wraps the application with the Redux `Provider` |
| [`src/state/hooks.ts`](src/state/hooks.ts) | Typed `useAppSelector` and `useAppDispatch` hooks |
| [`src/state/slices/authSlice.ts`](src/state/slices/authSlice.ts) | Auth state: `isAuthenticated`, `user`, `role`, `accessToken` |
| [`src/state/slices/duaSlice.ts`](src/state/slices/duaSlice.ts) | DUA process state: generation status, fields, confidence levels |
| [`src/state/slices/fileSlice.ts`](src/state/slices/fileSlice.ts) | File upload state: selected files, upload progress |

---

### [Data Validation](src/validation/)

Validation is implemented using **Zod** schemas. All API inputs and model shapes are validated before use.

| File | Description |
|---|---|
| [`src/validation/duaSchema.ts`](src/validation/duaSchema.ts) | Schemas for DUA generation input, field shape, and full DUA document |
| [`src/validation/fileSchema.ts`](src/validation/fileSchema.ts) | Validates uploaded file metadata and allowed extensions |
| [`src/validation/userSchema.ts`](src/validation/userSchema.ts) | Validates user creation and update payloads |
| [`src/validation/index.ts`](src/validation/index.ts) | Barrel export for all schemas |

---

### [Observability & Exception Handling](src/logs/)

| File | Description |
|---|---|
| [`src/logs/Logger.ts`](src/logs/Logger.ts) | Singleton logger — sends `info`, `warn`, `error`, and `trackEvent` telemetry to **Azure Application Insights** |
| [`src/exceptionHandling/ExceptionHandler.ts`](src/exceptionHandling/ExceptionHandler.ts) | Singleton — centralized `handle()` and `handleAsync()` methods used by all layers |

---

### [Testing](src/__tests__/)

| File / Folder | Description |
|---|---|
| [`src/__tests__/unit/auth/`](src/__tests__/unit/auth/permissions.test.ts) | Unit tests for `hasPermission` and `getPermissionsForRole` |
| [`src/__tests__/unit/documentProcessors/`](src/__tests__/unit/documentProcessors/DocumentProcessorBuilder.test.ts) | Unit tests for `DocumentProcessorBuilder` and strategy selection |
| [`src/__tests__/unit/notificationService/`](src/__tests__/unit/notificationService/NotificationService.test.ts) | Unit tests for subscribe, notify, and unsubscribe flows |
| [`src/__tests__/unit/services/`](src/__tests__/unit/services/DuaService.test.ts) | Unit tests for `DuaService` orchestration |
| [`src/__tests__/e2e/dua.spec.ts`](src/__tests__/e2e/dua.spec.ts) | Playwright end-to-end test: full DUA generation flow |
| [`src/__tests__/setup.ts`](src/__tests__/setup.ts) | Jest global test setup |
| [`src/__mocks__/styleMock.ts`](src/__mocks__/styleMock.ts) | CSS module mock for Jest |

---

### [Configuration](src/)

| File | Description |
|---|---|
| [`src/next.config.ts`](src/next.config.ts) | Next.js config: `standalone` output, i18n locales (`en`, `es`), Azure Key Vault and App Insights runtime config |
| [`src/jest.config.ts`](src/jest.config.ts) | Jest config: `ts-jest` preset, `jsdom` environment, path aliases for all layers (`@components`, `@services`, `@auth`, etc.) |
| [`src/playwright.config.ts`](src/playwright.config.ts) | Playwright config: Chromium + Firefox projects, `baseURL`, screenshot on failure, CI retry policy |
| [`src/tsconfig.json`](src/tsconfig.json) | TypeScript compiler options and path aliases |
| [`src/.env.example`](src/.env.example) | Environment variable template: Azure AD, Key Vault, App Insights, API base URL, callback URL |
| [`src/.eslintrc.json`](src/.eslintrc.json) | ESLint ruleset |
| [`src/.prettierrc`](src/.prettierrc) | Prettier formatting rules |
| [`src/.lintstagedrc.json`](src/.lintstagedrc.json) | lint-staged config for pre-commit hooks |
| [`src/.husky/pre-commit`](src/.husky/pre-commit) | Husky pre-commit hook — runs lint-staged before every commit |
| [`src/settings/Settings.ts`](src/settings/Settings.ts) | Singleton — resolves secrets from Azure Key Vault or environment variables at runtime |

---

---

# Backend

## [Technology Stack](duabusiness/)

| Dimension | Decision | Justification |
|---|---|---|
| **Transport protocol** | HTTPS / TLS 1.3 | Internet-facing API; TLS is mandatory for customs data in transit |
| **API style** | REST over HTTP/1.1 | Broad integration support, native HTTP caching, well-understood by customs tooling consumers |
| **API contract standard** | OpenAPI 3.1 | Auto-generated documentation, client SDK generation, and contract-first design |
| **Async / long-running operations** | Azure Notification Hubs (push) + polling fallback | DUA generation can take 30–120 seconds; push notifications decouple the client from blocking waits |
| **Coding language** | C# — .NET 9 | Native Azure integration, ASP.NET Core performance, strong typing aligned with the customs domain model |
| **Web framework** | ASP.NET Core 9 (Minimal API + Controllers) | Minimal API for lightweight endpoints; Controllers for complex resource domains (DUA, Files, Users) |
| **ORM** | Entity Framework Core 9 | Code-first migrations, LINQ query composition, Azure SQL compatibility |
| **Database** | Azure SQL Database (General Purpose tier) | Relational structure fits the DUA field model; managed failover, auditing built-in |
| **Blob storage** | Azure Blob Storage | Stores raw uploaded documents and generated DUA `.docx` files outside the database |
| **Unit testing** | xUnit 2.9 | Standard .NET testing framework; compatible with Azure DevOps test reporting |
| **Integration testing** | Microsoft.AspNetCore.Mvc.Testing | In-process test server to test full HTTP pipeline without external dependencies |
| **Data validation** | FluentValidation 11 | Declarative validator classes per request model; separates validation from controller logic |
| **API documentation** | Swashbuckle (Swagger UI) | Auto-generates interactive OpenAPI docs from controller annotations |
| **Code style** | EditorConfig + StyleCop.Analyzers | Enforces consistent C# formatting across the team |
| **Code automation** | Husky.NET (pre-commit hooks) | Runs linting and unit tests before every commit |
| **Cloud service** | Azure Cloud Services | Same ecosystem as the frontend; unified identity (Entra ID), billing, and monitoring |
| **Hosting** | Azure App Service (B3 tier, auto-scale to P2v3) | PaaS removes OS patching; auto-scale handles processing spikes |
| **API gateway** | Azure API Management (Developer tier → Standard in prod) | Rate limiting, JWT validation at the edge, OpenAPI publishing, versioning |
| **Async messaging** | Azure Notification Hubs | Sends real-time processing status updates to the frontend callback URL |
| **File streaming** | Azure Blob Storage multipart streaming | Large files are streamed directly to blob; avoids in-memory buffering on the API server |
| **AI / OCR service** | Azure AI Document Intelligence (Form Recognizer) | Extracts structured fields from invoices, packing lists, and scanned images; returns bounding-box confidence scores used to populate `ConfidenceLevel` |
| **Environments** | Development · Stage · Production | Separate App Service slots; Stage is a full-fidelity copy of Production for final validation |
| **Repository** | Monorepo — `duabusiness/` folder | Shares the same Azure DevOps repo as the frontend (`duawebapp/`) |

---

## [Services / Microservices and Repository Architecture](duabusiness/)

**Architecture style: Modular Monolith**

A single deployable ASP.NET Core application is used, internally organized into bounded contexts aligned with DDD principles. This decision avoids the operational complexity of microservices (distributed tracing, network retries, saga orchestration) at a stage where the domain is still being validated and the team size does not justify independent deployment pipelines per service.

**Repository strategy: Monorepo**

Both `duawebapp/` (frontend) and `duabusiness/` (backend) live in the same Azure DevOps repository. This allows a single pull request to span API contract changes and the frontend API client that consumes them, eliminating version-skew between layers.

**Bounded contexts (DDD)**

| Bounded Context | Responsibility | Key Folder |
|---|---|---|
| **Identity** | Authentication token validation, role and permission enforcement, session metadata | [`duabusiness/Identity/`](duabusiness/Identity/) |
| **DocumentIngestion** | Receives uploaded files, streams to Azure Blob Storage, triggers processing pipeline | [`duabusiness/DocumentIngestion/`](duabusiness/DocumentIngestion/) |
| **DuaGeneration** | Orchestrates OCR extraction, semantic mapping, confidence scoring, and `.docx` generation | [`duabusiness/DuaGeneration/`](duabusiness/DuaGeneration/) |
| **TemplateManagement** | CRUD for official DUA templates stored in blob and registered in the database | [`duabusiness/TemplateManagement/`](duabusiness/TemplateManagement/) |
| **UserManagement** | User CRUD, role assignments, audit trail of role changes | [`duabusiness/UserManagement/`](duabusiness/UserManagement/) |
| **Observability** | Structured logging, event tracking, health endpoints | [`duabusiness/Observability/`](duabusiness/Observability/) |

Each bounded context owns its own controllers, services, domain models, repositories, and validators. Cross-context communication happens only through shared interfaces in [`duabusiness/Shared/`](duabusiness/Shared/), never by directly calling another context's internal classes.

---

## [Layered Design](duabusiness/)

The backend follows a **Clean Architecture** layering, with dependency flow pointing inward (infrastructure depends on domain, never the reverse).

```
HTTP Request
     │
     ▼
┌─────────────────────────────┐
│     API Layer               │  ASP.NET Core Controllers / Minimal API routes
│  (Controllers, Middleware)  │  JWT validation middleware, rate limiting, request logging
└────────────┬────────────────┘
             │
             ▼
┌─────────────────────────────┐
│   Application Layer         │  Command / Query handlers (CQRS-lite)
│  (Services, Validators)     │  FluentValidation, orchestration logic, no domain rules here
└────────────┬────────────────┘
             │
             ▼
┌─────────────────────────────┐
│   Domain Layer              │  Entities, Value Objects, Domain Services, Repository interfaces
│  (Entities, Aggregates)     │  Pure C# — no framework dependencies
└────────────┬────────────────┘
             │
             ▼
┌─────────────────────────────┐
│   Infrastructure Layer      │  EF Core DbContext, Azure Blob Storage client,
│  (Repositories, Adapters)   │  Azure AI Document Intelligence adapter, Notification Hubs adapter
└─────────────────────────────┘

Shared / Cross-cutting:
  Settings (Azure Key Vault)
  Logger (Application Insights)
  ExceptionHandler (global middleware)
  Models / DTOs
```

**Request flow narrative:**

1. An HTTP request arrives at **Azure API Management**, which validates the JWT issued by Microsoft Entra ID and enforces rate limits.
2. APIM forwards the request to the **ASP.NET Core API Layer** running in Azure App Service.
3. The JWT middleware extracts the user's role and injects it into the `HttpContext`.
4. The controller delegates work to the **Application Layer** service, passing validated request DTOs.
5. Application services call **Domain Layer** aggregates and repository interfaces.
6. The **Infrastructure Layer** fulfills repository contracts via EF Core (Azure SQL) or the Blob Storage / AI Document Intelligence clients.
7. For long-running operations (DUA generation), the Application Layer returns a `202 Accepted` with a `processId`, then pushes progress updates via **Azure Notification Hubs** to the frontend callback URL.

---

## [Security](duabusiness/Identity/)

Security decisions that apply across all backend layers:

### Transport

- **TLS 1.3** enforced at Azure API Management level. HTTP requests are rejected with `301 Redirect` to HTTPS.
- **HSTS** header (`max-age=31536000; includeSubDomains`) is set on all responses.

### Authentication & Token Validation

- All endpoints require a **Bearer JWT** issued by **Microsoft Entra ID**.
- JWTs are validated at the **Azure API Management** edge (signature, expiry, audience, issuer) before reaching the application server.
- Inside the application, the **Identity middleware** (`duabusiness/Identity/Middleware/RoleEnforcementMiddleware.cs`) reads the `roles` claim and maps it to the internal `RoleType` enum.
- Tokens have a **60-minute expiry**. Refresh is handled by the frontend via MSAL; the backend never stores refresh tokens.

### Authorization

- **RBAC**: every controller action is decorated with `[RequirePermission(PermissionCode.X)]`. The `PermissionAuthorizationHandler` resolves the user's role from the JWT and checks it against the permission map defined in `duabusiness/Identity/Authorization/PermissionDefinitions.cs`.
- **PBAC policies** are enforced inside Application Layer services (e.g., `POL-001 ExportOnlyWhenReviewed` is checked in `DuaExportService` before generating the download URL).
- **ACL**: the `DuaProcess` entity stores `ownerId` and `assignedReviewerId`. The `DuaAccessGuard` service rejects edit operations when the calling user is neither the owner, the assigned reviewer, nor a `SYS_ADMIN`.

### Encryption

- **Data in transit**: TLS 1.3 (see above).
- **Data at rest**: Azure SQL Transparent Data Encryption (TDE) with a customer-managed key stored in Azure Key Vault. Azure Blob Storage uses service-managed encryption (AES-256).
- **Sensitive fields** (e.g., OAuth client secrets, database connection strings) are never in source code. They are resolved at runtime from **Azure Key Vault** via the `Settings` singleton (`duabusiness/Shared/Settings/Settings.cs`).

### API Surface Hardening

| Control | Value | Implementation |
|---|---|---|
| Max payload size (general) | 10 MB | `RequestSizeLimitAttribute` on base controller |
| Max payload size (file upload) | 100 MB per file, 500 MB per batch | `DisableRequestSizeLimit` + manual size check in `FileUploadService` |
| Rate limit — general endpoints | 200 requests / minute / user | Azure API Management inbound policy |
| Rate limit — DUA generation | 10 requests / minute / user | Azure API Management inbound policy on `/api/v1/dua/generate` |
| Max concurrent DUA processes per user | 3 | Checked in `DuaGenerationService` before enqueuing |
| OWASP API Top 10 mitigations | Injection: parameterized EF Core queries. Broken Auth: APIM JWT validation. Excessive Data Exposure: response DTOs never expose internal entity IDs or raw file paths. | Applied across all layers |

### Secrets Management

**Secure store service:** `Azure Key Vault`

| Secret Name | Content |
|---|---|
| `entra-client-id` | Azure Entra ID application client ID |
| `entra-tenant-id` | Azure Entra ID tenant ID |
| `sql-connection-string` | Azure SQL connection string with credentials |
| `blob-storage-connection` | Azure Blob Storage account connection string |
| `notification-hubs-connection` | Azure Notification Hubs connection string |
| `document-intelligence-key` | Azure AI Document Intelligence API key |
| `app-insights-connection` | Azure Application Insights connection string |
| `encryption-key` | AES-256 key for field-level encryption on sensitive DUA data |

---

## [Design Patterns](duabusiness/)

| Pattern | Usage | File(s) |
|---|---|---|
| **Repository** | Abstracts data access; domain layer depends on `IRepository<T>` interfaces, never on EF Core directly | [`duabusiness/Shared/Repositories/IRepository.cs`](duabusiness/Shared/Repositories/IRepository.cs) |
| **Unit of Work** | Wraps multiple repository operations in a single EF Core transaction | [`duabusiness/Shared/Repositories/IUnitOfWork.cs`](duabusiness/Shared/Repositories/IUnitOfWork.cs) |
| **CQRS-lite (Command / Query)** | Commands mutate state; Queries return data. Separated by folder convention, not by separate buses | [`duabusiness/DuaGeneration/Commands/`](duabusiness/DuaGeneration/Commands/) · [`duabusiness/DuaGeneration/Queries/`](duabusiness/DuaGeneration/Queries/) |
| **Strategy** | Selects the correct document parser (Word, Excel, PDF, Image) at runtime based on MIME type | [`duabusiness/DocumentIngestion/Strategies/`](duabusiness/DocumentIngestion/Strategies/) |
| **Factory** | `DocumentParserFactory` instantiates the right strategy without exposing concrete types | [`duabusiness/DocumentIngestion/Factories/DocumentParserFactory.cs`](duabusiness/DocumentIngestion/Factories/DocumentParserFactory.cs) |
| **Adapter** | `DocumentIntelligenceAdapter` wraps the Azure AI SDK; `NotificationHubAdapter` wraps the Azure SDK — both implement internal interfaces | [`duabusiness/Shared/Adapters/`](duabusiness/Shared/Adapters/) |
| **Decorator** | `LoggingRepositoryDecorator<T>` wraps every repository to add structured logging without modifying domain code | [`duabusiness/Shared/Repositories/LoggingRepositoryDecorator.cs`](duabusiness/Shared/Repositories/LoggingRepositoryDecorator.cs) |
| **Singleton** | `Settings`, `Logger`, `ExceptionHandler` are registered as `AddSingleton` in the DI container | [`duabusiness/Shared/Settings/Settings.cs`](duabusiness/Shared/Settings/Settings.cs) |
| **Options pattern** | `IOptions<T>` binds each bounded context's configuration section from `appsettings.json` / Key Vault | Applied per bounded context in `Program.cs` |
| **Middleware pipeline** | `RoleEnforcementMiddleware`, `CorrelationIdMiddleware`, `GlobalExceptionHandlerMiddleware` are composed in order in `Program.cs` | [`duabusiness/Shared/Middleware/`](duabusiness/Shared/Middleware/) |

---

## [`/duabusiness` Project Scaffold](duabusiness/)

```
duabusiness/
├── Program.cs                          → App entry point: DI registration, middleware pipeline, OpenAPI setup
├── appsettings.json                    → Non-sensitive config (logging levels, feature flags)
├── appsettings.Development.json        → Dev overrides (local SQL, mock AI service)
├── duabusiness.csproj
│
├── Identity/                           → Bounded context: authentication & authorization
│   ├── Middleware/
│   │   └── RoleEnforcementMiddleware.cs
│   ├── Authorization/
│   │   ├── PermissionDefinitions.cs    → Role → PermissionCode[] map
│   │   ├── PermissionAuthorizationHandler.cs
│   │   └── RequirePermissionAttribute.cs
│   └── Services/
│       └── TokenValidationService.cs
│
├── DocumentIngestion/                  → Bounded context: file upload & parsing
│   ├── Controllers/
│   │   └── FileController.cs           → POST /api/v1/files/upload, GET /api/v1/files/{batchId}
│   ├── Services/
│   │   ├── FileUploadService.cs        → Streams files to Azure Blob Storage
│   │   └── FileValidationService.cs    → Extension, size, MIME type checks
│   ├── Strategies/
│   │   ├── IDocumentParserStrategy.cs
│   │   ├── WordParserStrategy.cs
│   │   ├── ExcelParserStrategy.cs
│   │   ├── PdfParserStrategy.cs
│   │   └── ImageParserStrategy.cs
│   ├── Factories/
│   │   └── DocumentParserFactory.cs
│   ├── Models/
│   │   ├── FileUploadBatch.cs
│   │   └── ParsedDocument.cs
│   └── Validators/
│       └── FileUploadRequestValidator.cs
│
├── DuaGeneration/                      → Bounded context: DUA orchestration & output
│   ├── Controllers/
│   │   └── DuaController.cs            → POST /api/v1/dua/generate, GET /api/v1/dua/{id}, GET /api/v1/dua/{id}/download, GET /api/v1/dua, PATCH /api/v1/dua/{id}/fields, POST /api/v1/dua/{id}/approve
│   ├── Commands/
│   │   ├── GenerateDuaCommand.cs
│   │   ├── GenerateDuaCommandHandler.cs
│   │   ├── UpdateDuaFieldCommand.cs
│   │   └── ApproveDuaCommand.cs
│   ├── Queries/
│   │   ├── GetDuaByIdQuery.cs
│   │   ├── GetDuaByIdQueryHandler.cs
│   │   └── GetDuaListQuery.cs
│   ├── Services/
│   │   ├── DuaOrchestrationService.cs  → Coordinates parsing → mapping → confidence → docx generation
│   │   ├── SemanticMappingService.cs   → Maps extracted fields to official DUA field codes
│   │   ├── ConfidenceScoreService.cs   → Assigns High / Medium / Low based on AI confidence + validation rules
│   │   ├── DuaDocxGeneratorService.cs  → Produces the pre-filled .docx file with color-coded confidence
│   │   ├── DuaExportService.cs         → Enforces POL-001 then generates SAS download URL from blob
│   │   └── DuaAccessGuard.cs           → Enforces POL-002, POL-003 (owner / reviewer / admin check)
│   ├── Models/
│   │   ├── DuaProcess.cs               → Aggregate root: id, status, fields[], ownerId, reviewerId
│   │   ├── DuaField.cs                 → fieldCode, value, confidence, sourceFile, requiresReview
│   │   ├── DuaStatus.cs                → Enum: Pending, Processing, Completed, Failed, Review
│   │   └── ConfidenceLevel.cs          → Enum: High, Medium, Low
│   ├── Repositories/
│   │   └── IDuaProcessRepository.cs
│   └── Validators/
│       ├── GenerateDuaRequestValidator.cs
│       └── UpdateDuaFieldRequestValidator.cs
│
├── TemplateManagement/                 → Bounded context: DUA template CRUD
│   ├── Controllers/
│   │   └── TemplateController.cs       → GET /api/v1/templates, POST /api/v1/templates, PUT /api/v1/templates/{id}, DELETE /api/v1/templates/{id}
│   ├── Services/
│   │   └── TemplateService.cs
│   ├── Models/
│   │   └── DuaTemplate.cs              → id, name, version, blobPath, isActive, createdAt
│   └── Validators/
│       └── TemplateUpsertValidator.cs
│
├── UserManagement/                     → Bounded context: user and role administration
│   ├── Controllers/
│   │   └── UserController.cs           → GET /api/v1/users, POST /api/v1/users, PUT /api/v1/users/{id}, DELETE /api/v1/users/{id}
│   ├── Services/
│   │   └── UserService.cs
│   ├── Models/
│   │   └── AppUser.cs                  → id, entraId, email, displayName, role, createdAt
│   └── Validators/
│       └── UserUpsertValidator.cs
│
├── Observability/                      → Bounded context: logging, health checks, audit
│   ├── Controllers/
│   │   └── HealthController.cs         → GET /health/live, GET /health/ready
│   ├── Services/
│   │   └── AuditLogService.cs          → Writes immutable audit records to Azure SQL
│   └── Models/
│       └── AuditEvent.cs               → actorId, action, resourceId, timestamp, result
│
├── Shared/                             → Cross-cutting infrastructure
│   ├── Settings/
│   │   └── Settings.cs                 → Singleton: reads from Key Vault / env vars at startup
│   ├── Middleware/
│   │   ├── CorrelationIdMiddleware.cs  → Injects X-Correlation-Id header on every request/response
│   │   ├── RequestLoggingMiddleware.cs → Logs method, path, status, duration, correlation ID
│   │   └── GlobalExceptionHandlerMiddleware.cs → Catches unhandled exceptions, returns RFC 7807 ProblemDetails
│   ├── Repositories/
│   │   ├── IRepository.cs
│   │   ├── IUnitOfWork.cs
│   │   ├── EfRepository.cs             → Generic EF Core implementation
│   │   └── LoggingRepositoryDecorator.cs
│   ├── Adapters/
│   │   ├── IDocumentIntelligenceAdapter.cs
│   │   ├── DocumentIntelligenceAdapter.cs  → Wraps Azure AI Document Intelligence SDK
│   │   ├── INotificationAdapter.cs
│   │   └── NotificationHubAdapter.cs       → Wraps Azure Notification Hubs SDK
│   ├── Persistence/
│   │   └── DuaDbContext.cs             → EF Core DbContext: DuaProcesses, DuaFields, Users, Templates, AuditEvents
│   └── Models/
│       ├── ApiResponse.cs              → Generic wrapper: success, data, error
│       └── ProblemDetails.cs           → RFC 7807 error response model
│
└── Tests/
    ├── Unit/
    │   ├── DuaGeneration/
    │   │   ├── SemanticMappingServiceTests.cs
    │   │   ├── ConfidenceScoreServiceTests.cs
    │   │   └── DuaAccessGuardTests.cs
    │   ├── DocumentIngestion/
    │   │   └── DocumentParserFactoryTests.cs
    │   └── Identity/
    │       └── PermissionAuthorizationHandlerTests.cs
    └── Integration/
        ├── DuaControllerTests.cs
        ├── FileControllerTests.cs
        └── TemplateControllerTests.cs
```

---

## [API Endpoints](duabusiness/)

All endpoints are prefixed `/api/v1/`. All require a valid Bearer JWT unless noted otherwise.

### Files

| Method | Path | Permission | Description |
|---|---|---|---|
| `POST` | `/api/v1/files/upload` | `DOCUMENT_SCAN_START` | Initiates a streaming multipart upload; returns `batchId` |
| `GET` | `/api/v1/files/{batchId}` | `DOCUMENT_LIST_VIEW` | Returns upload batch status and list of detected files |

### DUA

| Method | Path | Permission | Description |
|---|---|---|---|
| `POST` | `/api/v1/dua/generate` | `PROCESS_START` | Enqueues a DUA generation job; returns `202 Accepted` with `processId` |
| `GET` | `/api/v1/dua/{id}` | `DUA_RESULT_VIEW` | Returns the DUA process state, field values, and confidence levels |
| `GET` | `/api/v1/dua` | `HISTORY_VIEW` | Returns paginated list of DUA processes for the calling user |
| `PATCH` | `/api/v1/dua/{id}/fields` | `DUA_RESULT_EDIT` | Updates one or more field values (enforces POL-002) |
| `POST` | `/api/v1/dua/{id}/approve` | `DUA_RESULT_APPROVE` | Marks a DUA as approved (enforces POL-003) |
| `GET` | `/api/v1/dua/{id}/download` | `DUA_RESULT_EXPORT` | Returns a time-limited SAS URL to download the `.docx` file (enforces POL-001) |

### Templates

| Method | Path | Permission | Description |
|---|---|---|---|
| `GET` | `/api/v1/templates` | `DUA_TEMPLATE_SELECT` | Returns all active DUA templates |
| `POST` | `/api/v1/templates` | `SYSTEM_CONFIG` | Creates a new template (uploads `.docx` to blob) |
| `PUT` | `/api/v1/templates/{id}` | `SYSTEM_CONFIG` | Updates template metadata or file |
| `DELETE` | `/api/v1/templates/{id}` | `SYSTEM_CONFIG` | Soft-deletes a template (sets `isActive = false`) |

### Users

| Method | Path | Permission | Description |
|---|---|---|---|
| `GET` | `/api/v1/users` | `USER_ADMIN` | Returns all registered users |
| `POST` | `/api/v1/users` | `USER_ADMIN` | Registers a new user and assigns a role |
| `PUT` | `/api/v1/users/{id}` | `USER_ADMIN` | Updates user role or metadata |
| `DELETE` | `/api/v1/users/{id}` | `USER_ADMIN` | Deactivates a user account |

### Health

| Method | Path | Auth Required | Description |
|---|---|---|---|
| `GET` | `/health/live` | No | Returns `200 OK` if the process is alive |
| `GET` | `/health/ready` | No | Returns `200 OK` only if SQL and Blob Storage dependencies are reachable |

---

## [Key Backend Workflows](duabusiness/DuaGeneration/)

### Upload Files to Generate DUA

1. The frontend calls `POST /api/v1/files/upload` with a multipart form body containing one or more files.
2. The `FileController` validates the request using `FileUploadRequestValidator` (extension whitelist: `.docx`, `.xlsx`, `.pdf`, `.jpg`, `.png`; max file size: 100 MB; max batch size: 500 MB).
3. If validation fails, the controller returns `400 Bad Request` with a `ProblemDetails` body listing all validation errors.
4. If validation passes, `FileUploadService` opens a streaming pipe and writes each file directly to **Azure Blob Storage** under the path `uploads/{userId}/{batchId}/{fileName}` — the file content never fully materialises in API server memory.
5. For each successfully stored file, a `FileMetadata` record is written to Azure SQL via `EfRepository` within a single `IUnitOfWork` transaction (all files in the batch commit together or roll back together).
6. The controller returns `202 Accepted` with the `batchId` and the list of detected file names and types.
7. An `AuditEvent` (`action: FILE_BATCH_UPLOADED`) is written by `AuditLogService`.

### Generate DUA

1. The frontend calls `POST /api/v1/dua/generate` with `{ batchId, templateId }`.
2. `DuaController` validates the request using `GenerateDuaRequestValidator` (both IDs must exist and belong to the calling user).
3. `DuaOrchestrationService` creates a `DuaProcess` entity with `status = Pending` and persists it; returns `202 Accepted` with `{ processId }` to the frontend immediately.
4. The orchestrator updates `status = Processing` and begins iterating over the files in the batch:
   a. `DocumentParserFactory` selects the correct `IDocumentParserStrategy` based on the file MIME type.
   b. Each strategy reads the file stream from Azure Blob Storage and calls `DocumentIntelligenceAdapter.AnalyzeAsync()`, receiving a list of `ExtractedField` objects with raw values and AI confidence scores (0.0–1.0).
5. `SemanticMappingService` maps each `ExtractedField` to the official DUA field code (e.g., `FIELD_33_CUSTOMS_PROCEDURE`) using a rule table defined in `PermissionDefinitions.cs`. Fields not matched to any DUA code are collected as `unmappedFields` for manual review.
6. `ConfidenceScoreService` converts each AI confidence float to `ConfidenceLevel`:
   - `>= 0.85` → `High` (green)
   - `0.60 – 0.84` → `Medium` (yellow)
   - `< 0.60` → `Low` (red, `requiresReview = true`)
7. `DuaDocxGeneratorService` loads the selected template `.docx` from Blob Storage, fills each mapped field, and applies background shading per confidence level. The generated file is uploaded to `results/{userId}/{processId}/dua.docx` in Blob Storage.
8. `DuaProcess.status` is updated to `Completed` (or `Failed` if an unrecoverable error occurred). The `DuaField[]` array is persisted to Azure SQL.
9. `NotificationHubAdapter.SendAsync()` pushes a status update event to the frontend callback URL registered during session setup, carrying `{ processId, status, fieldCount, reviewRequiredCount }`.
10. An `AuditEvent` (`action: DUA_GENERATED`) is written.

### Setup / Update DUA Template

1. An authorised `SYS_ADMIN` calls `POST /api/v1/templates` with a multipart body containing the `.docx` template file and metadata (`name`, `version`).
2. `TemplateController` validates the request using `TemplateUpsertValidator` (file must be `.docx`, max 20 MB, version must follow semantic versioning `X.Y.Z`).
3. `TemplateService` streams the file to Blob Storage at `templates/{templateId}/template.docx`.
4. A `DuaTemplate` record is inserted into Azure SQL with `isActive = true`. Any previously active template with the same `name` is soft-deleted (`isActive = false`) to preserve history.
5. The controller returns `201 Created` with the new template's `id`, `name`, `version`, and `createdAt`.
6. An `AuditEvent` (`action: TEMPLATE_CREATED`) is written.

### Export DUA

1. The frontend calls `GET /api/v1/dua/{id}/download`.
2. `DuaController` calls `DuaExportService.GetDownloadUrlAsync(processId, callingUserId)`.
3. `DuaExportService` enforces **POL-001**: if `DuaProcess.status != Completed` or no reviewer has approved the document, a `403 Forbidden` response is returned.
4. `DuaAccessGuard` enforces **POL-003**: only the owner, the assigned reviewer, or a `SYS_ADMIN` may download.
5. If all checks pass, a **Shared Access Signature (SAS) URL** with a 15-minute expiry is generated for the blob `results/{userId}/{processId}/dua.docx`.
6. The controller returns `200 OK` with `{ downloadUrl, expiresAt }`.
7. An `AuditEvent` (`action: DUA_EXPORTED`) is written.

---

## [Observability](duabusiness/Observability/)

All three observability pillars are centralised in **Azure Monitor / Application Insights**.

### Structured Logs

- All log entries are emitted as **JSON** via `Microsoft.Extensions.Logging` + the Application Insights sink.
- Every log entry carries a `correlationId` injected by `CorrelationIdMiddleware` from the `X-Correlation-Id` request header (or generated if absent). This ID is propagated to Azure AI Document Intelligence calls so distributed traces can be stitched together.
- `RequestLoggingMiddleware` records: `method`, `path`, `statusCode`, `durationMs`, `userId`, `correlationId` for every inbound request.

| Log Level | When Used |
|---|---|
| `Information` | Successful operations: file uploaded, DUA completed, user created |
| `Warning` | Recoverable issues: field confidence below threshold, retry on transient DB error |
| `Error` | Unrecoverable failures caught by `GlobalExceptionHandlerMiddleware` |
| `Critical` | Key Vault unreachable at startup, database migration failure |

### Metrics

The following custom metrics are tracked via Application Insights `TelemetryClient.TrackMetric()`:

| Metric Name | Unit | Description |
|---|---|---|
| `dua.generation.duration` | ms | Time from `status = Processing` to `status = Completed` |
| `dua.fields.confidence.high` | count | Number of High-confidence fields per DUA |
| `dua.fields.confidence.medium` | count | Number of Medium-confidence fields per DUA |
| `dua.fields.confidence.low` | count | Number of Low-confidence (review required) fields per DUA |
| `file.upload.size` | bytes | Total batch size per upload |
| `api.request.duration` | ms | HTTP request latency by route (auto-collected by APIM + App Insights) |
| `api.request.errors` | count | 4xx and 5xx responses by route |

Dashboards are built in **Azure Monitor Workbooks** using these metrics. Alerts are configured for:
- `dua.generation.duration` p95 > 180 s → PagerDuty notification to on-call team.
- `api.request.errors` rate > 5% over 5 minutes → Email alert to `ops@duastreamliner.com`.

### Distributed Traces

- **OpenTelemetry** SDK is configured in `Program.cs` with the Azure Monitor exporter.
- Every outbound call to Azure Blob Storage, Azure SQL, and Azure AI Document Intelligence is automatically instrumented.
- Trace spans for each DUA generation step (parse, map, score, generate, notify) are manually emitted via `Activity.StartActivity()` so the end-to-end processing timeline is visible in the Application Insights **Transaction Search** view.

### Health Checks

| Endpoint | Check | Failure Condition |
|---|---|---|
| `GET /health/live` | Process is running | Always `200 OK` unless the process is crashed |
| `GET /health/ready` | Azure SQL reachable + Blob Storage reachable | Returns `503 Service Unavailable` with detail if any dependency is down |

Azure App Service **health check probe** is configured to call `/health/ready` every 30 seconds. If it fails 3 consecutive times, App Service removes the instance from the load balancer and attempts a restart.

---

## [Infrastructure / DevOps](duabusiness/)

### CI/CD

**Tool:** Azure DevOps Pipelines (YAML)

| Stage | Trigger | Steps |
|---|---|---|
| **Build** | Every push to any branch | Restore NuGet packages → `dotnet build` → run unit tests (xUnit) → publish test results → build Docker image |
| **Deploy to Dev** | Merge to `develop` branch | Run integration tests against Dev slot → deploy to `Azure App Service / dev` slot via `az webapp deploy` |
| **Deploy to Stage** | Merge to `main` branch | Deploy to `Stage` App Service slot → run Playwright smoke tests → manual approval gate |
| **Deploy to Prod** | After manual approval | Swap Stage ↔ Production slots (zero-downtime blue/green swap) |

### Infrastructure as Code

**Tool:** **Bicep** (Azure-native IaC)

All Azure resources are declared in `infrastructure/` at the monorepo root:

| File | Resources Declared |
|---|---|
| `infrastructure/main.bicep` | Resource group, App Service Plan, App Service (frontend + backend slots), API Management instance |
| `infrastructure/database.bicep` | Azure SQL Server, Azure SQL Database (General Purpose, 4 vCores), firewall rules |
| `infrastructure/storage.bicep` | Azure Blob Storage account, containers (`uploads`, `results`, `templates`), lifecycle policies |
| `infrastructure/keyvault.bicep` | Azure Key Vault, access policies for App Service managed identity |
| `infrastructure/monitoring.bicep` | Application Insights workspace, Log Analytics workspace, alert rules |
| `infrastructure/notifications.bicep` | Azure Notification Hubs namespace and hub |

All infrastructure changes go through the same Azure DevOps pipeline. A `bicep what-if` plan is generated and posted as a PR comment before any `bicep deploy` runs in Stage or Prod.

### Environment Parity

| Setting | Development | Stage | Production |
|---|---|---|---|
| Azure SQL tier | Basic (5 DTU) | General Purpose (2 vCores) | General Purpose (4 vCores) |
| App Service tier | B1 | P1v3 | P2v3 (auto-scale 2–6 instances) |
| Azure AI Document Intelligence | Free tier (500 pages/month) | S0 Standard | S0 Standard |
| Data | Synthetic generated fixtures | Anonymised copy of prod (refreshed weekly) | Live |

---

## [Availability](duabusiness/)

### SLA Target

**99.9% uptime** — equivalent to a maximum of **8.7 hours of downtime per year**.

### Single Points of Failure and Mitigations

| Component | Default SLA | Mitigation |
|---|---|---|
| **Azure App Service** (Standard/Premium tier) | 99.95% | Two or more instances behind the built-in load balancer; auto-heal on health check failure |
| **Azure SQL Database** (General Purpose) | 99.99% | Zone-redundant deployment; automatic failover in < 30 s; point-in-time restore up to 35 days |
| **Azure Blob Storage** (LRS) | 99.9% read, 99.9% write | Upgraded to **ZRS** (Zone-Redundant Storage) in Production; 99.99% read SLA |
| **Azure API Management** | 99.95% (multi-region) | Single region (same as App Service); acceptable for current scale |
| **Azure Notification Hubs** | 99.9% | Frontend polls `/api/v1/dua/{id}` every 10 s as fallback if push notification is not received within 30 s |
| **Azure AI Document Intelligence** | 99.9% | `DocumentIntelligenceAdapter` implements exponential-backoff retry (3 attempts, 2 s / 4 s / 8 s) for transient 429 and 503 responses |
| **Azure Key Vault** | 99.99% | Secrets are cached in-memory at startup for 1 hour; Key Vault outage does not affect running instances |

### Resilience Patterns

- **Circuit Breaker**: `Polly` library wraps all outbound HTTP calls (Azure AI Document Intelligence, Notification Hubs). After 5 consecutive failures within 60 seconds, the circuit opens for 30 seconds before retrying.
- **Timeout**: All outbound calls have an explicit timeout — 30 s for Document Intelligence, 10 s for Blob Storage operations, 5 s for Notification Hubs.
- **Bulkhead**: Maximum 10 concurrent DUA generation pipelines per App Service instance, enforced by a `SemaphoreSlim` in `DuaOrchestrationService`. Requests beyond the limit return `429 Too Many Requests`.
- **Graceful degradation**: If Notification Hubs is unreachable, the backend logs a warning and relies on the frontend polling fallback. The DUA generation result is still stored in SQL and Blob Storage.

---

## [Scalability](duabusiness/)

### Expected Bottlenecks

| Bottleneck | Reason | Mitigation |
|---|---|---|
| **DUA generation pipeline** | CPU-bound OCR + semantic mapping; each job takes 30–120 s | Azure App Service auto-scale (CPU > 70% → add instance, up to 6 instances); bulkhead limits per-instance concurrency |
| **File upload throughput** | Large files (up to 100 MB) streamed to Blob Storage | Multipart streaming avoids API server memory saturation; Blob Storage scales horizontally without configuration |
| **Azure SQL** | DuaField writes at end of each generation job | EF Core bulk insert for `DuaField[]`; read replicas for `GET /api/v1/dua` list queries (EF Core `UseQueryTrackingBehavior(NoTracking)`) |
| **Azure AI Document Intelligence** | Rate limited per subscription (15 transactions per second on S0) | Per-user rate limit of 10 DUA generations/minute via APIM; circuit breaker absorbs transient 429s |

### Elements That Scale When Request Volume Grows

- **Azure App Service**: horizontal scale-out (add instances) triggered by CPU ≥ 70% or active request queue > 100.
- **Azure Blob Storage**: scales automatically; no partition limit for the expected volume.
- **Azure SQL**: vertical scale (increase vCores) or read replicas for reporting queries.
- **Azure API Management**: request units are consumed per call; upgrade from Developer to Standard tier increases throughput limit.

### Stateless Design

The ASP.NET Core application is fully **stateless**. No in-memory session is stored between requests. All state (DUA process status, field values, user sessions) lives in Azure SQL or Blob Storage. This allows App Service to route any request to any instance without sticky sessions.

---

## [Architecture Diagrams (C4)](duabusiness/)

### Context Diagram

The DUA Streamliner system is used by customs specialists, reviewers, auditors, and administrators who access it through a web browser. The system processes source documents (invoices, packing lists, bills of lading) provided by the user and produces a pre-filled DUA Word document. Externally, the system delegates identity verification to **Microsoft Entra ID** and document intelligence extraction to **Azure AI Document Intelligence**. Notification delivery to the browser is handled by **Azure Notification Hubs**.

```mermaid
graph TD
    CS[Customs Specialist] -->|Uploads docs, starts generation| DUA[DUA Streamliner]
    CR[Customs Reviewer] -->|Reviews and approves DUA| DUA
    AU[Auditor] -->|Read-only audit access| DUA
    SA[SYS ADMIN] -->|System configuration| DUA
    DUA -->|Validates identity and roles| ENTRA[Microsoft Entra ID]
    DUA -->|Extracts fields from documents| DOCINT[Azure AI Document Intelligence]
    DUA -->|Pushes processing status| NOTIF[Azure Notification Hubs]
    NOTIF -->|Real-time update| CS
```

---

### Container Diagram

```
┌──────────────────────────────────────────────────────────────────────────────────┐
│  Azure Cloud                                                                     │
│                                                                                  │
│  ┌────────────────┐     HTTPS/JWT      ┌──────────────────────────────────────┐  │
│  │  Browser       │ ─────────────────► │  Azure API Management                │  │
│  │  React SSR     │                    │  Rate limiting, JWT edge validation, │  │
│  │  (Node.js 21)  │                    │  OpenAPI publishing                  │  │
│  │  Azure App     │                    └─────────────────┬────────────────────┘  │
│  │  Service       │                                      │ HTTPS                 │
│  └────────────────┘                                      ▼                       │
│                                               ┌──────────────────────────────┐   │
│                                               │  Backend API                 │   │
│                                               │  ASP.NET Core 9 (.NET 9)     │   │
│                                               │  Azure App Service           │   │
│                                               │  (P2v3, auto-scale 2–6)      │   │
│                                               └──┬──────┬──────────┬─────────┘   │
│                                                  │      │          │             │
│                              EF Core / TLS       │      │ SDK      │ SDK         │
│                              ┌───────────────────┘      │          │             │
│                              ▼                          ▼          ▼             │
│                    ┌──────────────────┐   ┌───────────────────┐  ┌────────────┐  │
│                    │  Azure SQL DB    │   │  Azure Blob       │  │  Azure     │  │ 
│                    │  EF Core 9       │   │  Storage (ZRS)    │  │  Notif.    │  │
│                    │  DuaProcesses    │   │  uploads/         │  │  Hubs      │  │
│                    │  DuaFields       │   │  results/         │  └────────────┘  │
│                    │  Users           │   │  templates/       │                  │
│                    │  Templates       │   └───────────────────┘                  │
│                    │  AuditEvents     │                                          │
│                    └──────────────────┘                                          │
│                                                                                  │
│  ┌────────────────────────┐   ┌────────────────────────┐   ┌───────────────────┐ │
│  │  Azure Key Vault       │   │  Azure Application     │   │  Azure AI         │ │
│  │  Secrets / API keys    │   │  Insights              │   │  Document Intel.  │ │
│  │  Connection strings    │   │  Logs / Metrics /      │   │  OCR + field      │ │
│  └────────────────────────┘   │ Traces / Alerts        │   │  extraction       │ │
│                               └────────────────────────┘   └───────────────────┘ │
└──────────────────────────────────────────────────────────────────────────────────┘
External:                                                                             
  Microsoft Entra ID  (identity provider / JWT issuer)
```

---

### Code Diagram — DuaGeneration Bounded Context

```
DuaGeneration/
│
├── «controller»
│   └── DuaController
│       uses ──► GenerateDuaCommandHandler
│       uses ──► GetDuaByIdQueryHandler
│       uses ──► DuaExportService
│       uses ──► DuaAccessGuard
│
├── «command handler»
│   └── GenerateDuaCommandHandler
│       uses ──► DuaOrchestrationService
│       uses ──► IDuaProcessRepository
│
├── «service»
│   ├── DuaOrchestrationService
│   │   uses ──► DocumentParserFactory          (DocumentIngestion context)
│   │   uses ──► SemanticMappingService
│   │   uses ──► ConfidenceScoreService
│   │   uses ──► DuaDocxGeneratorService
│   │   uses ──► INotificationAdapter           (Shared/Adapters)
│   │   uses ──► IDuaProcessRepository
│   │
│   ├── SemanticMappingService
│   │   uses ──► PermissionDefinitions          (field code table)
│   │
│   ├── ConfidenceScoreService
│   │   depends on ──► ConfidenceLevel          (domain enum)
│   │
│   ├── DuaDocxGeneratorService
│   │   uses ──► Azure Blob Storage             (via BlobStorageAdapter)
│   │
│   ├── DuaExportService
│   │   enforces ──► POL-001 (status check)
│   │   uses ──► BlobStorageAdapter.GenerateSasUrl()
│   │
│   └── DuaAccessGuard
│       enforces ──► POL-002 (edit before approval)
│       enforces ──► POL-003 (owner / reviewer / admin)
│
├── «domain model»
│   ├── DuaProcess          (aggregate root)
│   │   has ──► DuaField[]
│   │   has ──► DuaStatus   (enum)
│   │   has ──► ownerId, reviewerId
│   │
│   └── DuaField
│       has ──► ConfidenceLevel (enum: High, Medium, Low)
│       has ──► fieldCode, value, sourceFile, requiresReview
│
└── «repository interface»
    └── IDuaProcessRepository
        implemented by ──► EfRepository<DuaProcess>  (Shared/Repositories)
```

---

## Authors

* Camilo Allon Quesada
* Jose Pablo Chavarro Conde

## Initial References

* What is the DUA: [https://alianza-logistics.com/documento-unico-aduanero-2/](https://alianza-logistics.com/documento-unico-aduanero-2/)
* Official template (CR): [https://www.hacienda.go.cr/docs/Mensaje_TD_DUA-V3-17-12-03-2025.pdf](https://www.hacienda.go.cr/docs/Mensaje_TD_DUA-V3-17-12-03-2025.pdf)
* How to fill out the DUA (general guide): [https://gestionesenlinea.es/formulario-dua-documento-unico-administrativo/](https://gestionesenlinea.es/formulario-dua-documento-unico-administrativo/)
