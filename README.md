# TrabajoPractico-Informatica2_PuertaAutomatica

## Memoria descriptiva

Mi sistema representa una puerta automática con sensores de movimiento. La puerta es corrediza y funciona mediante un motor. Cualquier movimiento delante de la puerta será leido por dos sensores ubicados a ambos lados de la puerta. Esta se mantiene cerrada, y cuando uno de los sensores detecta algún movimiento se abre automaticamente. Además, hay un timer configurable para que la puerta pueda mantenerse abierta unos segundos despues de que los sensores dejen de detectar movimiento. 

## Máquina de estado de puerta automática

![captura de maquina de estado](https://user-images.githubusercontent.com/82234887/190162330-6e75c734-db36-4e67-b744-83177bda12d3.PNG)

- __SET__: Bandera de fin de inicialización
- __s__: Detector de movimiento en el sensor
