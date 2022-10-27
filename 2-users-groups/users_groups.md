# Usuarios, grupos, `etc/passwd` e `etc/shadow`

**Índice**

- [Usuarios, grupos, `etc/passwd` e `etc/shadow`](#usuarios-grupos-etcpasswd-e-etcshadow)
  - [Fichero /etc/passwd](#fichero-etcpasswd)
    - [¿Qué es el fichero /etc/passwd?](#qué-es-el-fichero-etcpasswd)
    - [Formato del archivo](#formato-del-archivo)



## Fichero /etc/passwd


### ¿Qué es el fichero /etc/passwd?
Este fichero almacena información esencial, que se requiere durante el inicio de sesión en linux. En otras palabras, almacena información de la cuenta del usuario. /etc/passwd es un archivo de texto sin formato. Contiene una lista de las cuentas del sistema, que proporciona información útil para cada cuenta, como ID de usuario, ID de grupo, directorio de inicio, shell y más.

El archivo /etc/passwd debe tener permiso de lectura general, ya que muchas utilidades de comando lo usan para asignar ID de usuario a nombres de usuario. Sin embargo, el acceso de escritura a /etc/passwd solo debe limitarse para la cuenta de superuser/root. 

### Formato del archivo

Contiene una entrada por línea para cada usuario (cuenta de usuario) del sistema. Todos los campos están separados por un (:). Total de siete campos de la siguiente manera.


**Nombre de usuario:** se utiliza cuando el usuario inicia sesión. Debe tener entre 1 y 32 caracteres de longitud.

**Contraseña:** un carácter x indica que la contraseña cifrada se almacena en el archivo /etc/shadow. Tenga en cuenta que debe usar el comando passwd para calcular el hash de una contraseña escrita en la CLI o para almacenar / actualizar el hash de la contraseña en el archivo /etc/shadow.

**ID de usuario (UID):** a cada usuario se le debe asignar una ID de usuario (UID). El UID 0 (cero) está reservado para root y los UID 1-99 están reservados para otras cuentas predefinidas. El sistema reserva UID 100-999 adicionales para cuentas / grupos administrativos y del sistema.

**ID de grupo (GID):** la ID de grupo principal (almacenada en /etc/group file)

**Información de ID de usuario:** el campo de comentario. Le permite agregar información adicional sobre los usuarios, como el nombre completo del usuario, el número de teléfono, etc. Este campo se utiliza mediante un comando de dedo.
Directorio de inicio: la ruta absoluta al directorio en el que estará el usuario cuando inicie sesión. Si este directorio no existe, el directorio de usuarios se convierte en /.

**Comando/shell:** la ruta absoluta de un comando o shell (/bin/bash). Típicamente, esto es un caparazón. Tenga en cuenta que no tiene que ser un shell