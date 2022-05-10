# examen3
3er Examen del Modulo 4

INSTRUCCION:
El objeto de la práctica es crear una virtual, y configurarla de forma automatizada, con la ayuda de Terraform y Ansible.

1) En este sentido se debe preparar una máquina virtual con sistema operativo Ubuntu Server 18.04 LTS https://ubuntu.com/download/server con las siguientes características:
      Memoria RAM 4G - 8G
      4 procesadores
      Almacenamiento 16 G - 32 G
      Una Tarjeta de Red
      Acceso a Internet
      
Detalles de la configuracion

KVM

2) En una consola de PowerShell (en modo administrador se debe correr) con la maquina virtual apagada:

      Set-VMProcessor -VMName UbuntuServer -ExposeVirtualizationExtensions $true 
      
Donde UbuntuServer es el nombre de la maquina virtual

4) Verificar que la maquina virtual tiene las extensiones de virtualización asistida por Hardware.


            egrep -c '(vmx|svm)' /proc/cpuinfo
            4

      
5) Debe salir un valor mayor que cero Luego como siempre se deben actualizar toda la distro.

      sudo apt update
      sudo apt upgrade
      
