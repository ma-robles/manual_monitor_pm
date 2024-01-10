---
title: Monitor de Partículas
description: Manual de usuario
author: Miguel Ángel Robles R.
email: "miguel.robles@atmosfera.unam.mx"
layout: default
---

## Introducción
El monitor de partículas se basa en una placa ESP32 y un sensor SPS30 de Sensirion, ademas agrega sensores de presión, temperatura y humedad relativa.
Todo contenido en un abrigo meteorológico propio.

## Partes

### Vista Lateral
![partes](/manual_monitor_pm/assets/img/partes.png)

### Vista Inferior
![partesInferior](/manual_monitor_pm/assets/img/partes_inferior.png)

## Configuración
Para que el monitor pueda sincronizar la hora y fecha, se debe conectar a internet y especificar la zona horaria. Esto se hace ingresando los datos de una red WiFi al archivo de configuración.

### Requisitos
- Datos de la red WiFi (SSID y contraseña)
- Computadora con el software Thonny y el driver de la tarjera instalados
- Cable USB a micro-USB

Nota: para mas detalles sobre cómo instalar Thonny y el driver vea el [manual Thonny](/manual_thonny/) y [Manual driver ESP32](/manual_driverESP32).

### Procedimiento
1. Abrir Thonny

2. Conectar el cable USB y micro-USB a la tarjeta ESP32 y a la computadora respectivamente. El conector de la ESP32 se encuentra en la parte inferior.

3. Presionar el botón STOP en la ventana de Thonny. En la sección inferior de la ventana de Thonny se debe observar el promt (>>>)
![stop](/manual_monitor_pm/assets/img/stop.png)

4. En Thonny, selecionar el menú file y Open. Se mostrará una ventana con 2 opciones: abrir archivo en la computadora o en la ESP32 (micropython device). Seleccione Micropython Device.
![abrir](/manual_monitor_pm/assets/img/abrir.png)

5. Se mostrarán los archivos que se encuentran en el dispositivo seleccionado. Seleccione el archivo info.py
![files](/manual_monitor_pm/assets/img/files.png)

6. Se abrirá el archivo y se mostrará. En la primera línea se deben colocar los datos del WiFi a utilizar. Primero el nombre de la red y luego la contraseña, es necesario escribir correctamente estos datos, entre comillas y sin espacios. Modifique la zona horaria, por defecto está como utc=-6. Evite modificar los demás parámetros.
![info](/manual_monitor_pm/assets/img/info.png)

7. Presione CTRL+D para reiniciar la tarjeta, en la parte inferior de la ventana de Thonny se mostraran los mensajes de la ESP32. Si la conexión es exitosa, se debe observar un mensaje con la leyenda "conectando" y el nombre de su red WiFi, así como la IP asignada al dispositivo.
![wifi](/manual_monitor_pm/assets/img/wifi.png)

8. Si no hay conexión, revise los datos ingresados. Presione el boton STOP en la ventana de Thonny y repita el procedimiento desde el paso 4.

nota: El sistema cuenta con un Timer  de reinicio en caso de que el programa se detenga. Debe realizar el procedimiento antes de que el tiempo del timer se termine o comenzará a correr el programa y no le permitirá guardar sus modificaciones. Si el módulo se reinicia antes de que pueda guardar sus cambios, presione el boton STOP de Thonny, espere a ver el promt (>>>) e intente de nuevo. La duración actual del timer es de 10 minutos.

## Instalación

### Sujeción
El monitor está pensado para fijarse a un poste vertical mediante una abrazadera tipo "U" a la placa de sujeción.
![sujeta](/manual_monitor_pm/assets/img/instala_alimenta.png)

nota: la placa de sujeción puede tener las perforaciones hacia arriba del monitor o hacia abajo, dependiendo de la versión. En cualquier caso, la placa de sujeción se debe colocar en la parte superior del equipo.

### Alimentación
El módulo se alimenta mediante el puerto micro-USB que se encuentra en la parte inferior del abrigo meteorológico. Se puede utilizar un cargador o un regulador a 5V  con cable micro-USB

![alimentacion](/manual_monitor_pm/assets/img/instala_alimenta.png)

### Ejemplo
A continuación se muestra una imagen de ejemplo en la que se monta un prototipo en un tripie. En la parte inferior del tripié se instaló una caja para intemperie en la que se encuentra un cargador conectado a una extensión eléctrica que a su vez se encuentra conectado a la línea eléctrica.

![instala](/manual_monitor_pm/assets/img/instala_completa.png)

## Ensamblado/des-ensamblado

El monitor se envia totalmente ensamblado y listo para colocarse en un tubo vertical. A continuación se describen los pasos a seguir en caso de que requiera desarmarlo.

