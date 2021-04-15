# Bash 
> GNU Bash o simplemente Bash es un lenguaje de órdenes y shell de Unix escrito por Brian Fox para el Proyecto GNU. Es un intérprete de órdenes que generalmente se ejecuta en una ventana de texto donde el usuario escribe órdenes en modo texto. Bash también puede leer y ejecutar órdenes desde un archivo, llamado guion o 'script'.Se ha utilizado ampliamente como el intérprete de inicio de sesión(login) predeterminado para la mayoría de las distribuciones de GNU/Linux.

Los usuarios de OS X y la mayoría de las distribuciones de Linux tienen suerte pues ya cuentan con un Bash shell instalado por defecto. Para los usuarios de Windows, es necesario cubrir un paso extra e instalar Git Bash descargando la versión más reciente [en esta pagina](https://gitforwindows.org/).
## Navegando por el sistema de archivos de tu computadora
Puedes saber en qué directorio estás a través del comando pwd, que significa “imprime el directorio de trabajo” (print working directory).
```
pwd
```
Si usas OS X o Linux, tu computadora probablemente mostrará:
```
/usuarios/nombre-de-usuario
```
En Windows:
```
C:\users\user
```
Para obtener una lista de los archivos que están en ese directorio.
```
ls
```
A lo mejor lo único que quieres ver son los archivos TXT que están en tu directorio principal.
```
ls *.txt
```
Digamos que quieres más información.
```
-l    (La letra minúscula '' ell ''.) Lista en formato largo. (Ver más abajo). Si la salida es a un terminal, se genera una suma total para todos los tamaños de archivo en una línea antes de la lista larga.
```
```
ls -l
```
