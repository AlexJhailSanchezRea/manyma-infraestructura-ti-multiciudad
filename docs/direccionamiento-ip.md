# Plan de direccionamiento IP

## Descripción

La infraestructura MANYMA utiliza segmentación lógica mediante VLAN y direccionamiento VLSM para separar usuarios, servidores, impresoras, regionales y acceso remoto.

pfSense funciona como gateway de cada segmento, router entre redes y punto central para la aplicación de reglas de firewall.

Los clientes reciben su configuración de red desde un servidor DHCP centralizado. Las solicitudes originadas en otras VLAN son reenviadas mediante DHCP Relay configurado en pfSense.

---

## Tabla general de direccionamiento

| Segmento | Área o función | Red / Prefijo | Gateway | Asignación |
|---|---|---|---|---|
| VLAN20 | Ventas | `192.168.50.0/26` | `192.168.50.1` | DHCP |
| VLAN10 | Administración | `192.168.50.64/27` | `192.168.50.65` | DHCP |
| VLAN100 | Servidores | `192.168.50.224/28` | `192.168.50.225` | Estática |
| VLAN70 | Sistemas TI | `192.168.51.64/27` | `192.168.51.65` | DHCP |
| VLAN140 | Marketing | `192.168.51.160/28` | `192.168.51.161` | DHCP |
| VLAN110 | Impresoras | `192.168.51.192/27` | `192.168.51.193` | Reservas o IP estática |
| Regional | La Paz | `192.168.60.0/26` | `192.168.60.1` | DHCP |
| Regional | Cochabamba | `192.168.70.0/25` | `192.168.70.1` | DHCP |
| OpenVPN | Acceso remoto | `10.10.10.0/24` | `10.10.10.1` | VPN |
| WAN laboratorio | Acceso externo VMware | `192.168.183.0/24` | VMware NAT | NAT |

---

## Rangos DHCP

| Segmento | Rango asignable |
|---|---|
| VLAN20 Ventas | `192.168.50.7` – `192.168.50.62` |
| VLAN10 Administración | `192.168.50.71` – `192.168.50.94` |
| VLAN70 Sistemas TI | `192.168.51.71` – `192.168.51.94` |
| VLAN140 Marketing | `192.168.51.167` – `192.168.51.174` |
| Regional La Paz | `192.168.60.7` – `192.168.60.62` |
| Regional Cochabamba | `192.168.70.7` – `192.168.70.126` |

La VLAN100 utiliza direcciones estáticas porque contiene servicios críticos como controladores de dominio, DNS, DHCP y File Server.

---

## Correspondencia entre VMware y segmentos

| Red VMware | Segmento | Red |
|---|---|---|
| VMnet1 | WAN / Internet del laboratorio | `192.168.183.0/24` |
| VMnet2 | VLAN100 Servidores | `192.168.50.224/28` |
| VMnet3 | VLAN10 Administración | `192.168.50.64/27` |
| VMnet4 | VLAN20 Ventas | `192.168.50.0/26` |
| VMnet5 | VLAN70 Sistemas TI | `192.168.51.64/27` |
| VMnet6 | VLAN140 Marketing | `192.168.51.160/28` |
| VMnet7 | Regional La Paz | `192.168.60.0/26` |
| VMnet8 | Regional Cochabamba | `192.168.70.0/25` |
| Segmento lógico | VLAN110 Impresoras | `192.168.51.192/27` |
| Túnel lógico | OpenVPN | `10.10.10.0/24` |

Las redes internas fueron configuradas como redes privadas del laboratorio para evitar el acceso directo desde el equipo físico.

---

## Direccionamiento de impresoras

| Área | Dirección IP | Cola compartida |
|---|---|---|
| Administración | `192.168.51.194` | `IMP_ADMIN_01` |
| Ventas | `192.168.51.195` | `IMP_VENTAS_01` |
| Marketing | `192.168.51.196` | `IMP_MARKETING_01` |
| Sistemas | `192.168.51.197` | `IMP_SISTEMAS_01` |

Las impresoras fueron simuladas mediante puertos TCP/IP y administradas desde el servidor de impresión `SRV-SERVICIOS01`.

---

## Funcionamiento de DHCP Relay

```mermaid
sequenceDiagram
    participant Cliente
    participant pfSense
    participant DHCP01

    Cliente->>pfSense: Solicitud DHCP Discover
    pfSense->>DHCP01: Reenvío mediante DHCP Relay
    DHCP01->>pfSense: Oferta de dirección IP
    pfSense->>Cliente: Entrega de configuración de red
