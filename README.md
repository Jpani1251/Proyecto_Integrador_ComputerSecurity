# Proyecto_Integrador_ComputerSecurity

**Unidad de Aprendizaje:** Computer Security  
**Grupo:** 6CV1
**Institución:** Escuela Superior de Cómputo (ESCOM-IPN)  

## Integrantes del Equipo
1. Paniagua Escamilla Jorge Alberto
2. Vizuet Mendoza Alejandro
3. Moreno Barranco Ulises


## Objetivo del Proyecto
Recorrer el ciclo completo de la ciberseguridad sobre un entorno de laboratorio corporativo autorizado. El proyecto simula una red pequeña con Active Directory utilizando máquinas virtuales para comprender, ejecutar y mitigar ataques de movimiento lateral, escalamiento de privilegios y persistencia.

## Entorno de Laboratorio Autorizado
**Infraestructura:** Entorno Corporativo con Active Directory en Máquinas Virtuales orquestadas localmente.
* **Controlador de Dominio (Target 1):** Windows Server (AD DS).
* **Estación de Trabajo (Target 2):** Cliente Windows unido al dominio.
* **Máquina Atacante (Equipo Rojo):** [Ej. Kali Linux / Parrot OS].
* **Hipervisor:** [Ej. Parallels Desktop / VMware / VirtualBox].

## Pasos para la Reproducibilidad (Despliegue del Entorno)
Para levantar el entorno y las herramientas exactas de este laboratorio, sigue estos pasos:

### 1. Preparación del Hipervisor y Red
1. Instalar el hipervisor.
2. Configurar un conmutador virtual (Virtual Switch) en modo **Red Interna / Aislada** con el segmento de red.

### 2. Despliegue de Máquinas Virtuales
1. **Windows Server (DC):**
   * Importar la ISO de Windows Server.
   * Asignar IP estática.
   * Promover a Controlador de Dominio y configurar el bosque.
2. **Cliente Windows:**
   * Importar la ISO de Windows 10/11.
   * Asignar IP dentro del segmento y configurar el DNS apuntando al DC.
   * Unir la máquina al dominio.
3. **Máquina Atacante:**
   * Importar máquina virtual.
   * Conectar la interfaz de red a la Red Interna aislada.

### 3. Herramientas Utilizadas
* **Fase 1 (Equipo Rojo):** Nmap, Metasploit, Mimikatz, BloodHound, Impacket.
* **Fase 2 (Equipo Azul):** Sysmon, [Nombre del SIEM/EDR, ej. Splunk / Wazuh / Elastic].
* **Fase 3 (Gobierno):** Documentación basada en ISO 27001/NIST CSF.