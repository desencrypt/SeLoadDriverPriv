# SeLoadDriverPriv
SeLoadDriverPriv

Explicación de como aprovecharse del permiso SeLoadDriverPriv Windows 64

## Habilitar privilegio

Después de tener una shell de administrador y poder observar que tenemos el SeLoadDriverPrivilege aunque este deshabilitado, debemos de ejecutar el siguiente script para poder habilitarlo, podemos copiar y ejecutar en la misma shell.

```
.\Enable-SeLoadDriverPrivilege.ps1
```

## Compilar y ejecutar EoPLoadDriver

Para conseguir el ejecutable EoPLoadDriver.exe debemos compilar el archivo (en x64 y release) que se encuentra en https://github.com/TarlogicSecurity/EoPLoadDriver/ , sin embargo puede descargarlo en este mismo repositorio ya compilado.

Esto nos va a ayudar a poder subir un driver que pueda ser explotable, en este repositorio esta el driver capcom.sys con su exploit.
su uso es el siguiente:


Debemos ejecutar indicandole la ruta de la clave de registro y la ruta en la cual se encuentra el driver que queremos subir

```
.\EoPLoadDriver.exe System\CurrentControlSet\ejemplo C:\usuario\Desktop\Capcom.sys
```

Puede comprobar si se ha subido con exito
https://www.nirsoft.net/utils/driverview.html

## Explotación

Para explotar el driver Capcom.sys, debemos compilar el exploit en x64 y release que se encuentra en la siguiente ruta (https://github.com/tandasat/ExploitCapcom), en este repositorio ya tendra el exploit compilado para poder ejecutarlo desde la misma shell.

Desde la misma shell ejecutamos lo siguiente y nos abrira una nueva terminal como administrador

```
.\ExploitCapcom.exe
```

## FINAL

Ya terminamos la escalada de privilegios y tendriamos una shell como administrador 


## Ayudas

<ul>
  <li>https://www.tarlogic.com/es/blog/explotacion-de-la-directiva-cargar-y-descargar-controladores-de-dispositivo-seloaddriverprivilege/</li>
  <li>https://github.com/FuzzySecurity/Capcom-Rootkit/tree/master/Driver</li>
  <li>https://github.com/tandasat/ExploitCapcom</li>
  <li>https://github.com/TarlogicSecurity/EoPLoadDriver</li> 
</ul>

