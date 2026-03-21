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
| Pages | [`src/components/pages/`](src/components/pages/) | [`pages.css`](src/components/pages/pages.css) |

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
-Time-based OTP (TOTP)
-SMS One-Time Password
-Voice Call OTP

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

## Authors

* Camilo Allon Quesada
* Jose Pablo Chavarro Conde

## Initial References

* What is the DUA: [https://alianza-logistics.com/documento-unico-aduanero-2/](https://alianza-logistics.com/documento-unico-aduanero-2/)
* Official template (CR): [https://www.hacienda.go.cr/docs/Mensaje_TD_DUA-V3-17-12-03-2025.pdf](https://www.hacienda.go.cr/docs/Mensaje_TD_DUA-V3-17-12-03-2025.pdf)
* How to fill out the DUA (general guide): [https://gestionesenlinea.es/formulario-dua-documento-unico-administrativo/](https://gestionesenlinea.es/formulario-dua-documento-unico-administrativo/)
