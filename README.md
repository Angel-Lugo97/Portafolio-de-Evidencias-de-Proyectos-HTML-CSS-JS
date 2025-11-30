# 📘 Portafolio de Evidencias – Calculadoras Unificadas
# Tecnológico de Software

## Materia: Fundamentos de álgebra

## Alumno: Angel Abraham Lugo Saenz

## Grupo: B

## Actividad #19. Portafolio de Evidencias de Proyectos HTML/CSS/JS
## 📚 Índice

1. [Logros del proyecto](#-qué-se-logró)
2. [Aprendizajes clave](#-aprendizajes-clave)
3. [Funciones puente para comunicación con iframes](#2-estructuración-y-modularización)
4. [Animación suave en scroll](#3-animación-suave-en-scroll)
5. [Estilizado global no intrusivo](#4-estilizado-global-no-intrusivo)
6. [Resolución de conflictos en Git](#5-resolución-de-conflictos-en-git)
7. [Integración de calculadoras dentro del index](#-cómo-se-integran-las-calculadoras)
8. [Estructura de carpetas del proyecto](#-estructura-del-proyecto)
9. [Mejoras futuras posibles](#-siguiente-mejora-posible)

## Objetivo

Este repositorio contiene la integración y visualización unificada de **7 calculadoras algebraicas** desarrolladas como parte de las actividades académicas de *Fundamentos de Álgebra* impartidas por la docente a cargo.

El objetivo principal de esta tarea fue **acoplar múltiples proyectos `HTML + CSS + JavaScript` en una sola página principal**, sin afectar la lógica interna ni hacer que las calculadoras perdieran funcionalidades originales.

---

## 📂 Estructura del proyecto
```
/
├─ index.html → Página principal
├─ calculadoras_unificadas.js
├─ calculadoras_unificadas.css
└─ actividades/→ Contiene las 7 calculadoras HTML independientes
---
## 🚀 ¿Qué se logró?

- ✅ Unificación visual de 7 calculadoras algebraicas mediante `iframes`.
- ✅ Navegación vertical con *scroll suave*, evitando interfaces desordenadas.
- ✅ Estética global aplicada en **escala de grises** con **bordes blancos** para pruebas de contraste.
- ✅ Animación *fade-in suave al scrollear*, implementada con `IntersectionObserver`.
- ✅ Carga y verificación de los `iframes` usando eventos `load` para debugging seguro.
- ✅ Separación ordenada de archivos padre (`index`, `JS y CSS global`) en carpeta raíz, y calculadoras incrustadas en `/actividades`.

```
---

## 🧠 Aprendizajes clave

Durante este proceso se adquirieron conocimientos en:

### 1. **Estructuración y modularización**
Se trabajó en mantener la **lógica original encapsulada dentro de cada HTML**, sin copiarla directamente al `index`, evitando colisiones entre funciones globales.

### 2. **Comunicación con iframes de forma segura**
Aunque `iframes` aíslan la lógica interna, se aprendió a crear objetos puente en el JS padre para acceder a funciones internas futuras sin romper el sistema:
Esto permite que más adelante el padre pueda enviar datos a los scripts internos de cada calculadora si se desea extender.

3. Animación suave en scroll

Usamos el listener principal DOMContentLoaded en el JS padre para activar la animación de aparición por secciones:

document.addEventListener("DOMContentLoaded", () => {
  const containers = document.querySelectorAll(".calc-container");
  const observer = new IntersectionObserver(entries => {
    entries.forEach(e => e.isIntersecting && e.target.classList.add("visible"));
  }, { threshold: 0.15 });

  containers.forEach(c => observer.observe(c));
});

4. Estilizado global no intrusivo

Se aplicó un CSS padre que controla solo la página contenedora, respetando los estilos propios de cada calculadora:

body {
  background: #000;
  filter: grayscale(100%);
  color: #fff;
}

.calc-container {
  border: 2px solid white;
  background: #111;
  border-radius: 12px;
  transition: opacity 0.8s ease;
}

5. Resolución de conflictos en Git

También se practicaron comandos esenciales de control de versión, como:

git pull --rebase para traer cambios sin ensuciar historial.

git add <archivo> + git rebase --continue para marcar resolución de conflictos.

git push origin main tras sincronizar local con remoto.
🧩 ¿Cómo se integran las calculadoras?

Cada calculadora se mantiene en la carpeta /actividades, y el index las incrusta así:

<section class="calc-container">
  <div class="calc-title">Recta Numérica</div>
  <iframe id="frameRecta" src="actividades/1-B_actividad_2_Angel_Lugo.html"></iframe>
</section>


Los contenedores se apilan uno debajo de otro para navegación vertical intuitiva:

Se evita recargar o reprogramar lógica matemática.

Se centraliza solo la animación y el diseño general.
✨ Comentario final

La unificación de proyectos no solo consistió en juntar archivos, sino en respetar modularidad y aislamiento, aplicar estética homogénea para pruebas, y garantizar una experiencia fluida de navegación dentro del portafolio.

Este repositorio documenta un proceso real de aprendizaje donde se aplicaron:

-Módulos encapsulados
-Debugging seguro
-Scroll easing
-Buenas prácticas en Git
-Integración visual escalable