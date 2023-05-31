## General
Esta guia de estilos almacena los colores y estilos tipográficos de Wally, existen tres formas de aplicar los style guide a un proyecto, mediante CSS, Tailwind o Sass (En el caso de sass se puede aplicar a la mayoría de los framewroks como boostrap.)

Para empezar a usar el style guide de Wally es necesario descargar este repositorio, seguidamente puede implementar el style guide en CSS, Tailwind o SASS (Boostrap, etc).

## 1.- CSS
Para comenzar a usar nuestros estilos de CSS es necesario descargar este repositorio, seguidamente acceder En la carpeta css/ dentro de la cual encontraras dos archivos, en el primer archivo **w-style-guide.css** encontrarás los estilos de wally sin ser minificados ya que el propósito de este archivo es facilitar la lectura de los estilos. Este primer archivo no se recomienda usarlo directamente en una página porque no está minificado. Para utilizar la versión minificada se debe usar el archivo **w-style-guide-minify.css** 

### 1.1 Colores
Los colores de Wally están representados como custom properties (variables CSS)
```
:root {
  --cool-gray-50: #FFFFFF;
  --cool-gray-100: #F9FAFB;
  --cool-gray-200: #F3F4F6;
  --cool-gray-300: #E5E7EB;
  --cool-gray-400: #D1D5DB;
  --cool-gray-500: #6B7280;
  --cool-gray-600: #374151;
  --cool-gray-700: #12131F;
  --green-50: #E7F8EE;
  --green-100: #A2E7BF;
  --green-200: #25B562;
  --green-300: #1A6B3C;
  --blue-50: #EFF6FF;
  --blue-100: #BFDBFE;
  --blue-200: #3B82F6;
  --blue-300: #1D4ED8;
  --red-50: #FEF2F2;
  --red-100: #FECACA;
  --red-200: #EF4444;
  --red-300: #B91C1C;
  --yellow-50: #FEFCE8;
  --yellow-100: #FEF08A;
  --yellow-200: #EAB308;
  --yellow-300: #A16207;
  --light-blue: #3293CF;
  --scarlet: #F65E47;
  --amber: #FDC980;
  --overlay: rgba(5,3,3,0.75);
}
```

Estas variables a su vez se encuentran representadas como clases de CSS, se puede aplicar como color de fondo o como color de texto, para ello solo es necesario agregar **bg** antes del nombre del color para aplicar el color como fondo y para aplicar un color a un texto solo es necesario agregar **c** antes del nombre del color. 
 ```
/* Background */
.bg-cool-gray-50 {
    background-color: var(--w-cool-gray-50);
}
/* Color */
.c-cool-gray-50 {
    color: var(--w-cool-gray-50);
}
```

Para aplicar estas clases solo es necesario agregarlas a un elemento HTML.
```
<header class="bg-cool-gray-50">Soy un Header</header>
```

### 1.2 Tipografias
La siguiente lista muestra el nombre de clase de las tipografias de Wally.

```
/* Typography class */
.text-6xl-bold  -> 60px Bold
.text-6xl-regular  -> 60px Regular

.text-5xl-bold  -> 48px Bold
.text-5xl-regular  -> 48px Regular

.text-4xl-bold  -> 36px Bold
.text-4xl-regular  -> 36px Regular

.text-3xl-bold  -> 30px Bold
.text-3xl-regular  -> 30px Regular

.text-2xl-bold  -> 24px Bold
.text-2xl-regular  -> 24px Regular

.text-xl-bold  -> 20px Bold
.text-xl-regular  -> 20px Regular

.text-lg-bold  -> 18px Bold
.text-lg-regular  -> 18px Regular

.text-base-bold  -> 16px Bold
.text-base-regular  -> 16px Regular

.text-sm-bold  -> 14px Bold
.text-sm-regular  -> 14px Regular

.text-xs-bold  -> 12px Bold
.text-xs-regular  -> 12px Regular

.text-small-bold  -> 10px Bold
.text-small-regular  -> 10px Regular

```

Para aplicar las tipografías de Wally solo es necesario usar las clases en una etiqueta de texto
```
<h2 class="text-6xl-regular">Soy un titular</h2>
```

El texto también puede ser responsive. Para lograrlo solo debes anteponer las siguientes siglas a tu clase de texto.
```
 /* breakpoints */
sm  > 640px;
md -> 768px;
lg -> 1024px;
xl -> 1280px;
xxl -> 1536px;
```
Un ejemplo: **md-text-6xl-bold** esto aplicaría a una medida de 60px al texto cuando el viewport tenga 768px de ancho.  Esto sería lo mismo que crear la siguiente media query.
```
@media (min-width: 768px) {
    .md-text-6xl-bold {
        font-family: "Inter", sans-serif;
        font-size: 60px;
        line-height: 64px;
        font-weight: 700;
    }
}    
```
Pero en lugar de crearla, solo tienes que agregarla como una clase a tu etiqueta de texto.
```
<h2 class="md-text-6xl-bold">Soy un titular</h2>
```
### 1.3 Figma
Hemos preparado un archivo de figma que te explica como identificar que colores y que tipografías debes usar para cada caso.
https://www.figma.com/file/6S1u1I7a7KLurDM0YqYjPV/Style-Guide?node-id=2740%3A14431&t=J1UwftocUgtKOUTJ-1  te invitamos a revisarlo.

Recuerda que si no tienes acceso, puedes solicitar acceso como "viewer" con tu cuenta de Wally.


## 2.- Tailwind
Si quieres usar los estilos de Wally en Tailwind solo es necesario agregar un tema a tu archivo de configuración de Tailwind.

Para agregar el tema debes copiar al archivo de configuración que se encuentra en **tailwind/tailwind.config.js**.

Ahora solo debes copiar el contenido de **theme** a tu archivo de configuración.

```
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./**/*.{html,js}"],
  theme: {
    colors: {
      'cool-gray-50': '#FFFFFF',
      'cool-gray-100': '#F9FAFB',
      'cool-gray-200': '#F3F4F6',
      'cool-gray-300': '#E5E7EB',
      'cool-gray-400': '#D1D5DB',
      'cool-gray-500': '#6B7280',
      'cool-gray-600': '#374151',
      'cool-gray-700': '#12131F',
      'green-50': '#E7F8EE',
      'green-100': '#A2E7BF',
      'green-200': '#25B562',
      'green-300': '#1A6B3C',
      'blue-50': '#EFF6FF',
      'blue-100': '#BFDBFE',
      'blue-200': '#3B82F6',
      'blue-300': '#1D4ED8',
      'red-50': '#FEF2F2',
      'red-100': '#FECACA',
      'red-200': '#EF4444',
      'red-300': '#B91C1C',
      'yellow-50': '#FEFCE8',
      'yellow-100': '#FEF08A',
      'yellow-200': '#EAB308',
      'yellow-300': '#A16207',
      'light-blue': '#3293CF',
      'scarlet': '#F65E47',
      'amber': '#FDC980',

    },
  },
}
```

### 2.1 ¿Cómo aplicar colores?
Con Tailwind es mucho más sencillo aplicar los colores a un elemento, ya que se generan de forma automática luego de agregar los colores a **theme**

Para fondos, solo tienes que agregar **bg** antes del nombre del color, Ejemplo: **bg-green-200**

```
<header class="bg-green-200">Soy un Header</header>
```

Para aplicar colores sobre los textos, solo es necesario agregar **text** antes del nombre del color, Ejemplo: **text-cool-gray-600**

```
<h2 class="text-cool-gray-600">Soy un titular</h2>
```

### 2.2 Tipografías de Wally
Tailwind tiene la particularidad de usar la misma tipografía que usa Wally. Asi que solo tienes que revisar la documentación de Tailwind https://tailwindcss.com/docs/font-size .

### 2.3 Optimización
1.- Recomendamos solo usar dos tipos de pesos de fuentes en Tailwind **Normal** que es igual a **Regular** y **Bold** Esto ayudará a mejorar el performance de cualquier proyecto.

2.- Tailwind cuenta con comandos CLI que permiten minificar tu codigo CSS y solo incluir las clases que usas y no las que no se utilizan. Así que no necesitas usar Purify.

## 3.- SASS
Sass es un preprocesador de CSS el cual nos permite dividir los estilos de CSS en una Arquitectura como ITCSS o Atomic Design, con el objetivo de crear una forma de trabajo más escalable con nuestros estilos. 

El style guide de Wally usa ITCSS y Atomic design quedando una estructura de carpetas de la siguiente forma.

```
/styles
├── /atoms
│       ├── button.scss
├── /generic
│       └── reset.scss
├── /molecules
│       ├── beta
├── /organisms
│       ├── beta
├── /settings
│       ├── breakpoints.scss
│       └── colors.scss
│       └── space.scss
│       └── typography.scss
├── utilities
│       ├── colors.scss
│       └── spacing.scss
│       └── typography.scss
└── index.scss
```
Este árbol de carpetas se encuentra dentro de la carpeta sass/styles

Estos archivos a su vez se encuentran importados desde index.scss, donde primero se importa la fuente, seguidamente las variables y por último las utilidades y átomos.

```
@import "./settings/typography.scss";
@import "./settings/breakpoints.scss";
@import "./settings/colors.scss";
@import "./settings/space.scss";
@import "./generic/reset.scss";
@import "./utilities/spacing.scss";
@import "./utilities/colors.scss";
@import "./utilities/typography.scss";
@import "./atoms/buttons.scss";
```

### 3.1 Colores
Los colores de Wally se encuentran en styles/settings/colors.scss
```
$cool-gray-50: #FFFFFF;
$cool-gray-100: #F9FAFB;
$cool-gray-200: #F3F4F6;
$cool-gray-300: #E5E7EB;
$cool-gray-400: #D1D5DB;
$cool-gray-500: #6B7280;
$cool-gray-600: #374151;
$cool-gray-700: #12131F;
$green-50: #E7F8EE;
$green-100: #A2E7BF;
$green-200: #25B562;
$green-300: #1A6B3C;
$blue-50: #EFF6FF;
$blue-100: #BFDBFE;
$blue-200: #3B82F6;
$blue-300: #1D4ED8;
$red-50: #FEF2F2;
$red-100: #FECACA;
$red-200: #EF4444;
$red-300: #B91C1C;
$yellow-50: #FEFCE8;
$yellow-100: #FEF08A;
$yellow-200: #EAB308;
$yellow-300: #A16207;
$light-blue: #3293CF;
$scarlet: #F65E47;
$amber: #FDC980;
$overlay: rgba(5,3,3,0.75);
```

Estas variables a su vez se encuentran representadas como clases de CSS, se puede aplicar como color de fondo o como color de texto, para ello solo es necesario agregar **bg** antes del nombre del color para aplicar el color como fondo y para aplicar un color a un texto solo es necesario agregar **c** antes del nombre del color. 
 ```
/* Background */
.bg-cool-gray-50 {
    background-color: $cool-gray-50;
}
/* Color */
.c-cool-gray-50 {
    color: $cool-gray-50;
}
```

Para aplicar estas clases solo es necesario agregarlas a un elemento HTML.
```
<header class="bg-cool-gray-50">Soy un Header</header>
```


### 3.2 Tipografias
La siguiente lista muestra el nombre de clase de las tipografias de Wally.

```
/* Typography class */
.text-6xl-bold  -> 60px Bold
.text-6xl-regular  -> 60px Regular

.text-5xl-bold  -> 48px Bold
.text-5xl-regular  -> 48px Regular

.text-4xl-bold  -> 36px Bold
.text-4xl-regular  -> 36px Regular

.text-3xl-bold  -> 30px Bold
.text-3xl-regular  -> 30px Regular

.text-2xl-bold  -> 24px Bold
.text-2xl-regular  -> 24px Regular

.text-xl-bold  -> 20px Bold
.text-xl-regular  -> 20px Regular

.text-lg-bold  -> 18px Bold
.text-lg-regular  -> 18px Regular

.text-base-bold  -> 16px Bold
.text-base-regular  -> 16px Regular

.text-sm-bold  -> 14px Bold
.text-sm-regular  -> 14px Regular

.text-xs-bold  -> 12px Bold
.text-xs-regular  -> 12px Regular

.text-small-bold  -> 10px Bold
.text-small-regular  -> 10px Regular

```

Para aplicar las tipografías de Wally solo es necesario usar las clases en una etiqueta de texto
```
<h2 class="text-6xl-regular">Soy un titular</h2>
```

El texto también puede ser responsive. Para lograrlo solo debes anteponer las siguientes siglas a tu clase de texto.
```
 /* breakpoints */
$sm  > 640px;
$md -> 768px;
$lg -> 1024px;
$xl -> 1280px;
$xxl -> 1536px;
```
Un ejemplo: **md-text-6xl-bold** esto aplicaría a una medida de 60px al texto cuando el viewport tenga 768px de ancho.  Esto sería lo mismo que crear la siguiente media query.
```
@media (min-width: $md) {
    .md-text-6xl-bold {
        font-family: "Inter", sans-serif;
        font-size: 60px;
        line-height: 64px;
        font-weight: 700;
    }
}    
```
Pero en lugar de crearla, solo tienes que agregarla como una clase a tu etiqueta de texto.
```
<h2 class="md-text-6xl-bold">Soy un titular</h2>
```
