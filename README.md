# React + Vite

Vite es una herramienta de desarrollo web de próxima generación que combina un servidor de desarrollo rápido y un sistema de compilación eficiente. Está diseñado para ser simple, flexible y fácil de usar.

## Instalacion de Vite:

El proceso de instalación comienza con crear un nuevo proyecto (teniendo instalado node) y abriendo la consola en el proyecto. En la consola se ejecutará el siguiente comando:

```bash
    npm create vite
```

Y esto desplegará un apartado donde podrás poner el nombre del proyecto, una vez terminado de definir el nombre se desplegará una lista de frameworks que se pueden manejar con vite, en este caso vamos a estar trabajando con react y la variante que vamos a elegir será JavaScript + SWC.

Luego de esto para ejecutar el front vamos a ingresar a la carpeta con el nombre que creamos anteriormente y vamos a escribir

```bash
    npm install
```

para instalar los paquetes de node. Y después de esto ya se podrá ejecutar sin problemas el siguiente comando

```bash
    npm run dev
```

Así tendremos levantado nuestro servidor. Por defecto vite tiene un diseño básico con un icono de vite y react y un contador en el centro. Si al usar el puerto local funciona y se pueden observar estas vistas significa que la instalación y configuración inicial de vite fue un exito.

## Instalación de JEST 

Jest es un framework de pruebas JavaScript de código abierto desarrollado por Facebook. Es un marco de prueba completo que incluye una biblioteca de afirmaciones, un corredor de pruebas y soporte para pruebas unitarias, de integración y de aceptación.

Jest es una buena opción para probar aplicaciones React, ya que está diseñado específicamente para ello. Sin embargo, también se puede utilizar para probar cualquier aplicación JavaScript.

Para el proceso de instalación de JEST puede visitar la [documentación oficial de JEST](https://jestjs.io/docs/getting-started).

Sin embargo a continuación se pondrán paso a paso las opciones para realizar la instalación en el proyecto.

Inicialmente vamos a instalar jest

```bash
    npm install --save-dev jest
```

También vamos a instalar Babel, Babel es un compilador JavaScript que transforma el código JavaScript moderno en código compatible con navegadores antiguos y entornos no compatibles. Babel se utiliza para transformar el código JavaScript que utiliza características de ECMAScript 2015+, como clases, módulos, promesas y funciones flecha. Este código se transforma en código compatible con navegadores antiguos, como Internet Explorer 9 y Edge 12.

Ahora instalaremos babel:

```bash 
        npm install --save-dev babel-jest @babel/core @babel/preset-env
```

Una vez instalado babel vamos a crear un archivo crearemos un archivo en nuestro directorio raiz el cual se llamará babel.config.cjs que es cjs porque también necesitamos que lea codigo javascript escrito en commonJs.

El archivo va a contener la siguientes lineas de código: 

```JavaScript
module.exports = {
presets: [['@babel/preset-env', {targets: {node: 'current'}}]],
};
```

Ahora instalaremos nuestra ultima dependencia proveniente de la libreria de jest:

```bash
    npm install --save-dev @types/jest
```

Por último debemos dirigirnos a nuestro package.json y en el apartado de scripts agregar una nueva:

```json
 "scripts": {
    "dev": "vite",
    "build": "vite build",
    "lint": "eslint . --ext js,jsx --report-unused-disable-directives --max-warnings 0",
    "preview": "vite preview",
    "test": "jest --watchAll"
  },
```

Con esto la configuración básica estaría lista para poder realizar el respectivo testing. 

Para ejecutar el programa necesitaremos abrir dos consolas, en una ejecutaremos *npm run dev* y en la otra *npm run test*, en la consola del test podremos ver todo lo relacionado con los test.

## Creación del testing

1. Dentro de nuestra estructura de carpetas vamos a crear una que se llame test.

2. Vamos a crear otra carpeta como modo de ejemplo llamada version y ahí se alojaran los archivos que deseamos testear. Este procedimiento también se puede hacer con los componentes para poder así observar que funcionan correctamente.

3. Dentro de la carpeta de test se van a agregar los archivos creados en la otra carpeta. (para tener un poco más de orden en el código se puede copiar el nombre de la carpeta del archivo que se está testeando) Los nombres de los archivos van a ser **nombre.test.js** para que jest pueda identificar cuales son tipo test. 

Una vez seguidos estos pasos y configurando adecuadamente los testings en la terminal donde ejecutamos el test se podran evidenciar los test aprovados y los que no pasaron.
