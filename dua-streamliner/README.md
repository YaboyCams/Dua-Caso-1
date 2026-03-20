# DUA Streamliner — Intelligent System for Automated DUA Generation

## Project Overview

The DUA Streamliner project aims to automate the generation of the Single Customs Document (DUA) by processing various document formats. This project is designed to reduce manual effort, minimize errors, and streamline the customs documentation process.

## Project Structure

The project is organized into a structured directory layout to facilitate development and maintainability:

```
dua-streamliner
├── src
│   ├── app
│   │   ├── login
│   │   ├── dashboard
│   │   ├── template-selection
│   │   ├── processing
│   │   ├── result
│   │   └── api
│   ├── components
│   │   ├── atoms
│   │   ├── molecules
│   │   ├── organisms
│   │   ├── templates
│   │   └── pages
│   ├── hooks
│   ├── services
│   │   ├── auth
│   │   ├── documents
│   │   ├── notifications
│   │   └── logging
│   ├── api-clients
│   │   ├── auth
│   │   ├── document
│   │   ├── notifications
│   │   └── logging
│   ├── settings
│   ├── models
│   │   ├── auth
│   │   ├── documents
│   │   ├── dua
│   │   ├── notifications
│   │   └── shared
│   ├── data-validation
│   ├── state-management
│   ├── utils
│   ├── exception-handling
│   ├── logs
│   ├── patterns
│   │   ├── builder
│   │   ├── strategy
│   │   ├── observer
│   │   ├── adapter
│   │   └── singleton
│   ├── document-parsers
│   └── types
├── package.json
├── tsconfig.json
├── .gitignore
└── README.md
```

## Features

- **Document Processing**: Automatically reads and extracts data from various document formats (Excel, Word, PDF, images).
- **Data Mapping**: Maps extracted data to the official DUA fields.
- **Validation**: Applies consistency checks and flags ambiguities in the extracted data.
- **Result Generation**: Generates a pre-filled DUA document with confidence indicators.

## Technology Stack

- **Frontend**: React.js, TypeScript
- **Backend**: Node.js
- **State Management**: Redux
- **Testing**: Jest, Playwright
- **Cloud Services**: Azure Cloud Services
- **CI/CD**: Azure DevOps

## Getting Started

1. Clone the repository.
2. Install dependencies using npm or yarn.
3. Configure environment variables as needed.
4. Run the application locally.

## Authors

- Camilo Allon Quesada
- Jose Pablo Chavarro Conde

## License

This project is licensed under the MIT License. See the LICENSE file for details.