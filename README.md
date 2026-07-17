<div align="center">

# MANYMA – Infraestructura TI Corporativa Multiciudad

### Diseño e implementación de una infraestructura empresarial centralizada, segmentada y conectada mediante VPN

![Estado](https://img.shields.io/badge/Estado-Completado-brightgreen)
![Tipo](https://img.shields.io/badge/Tipo-Proyecto%20académico-blue)
![Plataforma](https://img.shields.io/badge/Plataforma-VMware-orange)
![Windows Server](https://img.shields.io/badge/Windows-Server-0078D4)
![Firewall](https://img.shields.io/badge/Firewall-pfSense-darkblue)

</div>

---

## Descripción general

MANYMA es un proyecto académico de infraestructura TI orientado a simular el funcionamiento tecnológico de una organización con presencia en varias ciudades.

La solución integra administración centralizada de usuarios y equipos, servicios corporativos, segmentación de red, seguridad perimetral, almacenamiento, actualizaciones y comunicación segura entre sedes.

El laboratorio fue implementado en un entorno virtual controlado, aplicando conceptos de administración de sistemas, redes, virtualización, seguridad y continuidad operativa.

## Información del proyecto

| Característica | Detalle |
|---|---|
| Tipo de proyecto | Infraestructura TI corporativa |
| Modalidad | Proyecto académico individual |
| Año | 2026 |
| Entorno | Laboratorio virtual |
| Plataforma | VMware Workstation |
| Sistema principal | Windows Server |
| Firewall | pfSense |
| Alcance | Sede principal y sedes remotas |
| Comunicación entre sedes | VPN |
| Estado | Completado |

## Objetivo general

Diseñar e implementar una infraestructura TI segura, escalable y administrable que permita centralizar usuarios, equipos y servicios, además de proporcionar conectividad segura entre diferentes sedes.

## Objetivos específicos

- Centralizar la administración de usuarios y equipos.
- Configurar servicios corporativos de red.
- Organizar usuarios mediante grupos y unidades organizativas.
- Aplicar políticas de seguridad mediante GPO.
- Segmentar la infraestructura mediante VLAN.
- Diseñar el direccionamiento IP utilizando VLSM.
- Conectar las sedes mediante VPN.
- Proteger el perímetro de red mediante pfSense.
- Gestionar archivos, impresoras y actualizaciones.
- Validar la disponibilidad y conectividad de los servicios.

## Arquitectura general

```text
                         ┌─────────────────────────┐
                         │     Sede principal      │
                         │                         │
                         │  Windows Server         │
                         │  AD DS / DNS / DHCP     │
                         │  GPO / WSUS             │
                         │  File y Print Server    │
                         └────────────┬────────────┘
                                      │
                               VLAN y enrutamiento
                                      │
                              ┌───────▼───────┐
                              │    pfSense    │
                              │ Firewall/VPN  │
                              └───────┬───────┘
                                      │
                               Túneles VPN
                     ┌────────────────┼────────────────┐
                     │                │                │
               ┌─────▼─────┐    ┌─────▼─────┐    ┌─────▼─────┐
               │ Sede remota│    │ Sede remota│    │ Sede remota│
               │ Usuarios   │    │ Usuarios   │    │ Usuarios   │
               │ y equipos  │    │ y equipos  │    │ y equipos  │
               └────────────┘    └────────────┘    └────────────┘
```

## Tecnologías utilizadas

| Categoría | Tecnologías |
|---|---|
| Sistemas operativos | Windows Server, Windows 10, Windows 11 y Linux |
| Virtualización | VMware Workstation |
| Directorio y usuarios | Active Directory Domain Services |
| Servicios de red | DNS y DHCP |
| Políticas | Group Policy Objects |
| Almacenamiento | File Server y RAID |
| Impresión | Print Server |
| Actualizaciones | WSUS |
| Firewall | pfSense |
| Segmentación | VLAN y VLSM |
| Acceso remoto | OpenVPN |
| Seguridad adicional | pfBlockerNG y reglas de firewall |
| Gestión del tráfico | QoS |

## Servicios implementados

| Servicio | Función dentro de la infraestructura |
|---|---|
| Active Directory | Administración centralizada de usuarios, grupos y equipos |
| DNS | Resolución de nombres dentro del dominio |
| DHCP | Asignación automática de direcciones IP |
| GPO | Aplicación centralizada de configuraciones y políticas |
| File Server | Almacenamiento y acceso a carpetas compartidas |
| Print Server | Administración centralizada de impresoras |
| RAID | Disponibilidad y protección del almacenamiento |
| WSUS | Gestión centralizada de actualizaciones |
| pfSense | Firewall, enrutamiento, control de acceso y VPN |
| OpenVPN | Comunicación segura entre sedes |
| VLAN | Separación lógica de áreas y dispositivos |
| pfBlockerNG | Filtrado y protección adicional del tráfico |

## Implementación realizada

### Administración de identidad

- Instalación de Active Directory Domain Services.
- Creación del dominio corporativo.
- Configuración de unidades organizativas.
- Creación de usuarios y grupos.
- Unión de estaciones de trabajo al dominio.
- Asignación de permisos según funciones.

### Servicios de red

- Configuración de DNS.
- Implementación de DHCP.
- Creación de ámbitos y reservas.
- Diseño del direccionamiento IP mediante VLSM.
- Validación de resolución de nombres y conectividad.

### Políticas y administración

- Creación y aplicación de políticas GPO.
- Restricción de configuraciones no autorizadas.
- Administración centralizada de estaciones de trabajo.
- Gestión de actualizaciones mediante WSUS.

### Archivos, almacenamiento e impresión

- Creación de carpetas compartidas.
- Aplicación de permisos de acceso.
- Implementación de almacenamiento RAID.
- Configuración de Print Server.
- Validación de acceso según grupos de usuarios.

### Redes y seguridad

- Instalación y configuración de pfSense.
- Creación de interfaces y redes internas.
- Segmentación mediante VLAN.
- Configuración de reglas de firewall.
- Implementación de túneles VPN.
- Configuración de OpenVPN.
- Aplicación de filtrado mediante pfBlockerNG.
- Priorización de tráfico mediante QoS.

## Validaciones realizadas

| Prueba | Resultado esperado |
|---|---|
| Unión de equipos al dominio | Equipo registrado y autenticado correctamente |
| Resolución DNS | Resolución correcta del dominio y servidores |
| Asignación DHCP | Entrega automática de IP, gateway y DNS |
| Aplicación de GPO | Políticas aplicadas según usuario o equipo |
| Acceso a archivos | Acceso permitido según grupo y permisos |
| Impresión en red | Impresora disponible para usuarios autorizados |
| Comunicación entre VLAN | Acceso permitido únicamente por reglas definidas |
| Reglas de firewall | Bloqueo de tráfico no autorizado |
| Conectividad VPN | Comunicación segura entre sedes |
| Actualizaciones WSUS | Equipos administrados desde el servidor |
| Disponibilidad del almacenamiento | Acceso a datos durante las pruebas realizadas |

## Resultados principales

- Administración centralizada de usuarios y equipos.
- Integración de servicios corporativos en Windows Server.
- Segmentación lógica de la infraestructura.
- Comunicación segura entre sedes.
- Control del tráfico mediante reglas de firewall.
- Gestión centralizada de archivos, impresoras y actualizaciones.
- Validación de conectividad, acceso y disponibilidad.
- Documentación técnica de la implementación.

## Estructura del repositorio

```text
manyma-infraestructura-ti-multiciudad/
├── README.md
├── docs/
│   ├── arquitectura.md
│   ├── direccionamiento-ip.md
│   └── informe-proyecto.pdf
├── diagramas/
│   ├── arquitectura-general.png
│   └── topologia-red.png
├── configuraciones/
│   ├── active-directory.md
│   ├── servicios-windows-server.md
│   ├── reglas-pfsense.md
│   └── politicas-gpo.md
└── evidencias/
    ├── active-directory/
    ├── dns-dhcp/
    ├── file-server/
    ├── pfsense-vlan/
    └── vpn/
```

## Evidencias

Las evidencias técnicas serán organizadas por componente:

- Active Directory, usuarios y grupos.
- Configuración de DNS y DHCP.
- Aplicación de políticas GPO.
- File Server y permisos.
- Print Server.
- RAID y almacenamiento.
- WSUS.
- VLAN y segmentación.
- Reglas de pfSense.
- Comunicación mediante VPN.

> Las capturas se agregarán progresivamente en la carpeta `evidencias`.

## Próximas mejoras

- Incorporar monitoreo centralizado de servidores y dispositivos.
- Automatizar respaldos y pruebas de restauración.
- Implementar autenticación multifactor.
- Agregar redundancia para servicios críticos.
- Centralizar registros mediante una solución SIEM.
- Incorporar servicios híbridos o en la nube.

## Consideraciones de seguridad

Este repositorio presenta una implementación académica desarrollada en un entorno virtual.

Por seguridad, no se publican:

- Contraseñas.
- Claves privadas.
- Credenciales administrativas.
- Datos personales.
- Direcciones IP públicas.
- Archivos con secretos o información sensible.

Las direcciones IP privadas y nombres utilizados corresponden únicamente al laboratorio.

## Autor

**Alex Jhail Sánchez Rea**  
Egresado de Ingeniería de Sistemas

[LinkedIn](https://www.linkedin.com/in/alexjhailsanchezrea) · [GitHub](https://github.com/AlexJhailSanchezRea)
