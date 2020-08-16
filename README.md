# AsesoriaLinuxEnsambleAnotacion
Este repositorio fue creado para guardar la información requerida para una asesoría de Linux, Ensamble y Anotación

## Conexión

```sandra@san:$ ssh user@10.ip.10.00

sandra@san:$ user@10.ip.10.00’s password:
123123123

sandra@san: Host key not found from the 
list of known hosts.Are you sure you want 
to continue connecting (yes/no)

sandra@san:yes

user@usr:$
```

## Comandos

### Navegación

- `pwd` Comando que sirve para saber el directorio actual (Print Working Directory)
- `cd` Para cambiar de directorio de trabajo se utiliza cd (Change Directory)
- `ls` Para listar los archivos que hay en el directorio de trabajo se utiliza ls (LiSt)

| Comodín | Significado |
|---------|-------------|
| . | Directorio actual |
| .. | Directorio padre |
| ~ | Directorio “home” |
| - | Directorio previo |


### Sistema

```
man
who
df
du
free
top
date
echo
ping
history
uname
```

### Manipulación de archivos

#### Permisos

|  | Valor | Propietario |   Grupo   |   Todos   |
|--|-------|-------------|-------|-------|
|**Posición**| | **1** | **2** | **3** |
|**Lectura**| **4** | x | x  | x |
|**Escritura**| **2** | x | x  |  |
|**Ejecución**| **1** | x |   |  |
|  |  | **7** | **6**  | **4** |

```
chmod 764 myFile.txt
```
 ¿Qué hace?
 
 #### Comandos
 
 - `cat archivo1.txt archivo2.csv archivo3.tsv`
 - `cp /ruta/archivoOrigen.txt /ruta/destino/`
 - `mv /ruta/archivoOrigen.txt /ruta/destino/`
 - `rm archivo.txt`
 - `mkdir folder`
 - `rmdir folder`
 - `nano archivoNuevo.txt`
 
 [Nano]https://staffwww.fullcoll.edu/sedwards/Nano/IntroToNano.html



### Operaciones a los archivos

Para imprimir las primeras lineas
```
head archivo.txt
```
Para imprimir las últimas lineas
```
tail archivo.txt
```
Para dividir un archivo
```
split -l 10 archivo.txt
split -n 6 archivo.txt
```
Para leer una archivo por partes
```
less myArchivo.txt
```
Conocer el tamaño:

- `wc -l archivo.txt` Por lineas
- `wc -c archivo.txt` Por bytes
- `wc -m archivo.txt` Por caracteres
- `wc -w archivo.txt` Por palabras
- `wc -L archivo.txt` El tamaño del renglón más gránde

Para comparar dos archivos
```
diff archivo1.txt archivo2.txt
```

Para ordenar
```
sort myArchivo.txt
```

Para eliminar lineas identicas contiguas
```
uniq myArchivo.txt
uniq -d myArchivo.txt ## solo imprime las lineas duplicadas
uniq -c myArchivo.txt ## imprime el conteo de replicas
```

Cortar por columnas

 - `-c` Por caracteres
 - `-f` Por campos
 - `-d` Establecer el delimitador de campos, por defecto es TAB
```
cut  -c 5 myArchivo.txt ## imprime el caracter 5 de cada linea
cut -f 1-5 myArchivo.txt ## imprime los campos 1, 2, 3, 4 y 5 (separados por TAB)
cut -d "," -f 1,3-5 myArchivo.txt ## imprime los campos 1, 3, 4 y 5 (separados por ,)
```

Cambiar caracteres

```
cat archivo.txt | tr "\t" ","
cat archivo.txt | tr [a-z] [A-Z]
```

### Entradas y salidas

Redireccionar la salida estándar
```
who > usuarios.txt
ls -lh > lista_archivos.txt
ls -lh >> usuarios.txt ## Para adicionar en lugar de reescribir
```

Redireccionar la entrada estándar
```
cat < usuarios.txt
```

Redireccionar el error estándar
```
ls -l video.mpg 2> error.txt
ls -l video.gif 2>> error.txt ## Para adicionar en lugar de reescribir
```

Redireccionar la salida de un comando a la entrada de otro
```
ls -al /etc | sort | uniq | less
```

| Redirección | Acción  |
|-------------|---------|
| > |Redirige stdout a fichero |
| 2> |Redirige stderr a fichero |
| >& | Redirige stdout y stderr a fichero |
| < | Redirige stdin a un comando |
| \| | Redirige stdout hacia stdin de otro comando |
| >> | Añade stdout a fichero |
| 2>> | Añade stderr a fichero |
| >>& | Añade stdout y stderr a fichero |





