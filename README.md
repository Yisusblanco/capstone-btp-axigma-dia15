# Capstone — Gestión de Pedidos con Aprobación Inteligente

Material del capstone final del curso **BTP Axigma** (Día 14–15), preparado por Jesús Alexander Blanco Orta (Velion Tech SAC — Axigma).

Aplicación de gestión de órdenes de venta con aprobación mediante workflow, integrando cuatro capas de SAP BTP: app móvil SAP MDK, backend SAP CAP (Node.js) sobre Cloud Foundry / HANA Cloud, orquestación con SAP Build Process Automation (BPA), y notificaciones vía SAP Integration Suite (CPI).

## Estructura del repositorio

```
.
├── docs/               Documentación técnica del capstone (Word)
│   ├── 01-mdk-documentacion.docx        Arquitectura, app MDK, flujo end-to-end, catálogo de errores
│   ├── 02-backend-documentacion.docx    Modelo CDS, servicio OData, seguridad XSUAA, despliegue MTA
│   └── 03-btp-configuraciones.docx      Configuraciones en el Cockpit de SAP BTP (destinations, roles, servicios)
├── config/
│   └── destination-btp-capstone-orders-srv.json   Export de la Destination usada por BPA para consumir el backend
└── artifacts/
    ├── BPA_Capstone_Order_Approval_1.0.2.mtar             Paquete del workflow de aprobación (SAP Build Process Automation)
    └── Export_Integration_Suites_Capacitacion_Axigma.zip  Export del iFlow de notificación (SAP Integration Suite / CPI)
```

## Cómo usar este material

1. Lee la documentación en el orden sugerido: `01-mdk-documentacion.docx` → `02-backend-documentacion.docx` → `03-btp-configuraciones.docx`.
2. Importa `artifacts/BPA_Capstone_Order_Approval_1.0.2.mtar` en **SAP Build Process Automation** para desplegar el workflow de aprobación.
3. Importa `artifacts/Export_Integration_Suites_Capacitacion_Axigma.zip` en **SAP Integration Suite** para el iFlow de notificación por correo.
4. Usa `config/destination-btp-capstone-orders-srv.json` como referencia para crear la Destination hacia el backend CAP en tu propio subaccount BTP (ajusta URL, client ID/secret y token service según tu trial).

## Arquitectura general

- **Frontend móvil:** SAP Mobile Development Kit (MDK), cliente Android vía SAP Mobile Services.
- **Backend:** servicio CAP (Node.js) sobre Cloud Foundry, OData V2, persistencia en HANA Cloud.
- **Orquestación:** SAP Build Process Automation (BPA), disparada vía API REST desde el backend.
- **Notificación:** SAP Integration Suite (CPI), envío de decisión de aprobación/rechazo por correo.

## Repositorio

https://github.com/Yisusblanco/capstone-btp-axigma-dia15

Clona con:

```
git clone https://github.com/Yisusblanco/capstone-btp-axigma-dia15.git
```

---
Curso BTP Axigma — Julio 2026
