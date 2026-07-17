# Evidencias técnicas

Esta sección contiene las capturas y validaciones principales de la infraestructura MANYMA.

Las evidencias están organizadas por servicio para facilitar la revisión de la implementación.

## Componentes documentados

| N.º | Componente | Evidencia esperada | Estado |
|---:|---|---|---|
| 1 | Active Directory | Dominio, estructura organizativa y roles FSMO | ✅ Completado |
| 2 | DNS y DHCP | Zonas DNS, ámbitos y asignación de IP | Pendiente |
| 3 | Políticas GPO | Políticas creadas y aplicadas | Pendiente |
| 4 | File Server | Carpetas compartidas y permisos | Pendiente |
| 5 | RAID | Configuración y disponibilidad de discos | Pendiente |
| 6 | Print Server | Impresoras y colas compartidas | Pendiente |
| 7 | WSUS | Equipos y actualizaciones administradas | Pendiente |
| 8 | pfSense | Interfaces, reglas y segmentación | Pendiente |
| 9 | VLAN | Separación y comunicación controlada | Pendiente |
| 10 | VPN | Conectividad entre sedes | Pendiente |

## Organización

```text
evidencias/
├── active-directory/
├── dns-dhcp/
├── gpo/
├── file-server/
├── raid/
├── print-server/
├── wsus/
├── pfsense-vlan/
└── vpn/
