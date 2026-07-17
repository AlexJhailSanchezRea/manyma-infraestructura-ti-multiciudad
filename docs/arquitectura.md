# Arquitectura de la infraestructura

## Descripción general

La infraestructura MANYMA fue diseñada para representar una organización con una sede principal y diferentes sedes remotas.

La sede principal centraliza los servicios corporativos, mientras que las sedes remotas se conectan de manera segura mediante túneles VPN.

## Componentes principales

| Componente | Función |
|---|---|
| Windows Server | Administración de los servicios corporativos |
| Active Directory | Gestión centralizada de usuarios, grupos y equipos |
| DNS | Resolución de nombres dentro del dominio |
| DHCP | Asignación automática de direcciones IP |
| GPO | Aplicación de políticas de seguridad y configuración |
| File Server | Almacenamiento y distribución de archivos |
| Print Server | Administración centralizada de impresoras |
| WSUS | Gestión de actualizaciones de Windows |
| pfSense | Firewall, enrutamiento, segmentación y VPN |
| VMware Workstation | Plataforma de virtualización del laboratorio |

## Diseño lógico

```mermaid
flowchart LR
    USERS[Usuarios y equipos]

    USERS --> VLAN[VLAN por áreas]
    VLAN --> FW[pfSense]

    FW --> SERVERS[Servicios Windows Server]
    FW --> VPN[Túneles VPN]

    SERVERS --> AD[Active Directory]
    SERVERS --> DNS[DNS]
    SERVERS --> DHCP[DHCP]
    SERVERS --> FILE[File Server]
    SERVERS --> WSUS[WSUS]

    VPN --> SITE1[Sede remota 1]
    VPN --> SITE2[Sede remota 2]
    VPN --> SITE3[Sede remota 3]
