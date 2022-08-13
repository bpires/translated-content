---
title: animation-timing-function
slug: Web/CSS/animation-timing-function
translation_of: Web/CSS/animation-timing-function
---
{{CSSRef}}{{SeeCompatTable}}

## Resumen

La propiedad [CSS](/es/docs/CSS "CSS") **`animation-timing-function`** especifica cómo una animación CSS debe avanzar sobre la duración de cada ciclo. Los posibles valores son una o varias {{cssxref("&lt;timing-function&gt;")}}.

Para animaciones con keyframes, la timing function se aplica entre los [keyframes](/es/docs/Web/CSS/@keyframes "/en-US/docs/CSS/@keyframes") en lugar de sobre toda la animación. Es decir, se aplica al comienzo del keyframe y al final del mismo.

Una timing function definida dentro de un keyframe afecta a ese keyframe. Si no está definida para el keyframe, se aplica la timing function para la animación en general.

A menudo, es conveniente usar la propiedad abreviada {{cssxref("animation")}} para ajustar las propiedades de animación una sola vez.

{{cssinfo}}

## Sintaxis

```css
/* Keyword values */
animation-timing-function: ease;
animation-timing-function: ease-in;
animation-timing-function: ease-out;
animation-timing-function: ease-in-out;
animation-timing-function: linear;
animation-timing-function: step-start;
animation-timing-function: step-end;

/* Function values */
animation-timing-function: cubic-bezier(0.1, 0.7, 1.0, 0.1);
animation-timing-function: steps(4, end);

/* Multiple animations */
animation-timing-function: ease, step-start, cubic-bezier(0.1, 0.7, 1.0, 0.1);

/* Global values */
animation-timing-function: inherited;
animation-timing-function: initial;
animation-timing-function: unset;
```

### Valores

- `<timingfunction>`
  - : Cada {{cssxref("&lt;timing-function&gt;")}} representa la timing function vinculada a la propiedad correspondiente a animar, como se define en {{cssxref ("animación-propiedad")}}.

### Sintaxis formal

{{csssyntax}}

## Ejemplos

Visita [animaciones CSS](https://developer.mozilla.org/es/CSS/Usando_animaciones_CSS "en/CSS/CSS_animations") para ver algunos ejemplos.

## Especificaciones

| Especificación                                                                                                           | Estado                               | Comentario        |
| ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------ | ----------------- |
| {{SpecName('CSS3 Animations', '#animation-timing-function', 'animation-timing-function')}} | {{Spec2('CSS3 Animations')}} | Definición incial |

## Compatibilidad entre navegadores

{{Compat("css.properties.animation-timing-function")}}

##

## Consulte también

- [Usando animaciones CSS](/es/docs/Web/CSS/CSS_Animations/Using_CSS_animations "CSS developer guide about CSS animations")
- {{domxref("AnimationEvent", "AnimationEvent")}}