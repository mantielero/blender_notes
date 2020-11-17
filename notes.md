# Cargar un modelo
Típcamente usaremos .dae (collada) o .obj (wavefront). Ambos pueden exportarse desde FreeCAD.
Borramos el cubo que sale por defecto y después: **Archivo > Importar**.
# Ajustar cámara a vista actual
Haremos: **Vista > Alienear vista > Align Active Camera to View**
![](https://i.imgur.com/PDfoZMf.png)
 Con el F12, podemos renderizar la imagen.

# Cámara girando alrededor de una pieza
## Importamos
1. Borramos el cubo
2. Importamos la pieza

## Creamos un círculo
Lo creamos:
![](https://i.imgur.com/ejGLI0Y.png)
y modificamos su tamaño y posición mediante:
![](https://i.imgur.com/JiEJJn4.png)
## Poner la cámara en el círculo
### Parenting
En blender se pueden relacionar dos objetos mediante [parenting](https://docs.blender.org/manual/en/2.79/editors/3dview/object/properties/relations/parents.html#:~:text=To%20parent%20objects%2C%20select%20at,several%20possible%20different%20parenting%20types.).
Seleccionamos la cámara y el círulo (mediante **Shift click**) y vamos al menú de **Objeto > Superior > Seguir trayectoria**:
![](https://i.imgur.com/tc5witJ.png)
>Atajo: Ctrl+P

y nos aparecerá una fina línea negra entre la cámara y el círculo:
![](https://i.imgur.com/XWwT7ZM.png)

Seleccionamos sólo el círculo y vamos al modo de edición.
![](https://i.imgur.com/Z91xjIc.png)
> Atajo: Tab
y queda:
![](https://i.imgur.com/hEXe9FT.png)
Hacemos click en el punto al que apunta la cámara:
![](https://i.imgur.com/CRUxNob.png)

y seleccionamos sólo el punto del centro (pinchar y arrastrar). Veremos que ese punto está blanco y los otros dos en negro:
![](https://i.imgur.com/tHQoK8e.png)

Ahora hacemos snapping a **Cursor to Selected**:
![](https://i.imgur.com/JnmucNV.png)
> Alternativamente, se puede hacer: Shift+S

De esta forma, el cursor 3D se pone en ese punto.

Volvemos al modo objeto, pulsando **Tab**.

### Movemos la cámara al cursor 3D
Dentro del modo objeto, seleccionamos la cámara con el botón derecho 
(Yo tuve que hacer lo siguiente)
![](https://i.imgur.com/CeBh2wI.png)

y movemos la selección (cámara) al cursor 3d (que habíamos puesto en el punto de la curva):
![](https://i.imgur.com/xhu2nFy.png)

El resultado será:
![](https://i.imgur.com/MgYKuxU.png)

Si reproducimos la animación la cámara se moverá por el círculo, pero no apuntará a la zona de interés:
![](https://i.imgur.com/XqvFjL8.png)

## Apuntar la cámara
En la animación vamos al frame 0:
![](https://i.imgur.com/J2eo5Ss.png)

Posicionamos el cursor 3D en el centro del objeto a observar. Para ello:
1. Seleccionamos el objeto
   - Primero la herramienta seleccionar
![](https://i.imgur.com/6gGj1zQ.png)
   - Después con el botón izquierdo en el objeto
2. Movemos el cursor 3D:
   - **Shift+S**
   - Cursor to Selected
![](https://i.imgur.com/qD5ePGX.png)
> Yo creo que en mi caso lo lleva al centro del sistema de referencia del objeto seleccionado, no a su centro de masas.

Creamos un objeto vacío:
![](https://i.imgur.com/jByH4Jt.png)

En mi caso, como no me gusta donde ha quedado, modifico su ubicación.

Añadimos la constraint de que la cámara apunte al objeto vacío:
1. Seleccionamos la cámara
2. Vamos a la Restricción de Objeto y pulsamos **Add object restriction**:
![](https://i.imgur.com/vkhO7f9.png)
3. Seleccionamos **Rastrear** (Track to):
![](https://i.imgur.com/A7Uiwg4.png)
4. Seleccionamos el objeto **Vacío**, el **Eje de rastreo** (To) lo ponemos en **-Z**, y el **Arriba** seleccionamos **Y**.
![](https://i.imgur.com/7X366qz.png)

El resultado es la cámara apuntando al objeto vacío y correctamente orientada.
![](https://i.imgur.com/zbSyxlx.png)

Si pulsamos el Play, la cámara apunta ahora como debe.

