# DHCP & NAT Lab

Laboratorio de administración de redes centrado en la configuración de un servidor DHCP, enrutamiento IPv4 y NAT mediante Ubuntu Server 24.04 LTS.

El proyecto implementa dos ámbitos DHCP en redes internas independientes, con asignación dinámica de direcciones IP, reservas, opciones de red y conectividad hacia Internet.

## Objetivos

- Configurar las interfaces de red del servidor.
- Habilitar el reenvío de paquetes IPv4.
- Configurar NAT mediante iptables.
- Instalar y administrar ISC DHCP Server.
- Crear dos ámbitos DHCP con rangos dinámicos y reservas.
- Distribuir parámetros de red, DNS y rutas estáticas.
- Comprobar la conectividad y analizar el tráfico DHCP.

## Entorno de laboratorio

| Componente | Configuración |
|---|---|
| Servidor | Ubuntu Server 24.04 LTS |
| Cliente | Windows Server 2022 |
| Servicio DHCP | ISC DHCP Server |
| Administración | Webmin |
| DNS | BIND9 |
| Análisis de tráfico | Wireshark |
| Virtualización | Máquinas virtuales |

## Topología de red

El servidor dispone de tres interfaces de red:

| Interfaz | Red | Dirección IP |
|---|---|---|
| enp0s3 | NAT | Automática mediante DHCP |
| enp0s8 | intranet1 | 10.26.102.100/24 |
| enp0s9 | intranet2 | 172.26.102.100/24 |

El cliente Windows Server 2022 dispone de dos adaptadores conectados a las redes internas, configurados para obtener automáticamente sus parámetros de red.

## Servicios y configuración implementados

**DHCP:** configuración de dos ámbitos independientes, con rangos dinámicos, reservas de direcciones MAC, tiempos de concesión y opciones específicas para cada red.

**NAT y enrutamiento:** habilitación del reenvío IPv4 y configuración de reglas iptables para permitir la comunicación entre las redes internas y el exterior.

**Administración:** utilización de Webmin para la configuración gráfica del primer ámbito DHCP y edición manual del archivo `dhcpd.conf` para el segundo.

## Comprobaciones realizadas

- Consulta de parámetros de red mediante `ipconfig /all`.
- Comprobación de rutas mediante `route print`.
- Análisis del proceso DHCP con Wireshark (Discover, Offer, Request y ACK).
- Pruebas de conectividad mediante `tracert`.
- Consulta de los registros del servidor DHCP.

## Tecnologías y herramientas

`Ubuntu Server` · `Windows Server` · `ISC DHCP Server` · `Webmin` · `BIND9` · `iptables` · `IPv4` · `NAT` · `DHCP` · `Wireshark`

## Estructura del repositorio

- `configs/` — Archivos de configuración del laboratorio.
- `docs/` — Documentación y esquema de red.
- `screenshots/` — Capturas representativas de la configuración y las pruebas.

## Aprendizajes

Este laboratorio permitió poner en práctica la administración de servicios de red en Linux, la configuración de DHCP, el enrutamiento entre subredes, la traducción de direcciones mediante NAT y el diagnóstico de conectividad.

---

**Proyecto desarrollado en entorno virtual durante mi formación en ASIR.**
