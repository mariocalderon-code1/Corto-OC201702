# Enunciado del Examen Corto - CortoOC201702

## Objetivo
Los estudiantes deben construir una aplicación que presente una pregunta musical, permita al usuario elegir una respuesta y, dependiendo de si es correcta o no, reproduzca un sonido específico y pase a una pantalla de resultados mostrando el puntaje obtenido.

## Requerimientos Técnicos
1. **Actividades:** Mínimo 3 (Inicio, Preguntas, Resultados).
2. **Intents:** Uso de Intent para cambiar de pantalla y `putExtra()` para enviar el nombre del usuario y su puntaje.
3. **Multimedia:** Uso de la clase `MediaPlayer` para reproducir archivos `.mp3`.
4. **Componentes:** Uso de `Button`, `TextView` y `EditText`.

## Estructura del Ejercicio

### A. Preparación de Recursos
- Crear la carpeta `raw` en `res/raw`.
- Añadir dos archivos de audio cortos (buscar en internet): `correcto.mp3` y `error.mp3`.

### B. Activity Principal (MainActivity)
- **Interfaz:** Un campo de texto (`EditText`) para el nombre y un botón de "Comenzar".
- **Lógica:** Al presionar el botón, se debe capturar el nombre y pasarlo a la siguiente Activity.

### C. Activity de Pregunta
- **Interfaz:** Una pregunta sobre música y tres botones con opciones.
- **Lógica:**
    - Recibir el nombre mediante `getIntent().getStringExtra("username")`.
    - Si el alumno elige la respuesta correcta: reproducir `correcto.mp3` y sumar puntos.
    - Si falla: reproducir `error.mp3`.
    - Al finalizar, enviar el nombre y el puntaje acumulado a la última pantalla.

### D. Activity de Resultado
- **Interfaz:** Un `TextView` que muestre un mensaje personalizado.
- **Lógica:** Mostrar: "Felicidades [nombre], tu puntaje final es: [puntaje]".
