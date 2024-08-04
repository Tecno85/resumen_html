# Resumen HTML Jhoin Mircha

## Retos o Dificultades al Aprender

1. ¿Que significa el mensaja de error: link 'rel' attribute should include 'nooopener?.

RTA:

El mensaje de error "link 'rel' attribute should include 'noopener'" en Visual Studio Code se refiere a una recomendación de seguridad y rendimiento cuando se utilizan enlaces HTML `('<a>' tags)` que abren una nueva pestaña o ventana del navegador mediante el atributo target="\_blank".

Explicación:

Cuando usas `target="_blank"` en un enlace, estás indicando al navegador que abra el enlace en una nueva pestaña o ventana. Sin embargo, esto introduce un riesgo de seguridad conocido como `"tab nabbing"`. El sitio abierto en la nueva pestaña puede potencialmente ejecutar un script para obtener acceso a la ventana original a través del objeto window.opener, lo que podría permitir que la nueva página cambie la URL de la página original a una página de phishing, por ejemplo.

Para mitigar este riesgo, se recomienda agregar `rel="noopener"` (o `rel="noopener noreferrer"`) al enlace. Esto le dice al navegador que no proporcione a la nueva pestaña acceso a la ventana original a través de window.opener.

Ejemplo:

Antes:

`<a href="https://example.com" target="_blank">Visitar Example</a>`

Después:

`<a href="https://example.com" target="_blank" rel="noopener">Visitar Example</a>`

O, más seguro aún:

`<a href="https://example.com" target="_blank" rel="noopener noreferrer">Visitar Example</a>`
