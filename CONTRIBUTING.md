# Cómo contribuir y usar esta plantilla

Esta es una guía de lo que debes tener en cuenta para utilizar y contribuir con esta plantilla de cortes HTML.

## Primeros pasos 🤖

1. **Familiarízate con Astro JS:** Asegúrate de entender cómo funciona Astro JS. Puedes encontrar información útil en [la documentación oficial de Astro.](https://docs.astro.build/en/getting-started/)

También tendrás acceso a las siguientes grabaciones de capacitación:
   👍 [Primera sesión de capacitación Astro JS](https://drive.google.com/file/d/1U1BEY2LF1k3ZcBaAofJFx4OFe3K0p0_J/view?usp=sharing)
   👍 [Segunda sesión de capacitación Astro JS](https://drive.google.com/file/d/1mGhdKSl5G2Wy-lBK9LMGyAe5l8SAiht4/view?usp=sharing)

2. **Configura tu entorno de desarrollo:** Es recomendable utilizar `pnpm` como gestor de paquetes por su eficiencia y rapidez. Si no tienes `pnpm` instalado, puedes hacerlo ejecutando `npm install -g pnpm`.

## Cómo utilizarlo

Ten en cuenta la siguiente estructura de carpetas y dónde están alojados cada archivo:

```text
./
|-- public/
|-- src/
|   |-- components/ -> Componentes reutilizables
|   |-- const/ -> Almacenamiento de programas en formato
|       └─- Ciberseguridad-para-ejecutivos.js -> Archivo que almacena la mayoría del contenido del curso
|       └─- # Más cursos
|
|   |-- layout/ -> Estructura que envuelve todos los cortes HTML
|   |-- pages/ -> Páginas 
|       └─- index.astro  -> Página 1 o primer corte HTML del programa
|       └─- index2.astro -> Página 2 o segundo corte HTML del programa
|       └─- # Más páginas
|
|   |-- section/ -> Secciones reutilizables
```

### Crear un nuevo programa

Sigue los siguientes pasos para crear un nuevo curso y los cortes HTML:

1. **Duplica la estructura:** Dentro de la carpeta `/const` vas a encontrar programas ya creados. Tendrás que duplicar cualquier archivo de estos y cambiarle el nombre por `(Nombre-del-Programa.js)`.

2. **Ajusta los valores del curso:** Tendrás que cambiar los valores por los del curso que vas a crear.

```js
export const PROGRAMA = {
    tipo: 'Programa',
    titulo: 'Ciberseguridad para Ejecutivos',
    banner: 'cpe-banner-2024',
    ... Más información // Encontrarás la estructura completa en algún programa terminado
}
```

3. **Crear el corte HTML:** Tendrás que ir a la carpeta de `/pages` donde encontrarás la siguiente estructura:

```text
|-- pages/ -> Carpeta de páginas
    └─- index.astro -> Página 1 o primer corte HTML del programa
    └─- index2.astro -> Página 2 o segundo corte HTML del programa
    └─- # Más páginas
```

Cada página `index[n].astro` corresponde a un corte HTML. Dentro de cada una ya se encuentra la estructura de los cortes HTML creada, y lo que tendrás que hacer es actualizar el archivo que trae toda la configuración e información del programa.

```js
import { PROGRAMA, CONFIG } from "../const/<Nombre del archivo del programa que creó>"; // Así se ve la importación 
```

Luego de importar la información necesaria para el mailing, es necesario que revises y ajustes los textos que falten en cada corte HTML.

4. **Hacer un `build` del proyecto:** En este paso es necesario validar que todos los cortes HTML estén bien configurados. Para ello, ejecuta el comando `pnpm run build`, el cual compilará todo el proyecto y generará los archivos `.html` que vamos a organizar en el siguiente paso.

5. **Organizar los archivos:** Cuando generes la versión compilada del proyecto, se creará una carpeta llamada `/dist` en la raíz del proyecto que contendrá los archivos que vamos a organizar. Para generar la estructura de carpetas que se le entrega al cliente, guíate con las buenas <a href="#bp-estructura-carpetas">prácticas para generarla</a>.

6. **Subir al espacio compartido:** Una vez tengamos organizados los archivos para entregar al cliente, se subirán a la carpeta [compartida de drive](https://drive.google.com/drive/folders/1OW-XtrmSb4jvmd2SFca3sgP6DqR8ostC?usp=sharing).

## Buenas prácticas y recomendaciones

Esta es una guía rápida de buenas prácticas para crear estructuras de carpetas y nombrar imágenes que se subirán al CDN de [CloudFlare](https://www.cloudflare.com/es-es/). Si no tienes cuenta, puedes contactar a gcelis@vereon.co.

### Nombre de banner

Para crear el nombre de un banner, ten en cuenta la siguiente estructura:

**Ejemplo:**

- Nombre del programa: Ciberseguridad para Ejecutivos
- Nombre de la imagen: `cpe-banner-2024`

[Iniciales de cada palabra del programa - banner (Identificar tipo de imagen) - Año del programa]

### Nombre de imágenes de docentes

Para crear el nombre de la imagen de un docente, ten en cuenta la inicial de cada nombre del docente.

**Ejemplo:**

- Nombre del docente: Mario Sigfrido Huertas López
- Nombre de la imagen: `mshlopez`

[Inicial de cada nombre del docente y la última palabra se escribe completa]

**Nota:** Se deben optimizar las imágenes antes de subirlas al CDN y conservar su formato en `.jpg` si no tienen fondo y `.png` si la imagen tiene fondo.

Herramientas para optimizar imágenes:

1. [squoosh.app](https://squoosh.app/)
2. [iloveimg.com](https://www.iloveimg.com/es/comprimir-imagen)