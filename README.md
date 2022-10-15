# TrabajoPractico-Informatica2_PuertaAutomatica

## Memoria descriptiva

Mi sistema representa una puerta automática con sensores de movimiento. La puerta es corrediza y funciona mediante un motor. Cualquier movimiento alrededor de la puerta será leido por dos sensores ubicados a ambos lados de esta. La puerta se mantiene cerrada, y cuando uno de los sensores detecta algún movimiento se abre automaticamente. Además, hay un timer configurable para que la puerta pueda mantenerse abierta unos segundos despues de que los sensores dejen de detectar movimiento. 

## Máquina de estado de puerta automática

![image](https://user-images.githubusercontent.com/82234887/196004130-7c45d14b-b9ec-4e6b-8281-89f65daefe8c.png)

- __SET__: Bandera de fin de inicialización
- __s__: Detector de movimiento en el sensor
- __t__: Timer
- __t_set__: Segundos que se mantiene la puerta abierta

## Código

- Archivo de cabecera __mylib.h__

```c
# ifndef MY_LIB
# define MY_LIB
# include <stdio.h>

# endif
