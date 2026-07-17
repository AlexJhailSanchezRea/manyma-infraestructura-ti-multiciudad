# MANYMA – Infraestructura TI Corporativa Multiciudad

Proyecto académico orientado al diseño e implementación de una infraestructura tecnológica corporativa para una organización con varias sedes, utilizando servicios de Windows Server, segmentación de redes, virtualización, seguridad perimetral y acceso remoto seguro.

## Descripción

El proyecto MANYMA simula una infraestructura empresarial multiciudad administrada de forma centralizada. La solución permite gestionar usuarios, equipos, servicios de red, almacenamiento, actualizaciones y conectividad entre sedes.

La arquitectura fue implementada en un entorno virtual controlado, aplicando buenas prácticas de administración de sistemas, redes, seguridad y continuidad operativa.

## Objetivo

Diseñar e implementar una infraestructura TI escalable, segura y administrable que permita:

- Centralizar la gestión de usuarios y equipos.
- Proporcionar servicios de red corporativos.
- Segmentar la infraestructura mediante VLAN.
- Conectar las diferentes sedes mediante VPN.
- Gestionar archivos, impresoras y actualizaciones.
- Aplicar políticas de seguridad y control de acceso.
- Mejorar la disponibilidad y continuidad de los servicios.

## Tecnologías utilizadas

### Sistemas y virtualización

- Windows Server
- Windows 10 y Windows 11
- VMware Workstation
- Linux

### Servicios de infraestructura

- Active Directory Domain Services
- DNS
- DHCP
- Group Policy Objects
- File Server
- Print Server
- WSUS
- RAID

### Redes y seguridad

- pfSense
- VLAN y VLSM
- OpenVPN
- Firewall y reglas de acceso
- Enrutamiento entre redes
- QoS
- pfBlockerNG

## Arquitectura implementada

La infraestructura contempla una sede principal y sedes remotas conectadas mediante redes privadas virtuales.

```text
Usuarios y estaciones de trabajo
              │
              ▼
       Switches y VLAN
              │
              ▼
           pfSense
       Firewall y VPN
              │
     ┌────────┴────────┐
     ▼                 ▼
Windows Server      Sedes remotas
AD, DNS, DHCP       mediante VPN
GPO, WSUS
File Server
