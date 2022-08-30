---
title: "Teoría Arrays para el manejo de data grillada netcdf"
author: "Victor Diaz"
date: "30/8/2022"
output: html_document
---

## Arrays

Los arrays son agrupamiento de matrices, las cuales como se sabe solo tienen 2 dimensiones. En este caso los arrrays van a agrupar las matrices de tal forma que se superen las 2 dimensiones.

### Por ejemplo: Matriz:
Si tenemos una matriz simple de 3x4 (3 filas y 4 columnas)

```{r }
M <- matrix(1:24,nrow=3,ncol=4)
M
```

## Array de 2 capas:
Ahora a partir de la matriz M, podemos construir un array de 2 capas. Con el argumento dim(filas,columnas,capas)


```{r }
MA <- array(1:24,dim=c(3,4,2))
MA
```

## Array de 2 capas y 3 bloques:
A partir del array MA, podemos construir un array de 2 capas y 3 bloques agrupados. Con el argumento dim(filas,columnas,capas,bloques)


```{r }
MB <- array(1:72,dim=c(3,4,2,3))
MB
```

## Array de 2 capas , 3 bloques, etc :
A partir del array MB, podemos seguir construyendo estructuras más complejas y de más dimensiones. Con el argumento dim(filas,columnas,capas,bloques,etc)


```{r }
MBB <- array(1:216,dim=c(3,4,2,3,3))
MBB
```

## Para acceder a los valores de un array:
De forma muy simple solo es necesario elegir la [fila, columna,capa, bloque,etc]

```{r }
MB[1,1,1,3]
```

## Conclusiones

1. En general los archivos grillados .nc y sobretodo reanálisis constaran de 4 niveles [lon,lat,level,time], por lo que es necesario conocer la base de los arreglos para poder manejar la data correctamente.

2. Al usar data en superficie se podrá considerar solo [lon,lat,level]

