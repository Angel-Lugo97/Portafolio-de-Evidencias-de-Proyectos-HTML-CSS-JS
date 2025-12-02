# 📘 Portafolio de Evidencias – Calculadoras Unificadas
### Tecnológico de Software
### Materia: Fundamentos de Álgebra
### Alumno: Ángel Abraham Lugo Sáenz
### Grupo: B
###  Actividad #19 — Portafolio de Evidencias de Proyectos HTML/CSS/JS
## 📚 Índice
```
1- Objetivo del Proyecto
2- Estructura del Proyecto
3- Logros del Proyecto
4- Unificación Visual y Estilo Global
5- Explicación de IntersectionObserver
6- Limpieza y Unificación de Calculadoras
7- Documentación del CSS Global
8- Integración de Calculadoras mediante iframes
9- Animación Suave y Carga Dinámica
10- Aprendizajes Clave
11- Buenas Prácticas en Git
12- Comentario Final

```

## 🎯 Objetivo del Proyecto

Este repositorio contiene la integración y visualización unificada de 7 calculadoras algebraicas, cada una desarrollada como parte de diferentes actividades de la materia Fundamentos de Álgebra.
El objetivo principal fue reunir todas las calculadoras en una sola página (index.html), manteniendo sus funcionalidades originales y logrando una presentación profesional, uniforme y navegable, utilizando únicamente:

```
HTML
CSS
JavaScript
```

## 📂 Estructura del Proyecto
```
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

## 🚀 Logros del Proyecto

```
1- Integración visual de 7 calculadoras algebraicas mediante iframes.
2- Todas las calculadoras muestran misma tipografía, colores y estilo base.
3- Se eliminaron animaciones RGB y fondos inconsistentes.
4- Navegación vertical suave con scroll-behavior.
5- Aparición animada de secciones con IntersectionObserver.
6- Diseño oscuro homogéneo basado en escala de grises.\
7- Separación clara entre:
8- Estilo global (fuera del iframe)
9- Estilo unificador dentro del iframe
10- Modularidad completa sin alterar la lógica original de ninguna calculadora.
```

## 🎨 Unificación Visual y Estilo Global

Cada calculadora tenía originalmente colores distintos, tipografías diferentes, gradientes, animaciones RGB e interfaces variadas.
Para que todo luciera como un solo sistema coherente, se creó un tema visual uniforme basado en:
```
Tipografía global → Arial
Fondo oscuro → #111
Inputs estandarizados
Botones uniformes
Eliminación de animaciones distractoras
```
Este tema se aplicó dentro de cada iframe para asegurar consistencia visual completa.

## 🔥 Explicación del IntersectionObserver (Animación de Aparición)

La animación suave al hacer scroll se implementó con IntersectionObserver, una API moderna que detecta cuándo un elemento entra al viewport del usuario.

### Código utilizado:
```
document.addEventListener("DOMContentLoaded", () => {
  const containers = document.querySelectorAll(".calc-container");

  const observer = new IntersectionObserver(entries => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add("visible");
      }
    });
  }, { threshold: 0.15 });

  containers.forEach(c => observer.observe(c));
});
```

Esta técnica permite una navegación más fluida sin recargar el navegador.

## 🌙 Proceso de Limpieza y Unificación de las Calculadoras

Cada calculadora tenía su propio estilo, por lo que se realizó una limpieza de CSS en cada archivo:

### Se eliminaron:
```
Colores personalizados
Tipografías distintas
Fondos RGB
Degradados
Sombra de colores
Animaciones CSS
Estilos globales conflictivos
```
### Se conservaron:
```
Layouts (grid, flex)
Tamaños
Márgenes
Estructura interna
```
### Se agregó:
```
Un vínculo al tema global al final del <head>:

<link rel="stylesheet" href="tema_calculadoras.css">
```


Esto unificó toda la estética sin afectar la lógica matemática.

## 🖤 Documentación del CSS Global tema_calculadoras.css
```
Este archivo se encarga de:
Aplicar tema oscuro uniforme
Forzar misma tipografía
Normalizar inputs y botones
Eliminar animaciones
Mantener un diseño profesional y coherente
```
###  Ejemplo de estilos clave:
```
body {
  background: #111 !important;
  color: #f0f0f0 !important;
  font-family: Arial, sans-serif !important;
}

input, select, textarea {
  background-color: #222 !important;
  color: #fff !important;
}

button {
  background: #fff !important;
  color: #000 !important;
}

* {
  animation: none !important;
  transition: none !important;
}
```

## 🖥 Integración de Calculadoras mediante iframes

### Cada calculadora se integra así:
```
<section class="calc-container">
  <div class="calc-title">Recta Numérica</div>
  <iframe 
      id="frameRecta"
      src="actividades/1-B_actividad_2_Angel_Lugo.html">
  </iframe>
</section>
```

Los iframes aseguran que la lógica interna de cada calculadora se mantenga aislada y sin conflictos.

## ✨ Animación Suave y Carga Dinámica

Se usó IntersectionObserver para activar la animación de entrada y mejorar la experiencia visual.
Además, el JS principal registra cada iframe cuando termina de cargar para debugging si es necesario.

## 🧠 Aprendizajes Clave
```
Integración modular con iframes
Limpieza y unificación avanzada de CSS
Implementación de tema global
Manejo de animaciones eficientes
Rutas relativas y estructura de carpetas
Arquitectura visual profesional
Debugging y estructura organizada de código
```

## 🔧 Buenas Prácticas en Git

### Los comandos usados durante el proyecto incluyen:
```
git pull --rebase
git add .
git rebase --continue
git push origin main
```

Esto ayudó a mantener un historial ordenado y resolver conflictos.

## 🏁 Comentario Final

Este proyecto no solo integra calculadoras:
es una muestra de modularidad, diseño unificado, buenas prácticas web y documentación profesional.

### Se aplicó:
```
limpieza técnica
arquitectura modular
estilo global uniforme
animaciones modernas
control de versiones
organización de contenido
```
El resultado es un portafolio funcional, elegante y escalable, ideal para mostrar como evidencia de aprendizaje y habilidades técnicas.