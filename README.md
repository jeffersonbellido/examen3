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
2) Para los estudiantes que tienen como sistema operativo reciben una distribución de Linux "moderna" kernel >= 4.4 pueden saltar al punto 2

Se debe instalar KVM (dentro de la maquina) virtual, por lo que se debe habilitar la virtualización anidada en el anfitrión (host) Se ha podido comprobar con hyper-V que se puede habilitar y utilizar correctamente, en VirtualBox no funciona bien (es una función Beta) y en Mac es posible que la última versión de vmware Fusion funcione correctamente (Apple cambió algunas partes de la base de su soporte de virtualización por el cambio de procesadores).
En hyper-V se debe habilitar la virtualización anidada (de acuerdo a https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/user-guide/nested-virtualization )

En una consola de PowerShell (en modo administrador se debe correr) con la maquina virtual apagada:

      Set-VMProcessor -VMName UbuntuServer -ExposeVirtualizationExtensions $true 
      
Donde UbuntuServer es el nombre de la maquina virtual

Verificar que la maquina virtual tiene las extensiones de virtualización asistida por Hardware.

      egrep -c '(vmx|svm)' /proc/cpuinfo
      4
      
Debe salir un valor mayor que cero Luego como siempre se deben actualizar toda la distro.

      sudo apt update
      sudo apt upgrade
      
