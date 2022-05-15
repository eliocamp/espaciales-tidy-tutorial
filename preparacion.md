---
title: "Antes del tutorial"
---

En el tutorial les propondremos hacer ejercicios en sus propias computadoras, por eso te pedimos que sigas las siguientes instrucciones para tener todo listo ese día.

# Paquetes:

Durante este tutorial usaremos una serie de paquetes. Es posible que ya tengas algunos instalados, pero es importante que te asegures de tenerlos todos. Te sugerimos que corras las siguientes líneas de código y luego pruebes cargas las librerías.

``` {.r}
paquetes <- c("metR", "ggplot2", "data.table", "ggperiodic", "ggnewscale")
install.packages(paquetes)
```

Vamos a trabajar con un tipo de archivo particular, los NetCDF4. Para leer archivos NetCDF4 es necesario instalar los paquetes {ncdf4} y {udunits2}. 

En linux, estos paquetes dependen de las librerías de sistema netcdf y udunits-2 respectivamente. En Ubuntu y derivados, se pueden instalar con:

```{·bash}
sudo apt install libnetcdf-dev netcdf-bin libudunits2-dev
```

En windowns no es necesario que instales ningún programa o librería extra. 

Finalmente, podrás instalar los paquetes de R con:

``` {.r}
install.packages(c("udunits2", "ncdf4"))
```

Como nuestro planeta es una esfera, es útil poder proyectar los datos a coordenadas que no sean sólo latitud/longitud. Para eso vamos a usar el packete {proj4}, que depende de la librería de systema proj. Nuevamente, en ubuntu y derivados se puede instalar con:

```{·bash}
sudo apt install proj-bin
```

(Instrucciones para otros sistemas operativos [en la página del proyecto](https://proj.org/install.html))

Y luego instalar el paquete de R con:

``` {.r}
install.packages("proj4")
```


# Plan B

Si no lográs que funcione o preferís no instalar los paquetes en tu computadora, podés usar [este proyecto de RStudio Cloud](https://rstudio.cloud/project/xxxxxx), donde dejamos todos los paquetes instalados. Tené encuenta que necesitarás una cuenta en RStudio Cloud (la versión gratuita tiene sus limitaciones pero debería ser suficiente para el tutorial). Además deberás crear una cuenta en Climate Data Store y seguir los pasos de configuración en R.
