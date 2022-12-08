Instrucciones para ejecutar el codigo: 
Instale Keil Uvision en su equipo
Descargue el comprimido Codigos.rar en donde se encuentra el archivo Codigos.uvprojx
En la parte izquierda aparecera un espacio de nombre "Project" deslice la opcion "Source Group 1"
Si desea ejecutar el codigo por separado de cada dispositivo, seleccione exercise_1_1.c, exercise_1_2.c, exercise_1_3.c (en la linea 1 indica a que dispositivo pertenece dicho codigo)
Si desea ejecutar el codigo completo seleccione exercise_2_1.c
Una vez seleccionado el codigo a ejecutar, dirijase a la parte superior derecha y ejecute opcion "Build" (F7), luego "Rebuild" y "LOAD"

Configuraciones a tomar en cuenta:
- Se encuentra seleccionado correctamente el modelo de nuestra plataforma que estamos utilizando?
- Se encuentra en modo Use ST-Link Debugger?
- 
Para ello nos dirigimos a la ventana "Options for Target 'Target 1'"
En la pestaña Device nos aseguramos que este seleccionado STM32F334R8
En la pestaña "Target" Seleccionamos ✓ Use MicroLIB
En la pestañan "Debug" seleccionamos ✓ ST-Link Debugger

Errores comunes de compilacion:
Al momento de compilar el codigo asegurese de que en el main.c se encuentre descomentado el exercise_x_x.c a compilar
El resto de los exercise_x_x.c que no seran compilados deben estar totalmente comentados /*codigo*/ tanto en el exercise_x_x.c como en el main.c

(Si se presenta aun un error al momento de cargar el codigo a la plataforma, pruebe presionar el boton de reset y presione LOAD si soltar el boton)

Datos a tomar en cuenta TCS 3200:
El sensor TCS 3200 llegar a tener un variacion a la hora de detectar el color rojo, esto cambia dependiendo en el ambiente donde nos encontremos
Los parametros del sensor ya viene configurado para un ambiente a la luz del dia o ambientes similares, si no fuera el caso, siga los siguientes pasos.


Dirigase exercise_2_1.c cargue el codigo a la plataforma e inicie el Debug o presione Ctrl+F5 
Presione Run o F5 y en la ventana "Watch 1" la variable rojo cambiara, mueva el sensor a diferentes direcciones del ambiente hasta que pueda llegar a tener un rango estimado de valores.
Con este rango de valores modificara el codigo en la siguiente condicional

if (rojo > 160 && rojo < 280 )
      
modifique la condicional dependiendo el rango estimado de su ambiente. 
Hacer lo mismo para exercise_1_1.c

