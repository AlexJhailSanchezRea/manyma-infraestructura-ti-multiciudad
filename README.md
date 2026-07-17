<div align="center">

# MANYMA

## Gestión Integral de Infraestructura TI Corporativa Multiciudad

Proyecto individual de diseño e implementación de una infraestructura empresarial centralizada, segmentada y conectada mediante VPN.

![Estado](https://img.shields.io/badge/Estado-Completado-success)
![Año](https://img.shields.io/badge/Año-2026-blue)
![Tipo](https://img.shields.io/badge/Proyecto-Individual-orange)
![Windows Server](https://img.shields.io/badge/Windows-Server-0078D4)
![Firewall](https://img.shields.io/badge/Firewall-pfSense-darkblue)
![Virtualización](https://img.shields.io/badge/Virtualización-VMware-yellow)

</div>

---

## Contenido

- [Descripción](#descripción)
- [Arquitectura](#arquitectura)
- [Tecnologías](#tecnologías)
- [Implementación](#implementación)
- [Validaciones](#validaciones)
- [Evidencias](#evidencias)
- [Estructura del repositorio](#estructura-del-repositorio)
- [Seguridad](#seguridad)
- [Autor](#autor)

---

## Descripción

MANYMA representa una infraestructura TI corporativa para una organización con presencia en varias ciudades.

El laboratorio integra administración de usuarios y equipos, servicios de red, almacenamiento, impresión, actualizaciones, segmentación, seguridad perimetral y comunicación segura entre sedes.

La solución fue implementada completamente en un entorno virtual utilizando Windows Server, VMware y pfSense.

### Información general

| Característica | Detalle |
|---|---|
| Modalidad | Proyecto académico individual |
| Año | 2026 |
| Duración aproximada | 3 semanas |
| Plataforma | VMware Workstation |
| Sistema principal | Windows Server |
| Firewall | pfSense |
| Alcance | Sede principal y sedes remotas |
| Comunicación | VPN entre sedes |
| Estado | Completado |

---

## Arquitectura

```mermaid
flowchart TD
    USERS[Usuarios y estaciones de trabajo]

    subgraph MAIN[Sede principal]
        AD[Active Directory]
        DNS[DNS]
        DHCP[DHCP]
        GPO[GPO]
        FILE[File Server y RAID]
        PRINT[Print Server]
        WSUS[WSUS]
    end

    USERS --> SWITCH[Switches y VLAN]
    SWITCH --> PFSENSE[pfSense<br/>Firewall, routing y VPN]

    PFSENSE --> MAIN
    PFSENSE --> VPN[Túneles VPN]

    VPN --> SITE1[Sede remota 1]
    VPN --> SITE2[Sede remota 2]
    VPN --> SITE3[Sede remota 3]

    MAIN --> BACKUP[Respaldos y continuidad]
```

La arquitectura utiliza pfSense como punto central de enrutamiento, segmentación, filtrado y comunicación entre las diferentes redes.

---

## Tecnologías

| Área | Tecnologías y servicios |
|---|---|
| Sistemas operativos | Windows Server, Windows 10, Windows 11 y Linux |
| Virtualización | VMware Workstation |
| Identidad | Active Directory Domain Services |
| Servicios de red | DNS y DHCP |
| Administración | Group Policy Objects |
| Almacenamiento | File Server y RAID |
| Impresión | Print Server |
| Actualizaciones | WSUS |
| Firewall | pfSense |
| Segmentación | VLAN y VLSM |
| Acceso remoto | OpenVPN |
| Seguridad | Reglas de firewall y pfBlockerNG |
| Gestión de tráfico | QoS |

---

## Implementación

### Identidad y control de acceso

- Instalación de Active Directory Domain Services.
- Creación del dominio corporativo.
- Organización mediante unidades organizativas.
- Creación de usuarios, grupos y equipos.
- Unión de estaciones de trabajo al dominio.
- Asignación de permisos según funciones.

### Servicios de red

- Configuración de DNS.
- Configuración de DHCP.
- Creación de ámbitos, exclusiones y reservas.
- Diseño de direccionamiento mediante VLSM.
- Validación de conectividad y resolución de nombres.

### Políticas y administración centralizada

- Creación y aplicación de políticas GPO.
- Restricción de configuraciones no autorizadas.
- Administración de equipos del dominio.
- Gestión de actualizaciones mediante WSUS.

### Almacenamiento e impresión

- Configuración de File Server.
- Creación de carpetas compartidas.
- Aplicación de permisos según grupos.
- Implementación de almacenamiento RAID.
- Configuración de Print Server.

### Redes y seguridad

- Instalación y configuración de pfSense.
- Creación de interfaces y redes internas.
- Segmentación mediante VLAN.
- Configuración de reglas de firewall.
- Implementación de OpenVPN.
- Comunicación segura entre sedes.
- Filtrado mediante pfBlockerNG.
- Priorización de tráfico mediante QoS.

---

## Validaciones

| Prueba realizada | Resultado |
|---|---|
| Unión de equipos al dominio | ✅ Correcto |
| Autenticación de usuarios | ✅ Correcto |
| Resolución de nombres DNS | ✅ Correcto |
| Asignación automática mediante DHCP | ✅ Correcto |
| Aplicación de políticas GPO | ✅ Correcto |
| Acceso a carpetas compartidas | ✅ Correcto |
| Aplicación de permisos por grupo | ✅ Correcto |
| Impresión en red | ✅ Correcto |
| Comunicación entre VLAN autorizadas | ✅ Correcto |
| Bloqueo de tráfico no permitido | ✅ Correcto |
| Comunicación mediante VPN | ✅ Correcto |
| Administración de actualizaciones | ✅ Correcto |
| Disponibilidad del almacenamiento | ✅ Correcto |

---

## Resultados

- Administración centralizada de usuarios, grupos y equipos.
- Implementación de servicios corporativos con Windows Server.
- Segmentación de áreas mediante VLAN.
- Comunicación segura entre sedes.
- Control de acceso mediante reglas de firewall.
- Gestión centralizada de archivos, impresoras y actualizaciones.
- Implementación de almacenamiento con tolerancia a fallos.
- Validación técnica de conectividad, acceso y disponibilidad.
- Documentación completa de la infraestructura.

---

## Evidencias

Las capturas y validaciones se encuentran organizadas por servicio:

| Componente | Evidencias |
|---|---|
| Active Directory | [Ver evidencias](evidencias/active-directory/) |
| DNS y DHCP | [Ver evidencias](evidencias/dns-dhcp/) |
| GPO | [Ver evidencias](evidencias/gpo/) |
| File Server y RAID | [Ver evidencias](evidencias/file-server/) |
| Print Server | [Ver evidencias](evidencias/print-server/) |
| WSUS | [Ver evidencias](evidencias/wsus/) |
| pfSense y VLAN | [Ver evidencias](evidencias/pfsense-vlan/) |
| VPN entre sedes | [Ver evidencias](evidencias/vpn/) |

> Las evidencias serán incorporadas progresivamente al repositorio.

---

## Documentación

| Documento | Contenido |
|---|---|
| [Arquitectura](docs/arquitectura.md) | Diseño general de la infraestructura |
| [Direccionamiento IP](docs/direccionamiento-ip.md) | Redes, subredes y asignación de direcciones |
| [Servicios de Windows Server](configuraciones/servicios-windows-server.md) | Configuración de servicios corporativos |
| [Políticas GPO](configuraciones/politicas-gpo.md) | Políticas implementadas |
| [Reglas de pfSense](configuraciones/reglas-pfsense.md) | Reglas de acceso y segmentación |
| [Informe completo](docs/informe-proyecto.pdf) | Documentación académica del proyecto |

---

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
│   ├── politicas-gpo.md
│   └── reglas-pfsense.md
└── evidencias/
    ├── active-directory/
    ├── dns-dhcp/
    ├── gpo/
    ├── file-server/
    ├── print-server/
    ├── wsus/
    ├── pfsense-vlan/
    └── vpn/
```

---

## Mejoras futuras

- Implementar monitoreo centralizado de servidores.
- Automatizar respaldos y pruebas de recuperación.
- Agregar autenticación multifactor.
- Incorporar redundancia para servicios críticos.
- Centralizar registros mediante una solución SIEM.
- Integrar servicios híbridos o en la nube.

---

## Seguridad

Este proyecto fue desarrollado en un entorno académico y virtual.

Por seguridad, el repositorio no publica:

- Contraseñas.
- Credenciales administrativas.
- Claves privadas.
- Direcciones IP públicas.
- Datos personales.
- Archivos con secretos.
- Información de infraestructura real.

Las direcciones IP privadas, nombres de dominio y configuraciones corresponden únicamente al laboratorio.

---

## Autor

**Alex Jhail Sánchez Rea**  
Egresado de Ingeniería de Sistemas

[LinkedIn](https://www.linkedin.com/in/alexjhailsanchezrea) · [GitHub](https://github.com/AlexJhailSanchezRea)

---

<div align="center">

Proyecto desarrollado como parte del Examen de Grado de Ingeniería de Sistemas.

</div>
