📘 Portafolio de Evidencias – Calculadoras Unificadas
Tecnológico de Software
Materia: Fundamentos de Álgebra
Alumno: Ángel Abraham Lugo Sáenz
Grupo: B
Actividad #19 — Portafolio de Evidencias de Proyectos HTML/CSS/JS
📚 Índice

Objetivo del Proyecto

Estructura del Proyecto

Logros del Proyecto

Unificación Visual y Estilo Global

Por qué se utilizó tema_calculadorascss

Integración de Calculadoras mediante iframes

Animación Suave y Carga Dinámica

Aprendizajes Clave

Buenas Prácticas en Git

Comentario Final

🎯 Objetivo del Proyecto

Este repositorio contiene la integración y visualización unificada de 7 calculadoras algebraicas, cada una desarrollada como parte de diferentes actividades de la materia Fundamentos de Álgebra.

El objetivo principal fue reunir todas las calculadoras en una sola página (index.html), manteniendo sus funcionalidades originales y logrando una presentación profesional, uniforme y navegable, utilizando únicamente:
HTML
CSS
JavaScript

```

📂 Estructura del Proyecto
/
├─ index.html                → Página principal que unifica todo
├─ calculadoras_unificadas.js
├─ calculadoras_unificadas.css
└─ actividades/
      ├─ Actividad_6_Angel_Lugo.html
      ├─ 1-B_actividad_2_Angel_lugo.html
      ├─ 1B_Actividad_04_Angel_Lugo.html
      ├─ Actividad8_Angel_Lugo.html
      ├─ Activiad10_Angel_Lugo.html
      ├─ 1B_A12_Angel_Lugo.html
      └─ 1B_A14_Angel_Lugo.html
      └─ tema_calculadoras.css   ← Estilo global que unifica todas las calculadoras

```
🚀 Logros del Proyecto

✅ Unificación visual de 7 calculadoras algebraicas mediante iframes.

✅ Todas las calculadoras muestran misma tipografía, colores y estilo base.

✅ Se eliminaron animaciones RGB y fondos inconsistentes.

✅ Navegación vertical suave con scroll-behavior.

✅ Aparición animada de secciones con IntersectionObserver.

✅ Diseño oscuro homogéneo basado en escala de grises.

✅ Separación clara entre:

Estilo global (fuera del iframe)

Estilo unificador dentro del iframe

🎨 Unificación Visual y Estilo Global

Cada calculadora tenía inicialmente:

Fuentes diferentes

Colores distintos (morado, azul, degradados)

Fondos animados RGB

Botones personalizados

Estilos que no combinaban entre sí

Esto hacía que al integrarlas se vieran como 7 proyectos separados.

✔ Solución

Se creó un archivo especial dentro de /actividades llamado:

```
tema_calculadoras.css
```

Este archivo contiene un tema oscuro global, con:

Tipografía única -> Arial, sans-serif

Fondos unificados -> #111

Inputs estilizados

Botones uniformes

Tablas estilizadas

Controles visuales consistentes

Eliminación de animaciones con:

```
* {
  animation: none !important;
  transition: none !important;
}
```

El propósito fue que todas las calculadoras parecieran parte del mismo sistema profesional, sin importar cómo fueron creadas originalmente.

🧩 Por qué se utilizó tema_calculadoras.css

Los estilos del index.html NO pueden afectar el interior de los iframes, porque cada iframe carga su propio documento HTML.

Para lograr coherencia visual, fue necesario inyectar un CSS global en cada calculadora, agregando esta línea al final del <head>:

```
<link rel="stylesheet" href="tema_calculadoras.css">
```

Colocarlo al final garantiza que:

El estilo global override los estilos internos.

Los colores personalizados de cada actividad sean reemplazados.

Se eliminen fuentes personalizadas.

Se estandarice la paleta oscura.

De esta forma, cada calculadora mantiene su lógica, pero adopta la misma identidad visual.

🖥 Integración de Calculadoras mediante iframes

Las calculadoras se muestran dentro de contenedores uniformes con:

```
<section class="calc-container">
  <div class="calc-title">Recta Numérica</div>
  <iframe 
      id="frameRecta"
      src="actividades/1-B_actividad_2_Angel_Lugo.html">
  </iframe>
</section>
```

Ventajas de usar iframes:

Aíslan el código de cada calculadora.

Evitan conflictos de JavaScript y CSS.

Permiten mantener módulos independientes.

Facilitan la integración de nuevos proyectos.

✨ Animación Suave y Carga Dinámica

Se implementó una animación de aparición:
```
document.addEventListener("DOMContentLoaded", () => {
  const containers = document.querySelectorAll(".calc-container");

  const observer = new IntersectionObserver(entries => {
    entries.forEach(e => e.isIntersecting && e.target.classList.add("visible"));
  }, { threshold: 0.15 });

  containers.forEach(c => observer.observe(c));
});
```

Con esto, cada calculadora entra suavemente al viewport, generando una experiencia visual más moderna.

🧠 Aprendizajes Clave

Modularización y encapsulamiento de código.

Integración segura con iframes.

Unificación global de estilos dentro de documentos externos.

Manejo de animaciones, scroll y diseño responsive.

Gestión adecuada de rutas y carpetas.

Limpieza de estilos internos conflictivos.

Diseño UX/UI consistente.

🔧 Buenas Prácticas en Git

Durante el desarrollo se aplicaron comandos clave:

Sincronizar historia:
```
git pull --rebase
```

Añadir cambios:
```
git add .
```

Resolver conflictos en rebase:
```
git rebase --continue
```

Publicar actualización:
```
git push origin main
```

Esto permitió mantener un historial limpio y evitar sobrescrituras.

🏁 Comentario Final

Este proyecto no consistió únicamente en juntar calculadoras, sino en:

Comprender cómo integrarlas de manera modular

Diseñar un sistema visual uniforme

Resolver incompatibilidades estéticas

Aplicar buenas prácticas de estructura

Aprender técnicas modernas de animación y responsividad

Practicar control de versiones con Git

El resultado final es un portafolio profesional, navegable, limpio, funcional y escalable, donde todas las calculadoras forman parte de un único ecosistema visual coherente.