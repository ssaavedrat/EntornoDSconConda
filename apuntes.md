# Entorno de Trabajo para Ciencia de Datos con Jupyter Notebooks

## Ambientes Virtuales

¿Qué es un ambiente virtual? Es un entorno de trabajo aislado del sistema operativo que permite instalar paquetes y librerías sin afectar el funcionamiento de otros programas.

Cada proyecto puede tener su propio ambiente virtual, con sus propias versiones de paquetes y librerías. Esto permite que un proyecto no se vea afectado por cambios en otros proyectos.

## Instalar Conda (Anaconda) a través de la terminal en WSL

Conda es un gestor de paquetes y ambientes virtuales. Anaconda es una distribución de Python que incluye Conda, Jupyter Notebooks y muchas librerías y paquetes de Python. Conda no es exclusivo de Python, también puede instalar paquetes de R, Ruby, Lua, Scala, Java, JavaScript, C/ C++, FORTRAN y más.

Nos dirigimos al sitio web de [Anaconda](https://www.anaconda.com/download). Buscamos la versión de Linux y copiamos el link de descarga. En la terminal de WSL escribimos:

```bash
wget -O anaconda.sh https://repo.anaconda.com/archive/Anaconda3-2019.10-Linux-x86_64.sh
```

esto descargará el archivo de instalación de Anaconda en la carpeta actual con el nombre `anaconda.sh`. Ahora ejecutamos el archivo de instalación:

```bash
bash anaconda.sh
```

Seguimos las instrucciones de instalación. Al finalizar la instalación, cerramos la terminal y la volvemos a abrir, para que los cambios surtan efecto.

Podemos verificar que la instalación fue exitosa escribiendo en la terminal:

```bash
conda --version
```

## Conda: Crear y Actualizar Ambientes Virtuales

### Listar ambientes virtuales

Para listar los ambientes virtuales, escribimos en la terminal:

```bash
conda env list
```

### Crear un ambiente virtual

Para crear un ambiente virtual, escribimos en la terminal:

```bash
conda create --name nombre_ambiente
```

Si quiero paquetes específicos (con versiones específicas inclusive), escribo:

```bash
conda create --name nombre_ambiente paquete1 paquete2=1.8
```

### Activar y desactivar un ambiente virtual

Para activar el ambiente virtual, escribimos en la terminal:

```bash
conda activate nombre_ambiente
```

Para desactivar el ambiente virtual, escribimos en la terminal:

```bash
conda deactivate
```

### Versiones de Paquetes en un Ambiente Virtual

Para verificar las versiones de los paquetes instalados en el ambiente virtual, escribimos en la terminal:

```bash
conda list
```

En ocasiones los ambientes son grandes, si quiero filtrar por un paquete específico, escribo:

```bash
conda list paquete
```

Si queremos actualizar el paquete, escribimos en la terminal:

```bash
conda update paquete
```

Pero actualizará según la versión de Python que tengamos instalada. Si el paquete no es compatible no podrá resolver el ambiente y dará detalles de dicho error (dependencias no resueltas).

### Clone un Ambiente Virtual

Para clonar un ambiente virtual, escribimos en la terminal:

```bash
conda create --name nombre_nuevo_ambiente --copy --clone nombre_ambiente_a_clonar
```

## Conda: Eliminar Ambientes y Paquetes

Para eliminar un paquete, dentro del ambiente, escribimos en la terminal:

```bash
conda remove paquete
```

Para eliminar un ambiente virtual, escribimos en la terminal:

```bash
conda env remove --name nombre_ambiente
```

No se puede remover un ambiente virtual si está activo. Si el ambiente está activo, primero debe desactivarse (para volver al base).

