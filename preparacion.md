---
title: "Antes del tutorial"
---


# Paquetes:

Lo primero es tener instalados algunos paquetes. Corré esto para instalarlos:

``` {.r}
paquetes <- c("metR", "ecmwfr", "ggplot2", "data.table", "ggperiodic", "ggnewscale")
install.packages(paquetes)
```

Para leer archivos NetCDF4 hay que instalar los paquetes ncdf4 y udunits2 
En linux, estos paquetes dependen de las librería de sistema netcdf y udunits-2 respectivamente. 
En Ubuntu y derivados , se pueden instalar con:


```{·bash}
sudo apt install libnetcdf-dev netcdf-bin libudunits2-dev
```

Luego, hay que instalar los paquetes de R con:

``` {.r}
install.packages(c("udunits2", "ncdf4"))
```

# Cuentas

Vamos a usar el paquete [ecmwfr](https://bluegreen-labs.github.io/ecmwfr/) para descargar datos climáticos. 
El mismo permite hacer pedidos de datos a varios servicios, pero en este tutorial vamos a usar el Climate Data Store. 

Para descargar datos climáticos del Climate Data Store primero hay que tener una cuenta. 
Si no tenés una, creala en <https://cds.climate.copernicus.eu/user/register>.

![Captura de pantalla del formulario de registro de Climate Data Store.](img/registro.png)

Una vez que tengas tu usuario y contraseña, hay que setear las credenciales en R.
Andá a [tu perfil de usuario](https://cds.climate.copernicus.eu/user/login?destination=user) y abajo de todo vas a ver una sección con título "API Key" con dos valores: tu UID (User ID) y tu API Key. 

![Captura de pantalla de ](img/api-key.png)

Ahora corré este código en R, reemplazando `<UID>` por tu UID y `<API Key>` con tu APi Key:

``` {.r}
ecmwfr::wf_set_key(service = "cds", user = "<UID>", key = "<API Key>")
```

Si sale todo bien, la función va a devolver un mensaje como este:

```
User <UID> for cds service added successfully in keychain
```

# Prueba de que todo anda bien

Finalmente, para probar que todo se instaló correctamente, corré este pequeño "Hello, world!"


```{·r}
request <- list(stream = "oper",
   levtype = "sfc",
   param = "167.128",
   dataset = "interim",
   step = "0",
   grid = "0.75/0.75",
   time = "00",
   date = "2014-07-01/to/2014-07-02",
   type = "an",
   class = "ei",
   area = "50/10/51/11",
   format = "netcdf",
   target = "tmp.nc")

data <- ecmwfr::wf_request(request)
metR::ReadNetCDF(data, vars = "t2m")
```

Primero deberías ver algo como esto:


```
Requesting data to the webapi service with username <your_email>
- staging data transfer at url endpoint or request id:
  https://api.ecmwf.int/v1/datasets/interim/requests/xxxxxxxXXXXxxxxXXXxxx

- timeout set to 1.0 hours
| polling server for a data transfer
```

Esto indica que el pedido de datos se envió al servicio y éste lo está procesando. 
Luego de unos segundos, va a empezar a descargar:

```
Downloading file
  |===========================================================| 100%
- file not copied and removed (path == tempdir())
- request purged from queue!
```

Y luego de que se descargue, la última línea lee los datos y tenés que ver esto:

```
         time latitude longitude      t2m
1: 2014-07-01    50.75     10.00 282.4616
2: 2014-07-01    50.75     10.75 282.2275
3: 2014-07-01    50.00     10.00 282.9887
4: 2014-07-01    50.00     10.75 282.9998
5: 2014-07-02    50.75     10.00 282.1887
6: 2014-07-02    50.75     10.75 281.8115
7: 2014-07-02    50.00     10.00 284.0701
8: 2014-07-02    50.00     10.75 283.1466
```


Si salió todo bien, ¡ya está todo listo para el tutorial!


# Plan B

Si no podés hacer que funcione, podés usar [este proyecto de RStudio Cloud](https://rstudio.cloud/project/2679681), el cual tiene todos paquetes instalados. 
Vas a tener que setear tus cuentas. 
