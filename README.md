paso 1,2,3,4 del chat francisco 6.
se arregló la duracion de los poderes.


lo que si se implementó
He analizado el código proporcionado y he identificado los siguientes puntos relacionados con la integridad y el correcto funcionamiento del mismo:

Probabilidad de Generación de Poderes:

Problema: En BlockBreakerGame.java, la condición para generar un poder es if (Math.random() < 0.9), lo que implica una probabilidad del 90%. Sin embargo, mencionaste una probabilidad de 1/8 (12.5%).
Recomendación: Cambiar la condición a if (Math.random() < 0.125) para reflejar la probabilidad deseada.
Colisión de Poderes con el Paddle:

Problema: En Poder.java, el método verificarColisionConPaddle verifica la colisión considerando solo el punto (x, y) del poder, lo que puede no ser preciso si el poder tiene dimensiones.
Recomendación: Implementar una detección de colisión basada en rectángulos que considere el ancho y alto de la textura del poder.
Duración de los Poderes Activos:

Problema: En BlockBreakerGame.java, al activar un poder, se establece la duración según el tipo de poder. Sin embargo, no se verifica si múltiples instancias del mismo poder pueden superponerse y afectar la duración.
Recomendación: Asegurar que la activación de un poder ya activo reinicie su duración en lugar de permitir múltiples instancias que puedan interferir entre sí.
Normalización de la Velocidad de la Bola:

Problema: En PingBall.java, el método normalizeSpeed asegura que la velocidad total de la bola sea constante. Sin embargo, al reducir la velocidad con PoderReducirVelocidadBola, esto puede entrar en conflicto.
Recomendación: Ajustar la lógica de normalización para considerar multiplicadores de velocidad o modificar la forma en que se aplica la reducción para evitar conflictos.
