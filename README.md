# DUA Streamliner — Sistema Inteligente para la Generación Automatizada del DUA

## Problema
El Documento Único Aduanero (DUA) requiere completar múltiples campos basados en documentos heterogéneos (facturas, listas de empaque, certificados, conocimientos de embarque, pólizas, permisos, etc.).  
Hoy, este proceso suele hacerse manualmente, es repetitivo, propenso a errores y depende del conocimiento experto, lo que puede causar retrasos, multas o rechazos.

## Objetivo del proyecto
Diseñar una solución que, a partir de una carpeta con documentos (Excel, Word, PDF e imágenes escaneadas), sea capaz de:
1. Leer y extraer contenido multiformato (incluyendo OCR para escaneos).
2. Identificar semánticamente datos aduaneros relevantes.
3. Mapear automáticamente los datos a las casillas oficiales del DUA.
4. Aplicar validaciones básicas de coherencia y marcar ambigüedades.
5. Generar un Word (.docx) del DUA prellenado con códigos de confianza:
   - Verde: alta confianza
   - Amarillo: confianza media
   - Rojo: requiere revisión

## Alcance (por ahora)
Este repositorio contiene el **diseño** del sistema (arquitectura, modelos de datos, UX/UI, calidad, deployment/CI-CD, seguridad, observability, etc.).  
No incluye implementación funcional en esta etapa.

## Autores
- Camilo Allon Quesada
- José Pablo Chavarro Conde

## Referencias iniciales
- Qué es DUA: https://alianza-logistics.com/documento-unico-aduanero-2/
- Template oficial (CR): https://www.hacienda.go.cr/docs/Mensaje_TD_DUA-V3-17-12-03-2025.pdf
- Cómo llenar el DUA (guía general): https://gestionesenlinea.es/formulario-dua-documento-unico-administrativo/