# Paquetes:

Vamos a usar algunos

``` {.r}
paquetes <- c("metR", "ecmwfr", "ggplot2", "data.table")
install.packages(paquetes)
```

# Cuentas

Crearse una cuenta en Climate Data Store

<https://cds.climate.copernicus.eu/cdsapp#!/home>

Setear las credenciales.
Correr esto en la consola:

``` {.r}
ecmwfr::wf_set_key(service = "cds")
```

Se va a abrir la página web de Climate Data Store donde vas a tener que logearte:

![](img/api-key.png)

Y luego te va a llevar a tu perfil de usuario.
Abajo de todo están los datos de tu UID y tu API Key.

![](img/api-key.png)

El UID tenés que escribirlo en la consola:

    > ecmwfr::wf_set_key(service = "cds") 
    Login or register to get a key 
    User ID / email: <UID>

Y luego la API Key hay que ponerla en el diálogo que aparece luego (si no estás en RStudio, va a aparecer en la siguiente línea)

![](img/password.png)
