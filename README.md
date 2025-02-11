<br />
<div align="center">
  <a href="https://github.com/Danmunozbe/Practica1/tree/Pain2">
    <img src="Imagenes/UNAL.png" alt="Logo" width="200">
  </a>

  <h3 align="center">ROBÓTICA DE DESARROLLO, INTRO A ROS</h3>

  <p align="center">Robótica [2016770]
    <br />Andres Y. Romero D. · Luis E. Carmona A. · Miguel A. Parrado P.
    <br /> ayromerod@unal.edu.co · lucarmonaa@unal.edu.co · mparradop@unal.edu.co
  </p>
</div>


### 1. RESUMEN CON LOS PASOS PRINCIPALES DE PROCESO DE INSTALACIÓN DE ROS2.

El primer paso para instalar ROS2 es descargar Miniforge. Para ello valos a su repositorio github: https://github.com/conda-forge/miniforge

Dependiendo del sistema operativo a usar, se realiza la descarga correspondiente. En nuestro caso se instalará en Windows, por lo tanto navegamos por la página hasta encontrar el enlace de descarga correspondiente:

![](https://github.com/ayromerod/Lab_ROS/blob/main/Imagenes/Sin%20t%C3%ADtulo5.png?raw=true)

Entonces se va a descargar un ejecutable. Cuando se termine de descargar, le damos doble click, y aparecerá la ventana de instalación. Damos click en siguiente, y cuando nos aparezca la opción de si desea hacer la instalación solo para mi o para todos los usuarios, seleccionamos solo para mi. Damos click en siguiente hasta que nos aparezcan 4 opciones para activar o desactivar. Activamos las tres primeras opciones como se observa en la siguiente figura:

![](https://github.com/ayromerod/Lab_ROS/blob/main/Imagenes/Captura.PNG?raw=true)

Damos click en instalar y esperamos a que la instalación finalice.

Una vez finalizada la instalación, abrimos el navegador y nos vamos a la página de RoboSack: https://robostack.github.io/index.html

Luego damos click en "getting started" como se muestra en la siguiente imagen:

![](https://github.com/ayromerod/Lab_ROS/blob/main/Imagenes/Sin%20t%C3%ADtulo4.png?raw=true)

Esto nos llevará a un tutorial para la instalación de ROS.

Ahora damos click en inicio, y buscamos la aplicación "miniforge promt". Al abrirla nos aparecerá una consola de comandos.

![](https://github.com/ayromerod/Lab_ROS/blob/main/Imagenes/Sin%20t%C3%ADtulo6.png?raw=true)

Volvemos a la página de Robostack y copiamos cada una de las lineas mostradas en la siguiente imagen, una por una y en el orden que aparecen. Pegamos cada una de esas instrucciones una por una y en orden, en la consola de mando de Miniforge:

![](https://github.com/ayromerod/Lab_ROS/blob/main/Imagenes/Sin%20t%C3%ADtulo7.png?raw=true)

La ejecución de algunos de esos procesos puede tardar varios minumos, así que esperamos.

Cuando haya finalizado el proceso, verificamos que ROS2 haya sido instalado. Para eso ejecutamos el nodo de la tortuguita: "ros2 run turtlesim turtlesim_node". Si ROS2 ya está instalado, se debe abrir la ventana de la tortuguita, como se observa a continuación:

![](https://github.com/ayromerod/Lab_ROS/blob/main/Imagenes/Sin%20t%C3%ADtulo8.png?raw=true)

### 2. PROCEDIMIENTO UTILIZADO

El procedimiento utilizado para la instalación de ROS2, hace uso de una distribución ligera de conda llamada miniforge. Se puede instalar en multiples sistemas operativos incluyendo Windows 10 y Windows 11. También se hizo uso de Robostack, que es una integración de ROS2 con conda, lo que permite gestionar ROS 2 y sus dependencias de manera sencilla.

![](https://github.com/ayromerod/Lab_ROS/blob/main/Imagenes/miniforge.png?raw=true)

![](https://github.com/ayromerod/Lab_ROS/blob/main/Imagenes/robostack.png?raw=true)

### 3. SISTEMA OPERATIVO SOBRE EL QUE SE HIZO LA INSTALACIÓN

La instalación fue realizada en el sistema operativo Windows 10 haciendo uso de las herramientas miniforge y RoboStack.

### 4. DIFICULTADES DE INSTALACIÓN O DE ARRANQUE

Se presentaron varias dificultades. La primera de ellas, corresponde a un error que se genera siempre se activa el entorno "ros_env" cuando se ejecuta el comando "mamba activate ros_env". El error que aparece se puede ver en la siguiente imagen:

![](https://github.com/ayromerod/Lab_ROS/blob/main/Imagenes/Sin%20t%C3%ADtulo9.png?raw=true)

Si bien este error no impide la ejecución de ROS2, de alguna manera podría afectar su funcionamiento generando errores futuros a medida que se vaya usando.

Otro error radica en el hecho de que RoboStack usa python 3.11 para su correcto funcionamiento, mientras que el RosToolbox de Matlab requiere que se especifique la ruta de python ya sea versión 8, 9 o 10, como se observa en la siguiente imagen:

![](https://github.com/ayromerod/Lab_ROS/blob/main/Imagenes/ros_matlab.png?raw=true)

Al especificar la ruta de la versión de python 3.11 instalado en el entorno ros_env, se genera un error y una advertencia diciendo que el Toolbox de Matlab solo es compatible con las versiones 3.9, 3.9 o 3.10. Esto hizo que mas adelante Matlab no reconiciera los mensajes de turtle sim, y por lo tanto se generara une error en Matlab, al intentar ingresar el comando: "poseSub = ros2subscriber(node, "/turtle1/pose", "turtlesim/Pose");" para suscribirnos en al topico de la pose de "turtle1". Así mismo, al intentar importar los mensajes de turtle sim a la msg list, se generó el siguiente error:

![](https://github.com/ayromerod/Lab_ROS/blob/main/Imagenes/Sin%20t%C3%ADtulo3.png?raw=true)

Por otro lado, se intentó reinstalar RoboStack con una versión de python 3.10, para que fuese compatible con el RosToolbox de Matlba, pero se obtuvo el siguiente error:

![](https://github.com/ayromerod/Lab_ROS/blob/main/Imagenes/Sin%20t%C3%ADtulo.png?raw=true)
