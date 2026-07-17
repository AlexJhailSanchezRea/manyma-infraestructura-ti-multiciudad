# Evidencias técnicas

Esta sección reúne las principales evidencias de implementación y validación de la infraestructura TI corporativa MANYMA.

## Componentes documentados

| N.º | Componente | Evidencia principal | Estado |
|---:|---|---|---|
| 1 | [Active Directory](active-directory/) | Arquitectura, unidades organizativas y roles FSMO | ✅ Completado |
| 2 | [DNS y DHCP](dns-dhcp/) | DNS interno, ámbitos, DHCP Relay y asignación de IP | ✅ Completado |
| 3 | [pfSense, VLAN y VPN](pfsense-vlan-vpn/) | Segmentación, reglas de firewall y OpenVPN | ✅ Completado |
| 4 | [GPO, File Server y RAID](gpo-file-server-raid/) | Políticas, permisos, acceso denegado y almacenamiento | ✅ Completado |

## Resumen de validaciones

| Área | Validación |
|---|---|
| Administración de identidades | Dominio, usuarios, grupos, equipos y unidades organizativas |
| Servicios de red | Resolución DNS y asignación automática mediante DHCP |
| Seguridad y segmentación | VLAN, reglas de pfSense y bloqueo de tráfico |
| Acceso remoto | Comunicación segura mediante OpenVPN |
| Administración centralizada | Aplicación de políticas GPO |
| Gestión de archivos | Carpetas compartidas y permisos mediante grupos |
| Almacenamiento | Storage Spaces y RAID 5 con paridad |

## Organización del repositorio

```text
evidencias/
├── active-directory/
├── dns-dhcp/
├── pfsense-vlan-vpn/
└── gpo-file-server-raid/
