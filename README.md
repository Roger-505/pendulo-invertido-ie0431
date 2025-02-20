# pendulo-invertido-ie0431

Este es un repositorio dedicado el examen #2 del curso Sistemas de Control IE0431 IIS2024, Universidad de Costa Rica, Escuela de Ingeniería Eléctrica. 

## Sistema de Control para Péndulo Invertido Rotatorio

Este proyecto consiste en el diseño y simulación de un sistema de control para un péndulo invertido rotatorio. El sistema incluye actuadores y sensores para medir el cambio de los ángulos de rotación del brazo rotatorio y el péndulo. El objetivo principal es mantener el péndulo en una posición vertical estable mediante control PID.

## Objetivos

1. **Cero error en estado estacionario** frente a cambios en la perturbación y el valor deseado.
2. **Reducción del tiempo de asentamiento** a lazo cerrado en comparación con el lazo abierto.
3. **Simulación y análisis** de la respuesta dinámica utilizando Simulink y Simscape de MATLAB.

## Descripción del Sistema

El sistema se compone de:

- Un péndulo invertido de brazo rotatorio.
- Sensores que miden los ángulos de rotación del péndulo y el brazo rotatorio.
- Un actuador que ajusta el torque aplicado al sistema.

El modelo fue diseñado en Simulink utilizando el modelo de Simscape "Inverted Pendulum Simscape Model". Las señales de entrada y salida fueron configuradas y normalizadas para garantizar la estabilidad del sistema.

## Diseño del Actuador y Control

Se implementó un controlador PID para la regulación de la variable manipulada $` V_f `$. El sistema fue diseñado con dos lazos de retroalimentación, cada uno de los cuales controla un ángulo diferente:

- $` C_\alpha(s) `$: Controlador para el ángulo del péndulo.
- $` C_\theta(s) `$: Controlador para el ángulo del brazo rotatorio.

Se sintonizaron los controladores utilizando métodos de optimización y sintonización empírica para obtener un desempeño óptimo en términos de respuesta dinámica y robustez.

## Simulación y Validación

La simulación fue realizada en MATLAB utilizando un modelo de Simscape. Durante la simulación, el sistema mostró un buen desempeño bajo diversas condiciones, incluyendo perturbaciones y cambios en el valor deseado. Los resultados mostraron una respuesta rápida y estable del sistema de control.

### Resultados de la Simulación:

- **0-3 s**: El sistema comienza con el péndulo inclinado a 30° respecto al eje z.
- **3-7.5 s**: Se aplica un cambio escalón en la perturbación, y el sistema responde adecuadamente, estabilizándose rápidamente.

### Vídeo de simulación

En [este vídeo](https://youtu.be/KwJOqnFWYP8), se muestra una simulación del sistema de control diseñado.

## Requisitos

- MATLAB/Simulink
- Simscape
- Herramientas de optimización como `fmincon` y `fminsearch`

## Autor

Roger Daniel Piovet García  
Curso: IE0431 – Sistemas de Control  
Universidad de Costa Rica
