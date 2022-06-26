# Práctica 15 - Monitores de recursos con Azure Monitor

Para poder hacer esta práctica crearemos una máquina virtual:
- Suscripción
- Grupo de recursos: sesion7
- Nombre: sesion7vm
- Region: Austraia Central
- Imagen: Windows 10 pro
A demás de configurar un usuario y una contraseña.

![Práctica 15 - parte 1](imagenes\p15p1.png)

Una vez creada la mpaquina virtual, nos metemos a ella y en Conexión RDP descargamos el archivo y ejecutamos la máquina virtual.

![Práctica 15 - parte 2](imagenes\p15p2.png)

Accedemos a la máquina virtual con el usuario y contraseña que configuramos.

![Práctica 15 - parte 3](imagenes\p15p3.png)

En la barra de búsqueda de Azure buscamos el _Monitor_.

![Práctica 15 - parte 4](imagenes\p15p4.png)

En alertas, seleccionamos "Agregar alerta" y agregamos una regla de alertas.

![Práctica 15 - parte 5](imagenes\p15p5.png)

En la sección de _Ámbito_ seleccionamos "Seleccionar un ámbito"

![Práctica 15 - parte 6](imagenes\p15p6.png)

Podemos filtrar por el tipo de recurso, en este caso Máquinas viruales.

![Práctica 15 - parte 7](imagenes\p15p7.png)

Seleccionamos nuestra máquina virtual que vamos a monitorear (sesion7vm).

![Práctica 15 - parte 8](imagenes\p15p8.png)

En la sección de _Condición_ agregamos una condición. En tipo de señal y supervisar servicio dejamos "Todo", y en el nombre se la señal buscamos _Percentage CPU_.

![Práctica 15 - parte 9](imagenes\p15p9.png)

En la configuración de la lógica de la señal, en _Lógica de alerta_ establecemos un operador "Mayor que", tipo de agregación "Promedio" y valor del umbral "30"(%); así como la granularidad de 1 minuto y frecuencia de cada minuto.

![Práctica 15 - 10](imagenes\p1510.png)

En la sección de detalles configuramos:
- Suscripción
- Grupo de recursos: sesion7
- Gravedad (Crítico, Error, Advertencia, Informativo, Detallado): Crítico
- Nombre de la regla de alertas: alerta de uso de CPU.
Revisamos y creamos.

![Práctica 15 - parte 10](imagenes\p15p10.png)

De regreso al Monitor, en la sección de Métricas buscamos nuestra Máquina virtual y aplicamos.

![Práctica 15 - parte 11](imagenes\p15p11.png)

Seleccionamos la métrica de Porcentaje de CPU.

![Práctica 15 - parte 12](imagenes\p15p12.png)

Cuando tengamos nuestra Máquina virtual, al llevar el CPU a más del 30%, en Azure Monitor podremos ver la alerta en la sección de Alertas.

![Práctica 15 - parte 13](imagenes\p15p13.png)

Al entrar a la alerta podremos ver un resumen de esta junto con una gráfica de métrica del recurso.

![Práctica 15 - parte 14](imagenes\p15p14.png)