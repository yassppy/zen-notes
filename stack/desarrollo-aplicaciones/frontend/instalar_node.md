# instalar_node

Usar un gestor de versiones como NVM evita la acumulación de archivos basura, previene conflictos de rutas en Windows y permite cambiar de versión fácilmente sin afectar el rendimiento del sistema.

Actualizar a la versión de Node.js más estable y recomendada. Utilizar el que dice LTS:
```bookmark
https://nodejs.org/es/about/previous-releases
```


1. Ver lista de versiones instaladas de Node.js dentro NVM
```
nvm list
```

2. Instalar la versión LTS actual (v24.20.0) o la más reciente:

```bash
nvm install lts # más reciente
nvm install 24.20.0 # actual
```

3. Activar la versión instalada
```
nvm use 24.20.0
```

4. Limpiar versiones antiguas
```
nvm uninstall <numero_de_version>
```
