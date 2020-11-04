# AREP-LAB8

## Contexto

Para el mostarr un grupo auto-escalable en AWS, se implemento la apliccacion de Fibonacci, ya que esta a un gran valor, requiere de varias peticiones que logran mostrar la saturacion de servidor.

## Tutorial

Se crea una plantilla de lanzamiento con el nombre que se quiera y la descripcion de esta

![image](https://user-images.githubusercontent.com/47215172/98064666-d36f3700-1e20-11eb-8de5-2dd59d12f2b1.png)


Se crea un AMI (Amazon Linux 2 AMI) que sirve de plantilla para la configuración de las instancias.

Se elige una instancia que sea compatible y en este caso gratuita que es t2.micro

![image](https://user-images.githubusercontent.com/47215172/98064681-dff38f80-1e20-11eb-81d7-23b519ba02e2.png)


Creamos un par de claves para el grupo.

![image](https://user-images.githubusercontent.com/47215172/98064695-eaae2480-1e20-11eb-8575-00ad3f6ed04e.png)


Y lo asignamos a la plantilla

![image](https://user-images.githubusercontent.com/47215172/98064710-f4d02300-1e20-11eb-9b5f-9635886f7475.png)


Creamos un grupo de seguridad, para habilitar las conexiones.

![image](https://user-images.githubusercontent.com/47215172/98064727-ff8ab800-1e20-11eb-865a-7829d8b711cd.png)

![image](https://user-images.githubusercontent.com/47215172/98064746-0adde380-1e21-11eb-9376-098353b473db.png)


Se modifican las reglas de entrada

![image](https://user-images.githubusercontent.com/47215172/98065527-c7847480-1e22-11eb-8e01-8775359e9de6.png)


Se configura la red para que esta se maneje mediante VPC

![image](https://user-images.githubusercontent.com/47215172/98064779-1fba7700-1e21-11eb-8750-c124c7953153.png)


Se ingresa el script, que van a correr las maquinas al ser creadas con el fin de que todas tengan el repositorio y puedan ejecutar la app

![image](https://user-images.githubusercontent.com/47215172/98064808-32cd4700-1e21-11eb-9763-1d0b70a8cdce.png)

![image](https://user-images.githubusercontent.com/47215172/98064821-3c56af00-1e21-11eb-9f9d-9b1518d6ce87.png)


Se crea un grupo de auto-escalamiento

![image](https://user-images.githubusercontent.com/47215172/98064844-4a0c3480-1e21-11eb-988f-31a79ac2f966.png)


Se configura la red de este, con la mayor cantidad de subredes, para mayor disponibilidad.

![image](https://user-images.githubusercontent.com/47215172/98064861-57c1ba00-1e21-11eb-8c34-2d1dec9245a4.png)

![image](https://user-images.githubusercontent.com/47215172/98064935-67d99980-1e21-11eb-93f9-c5a9c0131afb.png)


Se define el tamaño del grupo

![image](https://user-images.githubusercontent.com/47215172/98064985-863f9500-1e21-11eb-887a-deb36efb45da.png)


Las políticas del escalado, que se base en la utilización de CPU

![image](https://user-images.githubusercontent.com/47215172/98065020-9eafaf80-1e21-11eb-96e0-affa237fbb4d.png)


AWS crea una primera instancia

![image](https://user-images.githubusercontent.com/47215172/98065104-d3236b80-1e21-11eb-9466-02a1d58efb90.png)


Se satura la primera instancia con una petición grande

![image](https://user-images.githubusercontent.com/47215172/98065123-de769700-1e21-11eb-9d6a-111564bbf127.png)


El incremente de CPU al realizar la petición grande

![image](https://user-images.githubusercontent.com/47215172/98065148-ea625900-1e21-11eb-998a-e37074795aa8.png)


AWS nos crea otra instancia para las peticiones

![image](https://user-images.githubusercontent.com/47215172/98065171-f6e6b180-1e21-11eb-8ba2-22449d2750c3.png)


Se muestra que se finalizo la petición grande con su valor correspondiente

![image](https://user-images.githubusercontent.com/47215172/98065185-02d27380-1e22-11eb-80b5-65543e76a1f0.png)


## Autor
  Johan Nicolas Cortes Torres
