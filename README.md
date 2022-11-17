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

typedef enum {
  close = 0;
  open = 1;
} estados_t;

typedef struct {
  char s;               // detección de movimiento en el sensor
  char t;               // segundos marcados en el timer
  char t_set;           // segundos que se mantiene la puerta abierta
} datos_t;

datos_t f_inicio (void);
estados_t f_close (datos_t);
estados_t f_open (datos_t);

# endif

```

- Archivo __main.c__
> con switch case

```c
#include "mylib.h"

int main() {
    datos_t config;
    estados_t estado = close;
    
    config = inicio();
    while(1){
      switch (estado) {
        case close: estado = f_close(config);
                     break;
        case open: estado = f_open(config);
                       break;
      }
    }
  return 0;
}

```

> Con punteros a funciones

 ```c
 #include "mylib.h"
 
 int main() {
     datos_t config;
     estados_t estado = close;
     estados_t (*fsm[])(datos_t) = {f_close, f_open}
     config = inicio();
     while(1) estado = (*fsm[estado])(config);
   return 0;
 }
 
 ```
 
 - Archivo __config.conf__

```bash
# Cantidad de segundos que se mantiene la puerta abierta sin detectar movimiento
t_set 3

```

- Funciones de estado

```c
estados_t f_close(datos_t){
    datos_t;
    if(s = 0 && t > t_set){
        estado = close;
    }
    else{
         estado = open;
    }
  return estado;
}

estados_t f_open(datos_t){
    datos_t;
    if(s = 1){
        estado = open;
    }
    else{
         estado = close
    }
  return estado;
}

```


