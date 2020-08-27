# worky-prueba

### Descripción del proyecto
Proyecto realizado para Worky

__Tecnología utilizada__
- Vue
- JS
- SASS
- Bulma

__Argumento__
Se eligió un desarrollo web (front-end) para un fácil acceso y rápido desarrollo.
Vue fue el framework de preferencia para empatar con la tecnología utilizada por Worky.
SASS y Bulma para más rapidez en la interfáz gráfica (y no hacer todo _a mano_)

### Arquitectura GIT
- Master: rama lista para pasar a producción.
- Development: rama en la que se agregan funcionalidades.
  

### Instalación de dependencias

```
//*** usando yarn ***
yarn install

//*** usando npm ***
npm install

```

### Iniciar proyecto localmente

```
//*** usando yarn ***
yarn serve

//*** usando npm ***
npm run serve
```

### Mejoras
Debido a que un demo y tenía que ser de rápido desarrollo se omitieron las siguiente funcionalidades:
- Uso de variables de entorno _.env_:
Al tener únicamente una url y sin información sensible se decidió no utilizar variables de entorno para la fácil instalación del proyecto en otras computadoras
- Pruebas unitarias | e2e
Al ser un desarrollo sencillo, con pocos componentes y tiempo limitado, no se implementaron las pruebas
