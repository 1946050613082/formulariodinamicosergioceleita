Desarrollo del Proyecto

1. Configuración Inicial del Proyecto
Elección de Tecnologías
Decidí utilizar Vue.js junto con Vite para desarrollar este proyecto. Vue.js es un framework progresivo de JavaScript que me permite crear interfaces de usuario de manera eficiente, mientras que Vite es una herramienta de construcción rápida que optimiza el desarrollo moderno.

Creación del Proyecto
Para iniciar, abrí mi terminal y ejecuté el siguiente comando para crear un nuevo proyecto con Vue y Vite:

bash
Copy
npm create vite@latest
Elegí el nombre del proyecto (formulario-registro).

Seleccioné Vue como framework.

Elegí JavaScript como variante.

Esto generó una estructura básica del proyecto con todos los archivos necesarios.

Instalación de Dependencias
Luego, navegué a la carpeta del proyecto e instalé las dependencias necesarias ejecutando:

bash
Copy
cd formulario-registro
npm install
Esto instaló Vue, Vite y otras dependencias necesarias para el desarrollo.



2. Estructura del Proyecto
Organización de Archivos
Dentro de la carpeta del proyecto, organicé los archivos de la siguiente manera:

src/: Contiene el código fuente de la aplicación.

components/: Para los componentes reutilizables.

assets/: Para recursos estáticos como imágenes.

App.vue: El componente principal de la aplicación.

main.js: El punto de entrada de la aplicación.

public/: Para archivos públicos (no lo usé en este proyecto).

index.html: La plantilla HTML principal.



3. Desarrollo del Componente Principal (App.vue)
Diseño del Encabezado
En el archivo App.vue, comencé por diseñar el encabezado de la aplicación:

Importé una imagen (dfg.png) desde la carpeta assets para usarla como logo.

Creé un título (Formulario de Registro) y un subtítulo (Completa los campos y envía tu información).

Apliqué estilos CSS para darle un diseño atractivo, con un fondo degradado, sombras y bordes redondeados.

Integración del Formulario
Importé el componente FormComponent desde la carpeta components.

Lo incluí dentro de una sección <main> para que fuera el foco principal de la página.

Añadí un mensaje de confirmación (¡Gracias por registrarte!) que se muestra después de enviar el formulario.

Lógica del Componente
Usé la Composition API de Vue para manejar el estado del formulario.

Creé una variable reactiva (isFormSubmitted) para controlar cuándo mostrar el mensaje de confirmación.

Implementé una función (handleFormSubmit) que se ejecuta cuando el formulario se envía, mostrando el mensaje de confirmación durante 3 segundos.





4. Desarrollo del Componente del Formulario (FormComponent.vue)
Diseño del Formulario
En el archivo FormComponent.vue, diseñé un formulario con tres campos:

Nombre: Un campo de texto obligatorio.

Correo Electrónico: Un campo de email que valida el formato.

Contraseña: Un campo de contraseña que requiere al menos 6 caracteres.

Validaciones en Tiempo Real
Usé propiedades computadas (emailValido y formularioValido) para validar los campos mientras el usuario escribe.

Si el correo no tiene un formato válido o la contraseña es demasiado corta, se muestran mensajes de error debajo de cada campo.

Manejo del Envío
Implementé una función (submitForm) que se ejecuta cuando el formulario se envía.

Si todos los campos son válidos, se muestra un mensaje de éxito (¡Formulario enviado con éxito!) dentro del formulario.

Estilos del Formulario
Apliqué estilos CSS para darle un diseño moderno al formulario, con un fondo degradado, sombras y bordes redondeados.

Los campos de entrada cambian de color al enfocarse o si hay errores.

El botón de envío se deshabilita si el formulario no es válido.






5. Pruebas y Ajustes
Pruebas en el Navegador
Ejecuté el proyecto en modo de desarrollo con el comando:

bash
Copy
npm run dev
Abrí la aplicación en el navegador (http://localhost:5173) y probé todas las funcionalidades:

Completé el formulario con datos válidos e inválidos para verificar las validaciones.

Verifiqué que el mensaje de confirmación se mostrara correctamente después de enviar el formulario.

Ajustes Finales
Corregí algunos errores de estilo y mejoré la responsividad del diseño para que se vea bien en dispositivos móviles y tablets.

Aseguré que todas las animaciones y transiciones funcionaran correctamente.



7. Conclusión
Este proyecto fue una excelente oportunidad para aplicar mis conocimientos de Vue.js y Vite. Aprendí a:

Crear componentes reutilizables.

Implementar validaciones en tiempo real.

Manejar el estado de la aplicación con la Composition API.

Diseñar interfaces de usuario modernas y responsivas.

El resultado final es un formulario de registro funcional, atractivo y fácil de usar, que cumple con todos los requisitos establecidos.



visualizacion grafica del funcionamiento de la interfaz 

![imagen 1](https://github.com/user-attachments/assets/a8ac9951-8ba8-4415-bc5a-943d303c77bb)
![imagen 2](https://github.com/user-attachments/assets/1c45ef88-c1a3-447b-92f1-99e07d5ec165)
![imagen 3](https://github.com/user-attachments/assets/98197bd3-7bf9-475b-bbcb-44783205bfae)







