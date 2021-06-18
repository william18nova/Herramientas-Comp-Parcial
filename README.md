# Documentación
## ¿cuál es el problema?
El problema consiste en crear una aplicación para una cafetería dentro de una universidad que quiere realizarles descuentos a sus compradores dependiendo del rol que cumplan en la universidad, siendo un descuento del 50% para los estudiantes y de 20% para profesores, además quieren que al final se imprima el valor total con el descuento, el rol del cliente, los códigos de los productos que compro, y el documento de este.

## ¿Qué modelo computacional lo resuelve? 
* Se crea la función *imprimir* la cual resivira los parametros **rol, documento, precioFinal, productos** los cuales se usarán para imprimir la factura o salida, esta función organiza el string que se va a imprimir para que concuerde con el género del cliente y la cantidad de productos que va a llevar. 

* Creamos la función **calculo** que recive los paramaetros **documento, rol, precio, codigos** esta función será la encargada de hacer los descuentos según el rol del cliente y convertía los codigos en una lista dentro de un string. 

* Creamos la función **datos_entrada** la cual sera la encargada de leer todos los datos de entrada e invocar con estos a las demás funciones con los datos recolectados, además de repetir el código tantas veces cómo se quiera. 

* Dentro la funcion **datos_entrada** creamos la varible **seguir = None** esta nos va a decir cuando se acaba el codigo. 

* Creamos el ciclo **while seguir  == "si":** el cual va a repetir el código y dentro de este creamos lo siguientes pasos. 

* Creamos la variable **precio = 0** ya que es en esta donde vamos a aguardar el valor de todos los productos que lleve el cliente. 

* Creamos la lista **codigos = []** en ella guardaremos todos los códigos de los productos que compre el cliente. 

* Creamos la variable **i = 1** esta será la indicadora de cuantos tipos de productos lleva el cliente 

* creamos la variable **documento =  int(input("Digite el número de documento: ”))** para preguntar el número de documento del cliente y guardarlo dentro de una variable, como restricción se tiene que solo se le pueden pasar numeros a este input. 

* Creamos la variable **rol = input("¿Cual es tu rol en la universidad?  ").lower()** donde guardamos el rol del cliente y convertirnos el texto en minúsculas para facilitar procesos más adelante dentro del código. 

* Se crea la variable **producto = input("Producto %d: " % (i))**, en esta se obtiene el código del producto, la cantidad y el precio, la restricción es que se deben de ingresar los datos en el orden especificado y el precio y la cantidad solo pueden tener numeros como entrada. 

* Se crea un ciclo **while  producto != "":** el cual permite registrar todos los tipos de producto que el cliente quiera hasta que se deje en blanco estos datos. 

* Dentro del ciclo while lo primero que se hace es **producto = producto.split()** para convertir los datos de productos a una lista. 

* Le sumamos a la variable **i**  1.

* Hacemos **codigos.append(producto[0])** para agregar a la lista **códigos** el código de los productos. 

* Hacemos la operación **precio += int(producto[1]) * int(producto[2])** para obtener el precio de todas las unidades de producto que va a comprar. 

* Al terminar el ciclo ejecutamos la función **calcular** con los parámetros **documento, rol, precio, códigos** 

* Dentro de la función calcular se crea la variable **productos = ""** donde haremos el listado de los códigos de los productos que lleve el cliente. 

* Después creamos los condicionales **if rol == "estudiante"** en la cual si el rol del cliente es estudiante se realiza la operación **precio = precio - (precio * 0.5)** aquí se le hará el descuento del 50% sobre el total de su compra. 

* Se crea el condicional **elif rol == "profesor" or rol == "profesora"** en caso de que el rol sea profesor o profesora se hace la operación **precio = precio - (precio * 0.2)**  aquí se le hará el descuento del 20% sobre el total de su compra. 

* Despues creamos el ciclo **for i in range(len(codigos))** que hará en bucle la operación **productos += codigos[i]** para agregar a un string todos los códigos de los productos que va a comprar, dentro de este también estará el condicional **if i < (len(codigos) - 1)** en caso de ser cierta la condición se hará esto **productos += ", "** con el fin de separar todos los códigos por comas. 

* Después se ejecuta la función **imprimir** con los parámetros **rol, documento, precio, productos**. 

* Dentro de rol están los condicionales **if (rol == "estudiante" or rol == "profesor") and "," in productos:**, **if (rol == "estudiante" or rol == "profesor") and "," in productos:**, **elif rol == "profesora" and "," in productos:**, **elif rol == "profesora" and "," not in productos:**, **elif (rol != "profesora" or rol != "profesor" or rol != "estudiante") and "," in productos:**, **elif (rol != "profesora" or rol != "profesor" or rol != "estudiante") and "," not in productos:**, esto con el fin de que el texto de la factura se ajuste al género del cliente, (se decide si se escribe El profesor o la profesora) y a la cantidad de productos que lleva (para saber si se imprime debe pagar $**precio** por el producto o debe pagar $**precio** por los productos). 

* Finalmente se regresa a la función **datos_entradar** donde se realiza el siguiente input **seguir = input("¿Quieres seguir registrando otras compras? Si/No: " ).lower()** esto para saber si el programa seguirá corriendo o finalizará. 

* En caso de que la respuesta sea invalida al input anterior se crea un ciclo **while seguir != "si" or seguir !="no":** que repetirá el input hasta que se digité la una respuesta valida, en caso de cerrar  el código para, o en caso de continuar vuelve a iniciar. 

## ¿Qué entradas recibe el programa?
El algoritmo recibe como entradas el número de documento del comprador, el rol que tiene este en la universidad, el código de el o los productos que va a comprar, la cantidad de cada producto que lleva y el valor de cada uno de estos y al final de cada facturación le pregunta al usuario si quiere seguir actuando o cerrar el programa. 

## ¿Qué salidas retorna el programa?
* El programa imprime la factura con los siguientes datos: 
* El rol del comprador dentro de la universidad.  
* El número de cedula de este. 
* El pecio total que pagar por los productos que lleva con l descuento aplicado según su rol. 
* Una lisa con los códigos d los productos que compro. 

## ¿Cómo se calcula?
* Para calcular la salida se toman los códigos de los productos que se vayan a comprar y se agregan en una lista llamada _“codigos”_
* Se multiplica el precio del producto por la cantidad de unidades de cada producto y el valor se va sumando en la variable _“precio”_ 
* Se toma el rol de cliente si es profesor se toma el precio y se le resta el resultado de multiplicar 0.2 por el precio, esto se guarda en la variable _“precioFinal”_, en caso de ser estudiante se hace lo mismo peo en ver de restarle al precio la multiplcacion del precio por 0.2 se le resta el resultado de multiplicar el precio por 0.5. 
* Los valores de la lista códigos se suman en un string _“productos”_ para tener una lista ordenada de estos. 
* Finalmente se toman los datos de _rol, documento, precioFinal, productos_ y se agregan dentro de un string para imprimir la factura 
