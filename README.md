# Style Guide
Este repositorio almacena los estilos generales de Wally, 

## 1.- CSS
Para comenzar puedes descargar este repositorio y una vez descargado. Debes incluir dos archivos a tu proyecto, el primero lo encontrarás en **build/css/variables.css** , este archivo guarda los colores de Wally en variables de CSS.

El segundo archivo que necesitaras se encuentra en la siguiente ruta **styles/styles-wally.css** este archivo contiene reglas CSS para colores y tipografías.

Seguidamente, debes cambiar la ruta del import del archivo **styles-wally.css** para que siempre apunte a las variables CSS. 
```
/* Import variables from figma */
@import ".././build/css/variables.css";
```
Con todo configurado puedes empezar a aplicar los estilos de Wally a tu proyecto.

### ¿Cómo aplicar colores?
Cada grupo de colores generalmente se encuentra divido en una escala de 50 al 300. Existe otro grupo de colores que comprende desde 50 hasta 700.
```
:root {
  --w-cool-gray-50: #FFFFFF;
  --w-cool-gray-100: #F9FAFB;
  --w-cool-gray-200: #F3F4F6;
  --w-cool-gray-300: #E5E7EB;
  --w-cool-gray-400: #D1D5DB;
  --w-cool-gray-500: #6B7280;
  --w-cool-gray-600: #374151;
  --w-cool-gray-700: #12131F;
  --w-green-50: #E7F8EE;
  --w-green-100: #A2E7BF;
  --w-green-200: #25B562;
  --w-green-300: #1A6B3C;
  --w-blue-50: #EFF6FF;
  --w-blue-100: #BFDBFE;
  --w-blue-200: #3B82F6;
  --w-blue-300: #1D4ED8;
  --w-red-50: #FEF2F2;
  --w-red-100: #FECACA;
  --w-red-200: #EF4444;
  --w-red-300: #B91C1C;
  --w-yellow-50: #FEFCE8;
  --w-yellow-100: #FEF08A;
  --w-yellow-200: #EAB308;
  --w-yellow-300: #A16207;
  --w-light-blue: #3293CF;
  --w-scarlet: #F65E47;
  --w-amber: #FDC980;
  --w-overlay: rgba(5,3,3,0.75);
}
```

Estas variables a su vez se encuentran representadas como clases de CSS en el archivo **styles-wally.css** .
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

### Tipografías de Wally
Para aplicar las tipografías de Wally solo es necesario usar las clases del archivo **styles-wally.css** .
```
/* Typography class */
.text-6xl-bold {
    font-family: "Inter", sans-serif;
    font-size: 60px;
    line-height: 64px;
    font-weight: 700;
}
.text-6xl-regular {
    font-family: "Inter", sans-serif;
    font-size: 60px;
    line-height: 64px;
    font-weight: 400;
}
```
Seguidamente, aplicarlas a una etiqueta de texto HTML.
```
<h2 class="text-6xl-regular">Soy un titular</h2>
```

El texto también puede ser responsive. Para lograrlo solo debes anteponer las siguientes siglas a tu clase de texto.
```
 /* breakpoints */
sm: 576px;
md: 768px;
lg: 992px;
xl: 1200px;
xxl: 1400px;
```
Un ejemplo: **md-text-6xl-bold** esto aplicaría una medida de 60px al texto cuando el viewport tenga 768px de ancho.  Esto sería lo mismo que crear la siguiente media query.
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
### Figma y Style Guide
Hemos preparado un archivo de figma que te explica como identificar que colores y que tipografías debes usar para cada caso.
https://www.figma.com/file/6S1u1I7a7KLurDM0YqYjPV/Style-Guide?node-id=2740%3A14431&t=J1UwftocUgtKOUTJ-1  te invitamos a revisarlo.

Recuerda que si no tienes acceso, puedes solicitar acceso como "viewer" con tu cuenta de Wally.

### Optimización 
Para optimiar tu CSS te recomentamos usar https://purifycss.online/ 

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

### ¿Cómo aplicar colores?
Con Tailwind es mucho más sencillo aplicar los colores a un elemento, ya que se generan de forma automática luego de agregar los colores a **theme**

Para fondos, solo tienes que agregar **bg** antes del nombre del color, Ejemplo: **bg-green-200**

```
<header class="bg-green-200">Soy un Header</header>
```

Para aplicar colores sobre los textos, solo es necesario agregar **text** antes del nombre del color, Ejemplo: **text-cool-gray-600**

```
<h2 class="text-cool-gray-600">Soy un titular</h2>
```

### Tipografías de Wally
Tailwind tiene la particularidad de usar la misma tipografía que usa Wally. Asi que solo tienes que revisar la documentación de Tailwind https://tailwindcss.com/docs/font-size .

### Optimización
1.- Recomendamos solo usar dos tipos de pesos de fuentes en Tailwind **Normal** que es igual a **Regular** y **Bold** Esto ayudará a mejorar el performance de cualquier proyecto.

2.- Tailwind cuenta con comandos CLI que permiten minificar tu codigo CSS y solo incluir las clases que usas y no las que no se utilizan. Así que no necesitas usar Purify.