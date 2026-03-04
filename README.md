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

## Authors

* Camilo Allon Quesada
* José Pablo Chavarro Conde

## Initial References

* What is the DUA: [https://alianza-logistics.com/documento-unico-aduanero-2/](https://alianza-logistics.com/documento-unico-aduanero-2/)
* Official template (CR): [https://www.hacienda.go.cr/docs/Mensaje_TD_DUA-V3-17-12-03-2025.pdf](https://www.hacienda.go.cr/docs/Mensaje_TD_DUA-V3-17-12-03-2025.pdf)
* How to fill out the DUA (general guide): [https://gestionesenlinea.es/formulario-dua-documento-unico-administrativo/](https://gestionesenlinea.es/formulario-dua-documento-unico-administrativo/)
