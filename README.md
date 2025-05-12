# Laalk
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Un Corazón para Ti ❤️</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        /* Estilos para centrar el contenido y el corazón */
        html, body {
            height: 100%;
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: #fce4ec; /* Un fondo rosa claro */
            overflow: hidden; /* Evita barras de scroll */
            -webkit-tap-highlight-color: transparent; /* Evita el resaltado azul en móviles al tocar */
        }

        /* Estilos del corazón */
        .heart {
            width: 100px; /* Tamaño inicial del corazón */
            height: auto;
            cursor: pointer;
            transition: transform 0.3s ease-in-out; /* Transición suave para la animación */
            fill: #e91e63; /* Color rosa intenso para el corazón */
        }

        /* Animación de latido */
        .heart.beat {
            animation: heartbeat 0.6s ease-in-out;
        }

        @keyframes heartbeat {
            0% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.3); /* Crece un poco */
            }
            100% {
                transform: scale(1);
            }
        }

        /* Estilo opcional para un mensaje */
        .message {
            position: absolute;
            bottom: 20px;
            font-family: sans-serif;
            color: #6d4c41; /* Marrón oscuro */
            font-size: 0.9rem;
            text-align: center;
            width: 100%;
            padding: 0 10px;
            box-sizing: border-box;
        }
    </style>
</head>
<body>

    <div class="flex flex-col items-center justify-center text-center">
        <svg id="loveHeart" class="heart" viewBox="0 0 24 24" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
            <path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"/>
        </svg>

        <p class="message">Toca el corazón ❤️</p>
    </div>

    <script>
        const heart = document.getElementById('loveHeart');

        // Función para activar la animación
        function pulseHeart() {
            // Añade la clase 'beat' para iniciar la animación
            heart.classList.add('beat');

            // Elimina la clase después de que termine la animación
            // para que pueda volver a activarse en el siguiente clic/toque.
            // La duración de la animación es de 0.6s (600ms).
            setTimeout(() => {
                heart.classList.remove('beat');
            }, 600);
        }

        // Añade el event listener para 'click' (funciona para ratón y toque)
        heart.addEventListener('click', pulseHeart);

        // Opcional: También puedes usar 'touchstart' para una respuesta táctil potencialmente más rápida
        // heart.addEventListener('touchstart', function(event) {
        //     event.preventDefault(); // Previene eventos de mouse duplicados si también usas 'click'
        //     pulseHeart();
        // });

    </script>
</body>
</html>
