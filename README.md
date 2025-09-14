<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Un Jardín para Ti</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&display=swap');

        body {
            margin: 0;
            overflow: hidden;
            background: linear-gradient(to top, #a8e063, #56ab2f); /* Fondo de prado verde */
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .sky {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 60%;
            background: linear-gradient(to bottom, #a1c4fd, #c2e9fb); /* Cielo azul claro */
            z-index: -1;
        }

        .welcome-message {
            position: absolute;
            top: 40%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-family: 'Dancing Script', cursive;
            font-size: 3.5em;
            color: white;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.4);
            text-align: center;
            opacity: 0;
            animation: fadeInOut 6s ease-in-out forwards;
            z-index: 100;
        }

        @keyframes fadeInOut {
            0%, 100% { opacity: 0; }
            10%, 80% { opacity: 1; }
        }

        .flower-container {
            position: absolute;
            bottom: 0;
            width: 100%;
            height: 100%;
            animation: appear 1s 5s forwards;
            opacity: 0;
        }
        
        @keyframes appear {
            to { opacity: 1; }
        }

        .flower {
            position: absolute;
            bottom: -50px; /* Inician ocultas abajo */
        }

        /* Tallo */
        .stem {
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 5px;
            background-color: #388e3c;
            border-radius: 5px 5px 0 0;
            animation: grow-stem 2s cubic-bezier(0.25, 0.46, 0.45, 0.94) forwards;
        }

        /* Hojas */
        .leaf {
            position: absolute;
            bottom: 20px;
            width: 40px;
            height: 20px;
            background-color: #4caf50;
            border-radius: 100% 0;
            opacity: 0;
            animation: grow-leaf 1.5s 1s forwards;
        }

        .leaf.right {
            left: 2px;
            transform: rotate(-30deg);
        }

        .leaf.left {
            right: 2px;
            transform: rotate(210deg);
        }

        /* Pétalos */
        .petals {
            position: absolute;
            bottom: 100%; /* Se posicionan al final del tallo */
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 80px;
            transform-origin: center center;
            animation: open-flower 2s 1.8s cubic-bezier(0.34, 1.56, 0.64, 1) forwards;
            transform: scale(0);
        }

        .petal {
            position: absolute;
            width: 40px;
            height: 50px;
            border-radius: 50% 50% 0 0;
            transform-origin: bottom center;
            left: 20px;
            bottom: 30px;
        }
        
        .petal:nth-child(1) { transform: rotate(0deg); }
        .petal:nth-child(2) { transform: rotate(45deg); }
        .petal:nth-child(3) { transform: rotate(90deg); }
        .petal:nth-child(4) { transform: rotate(135deg); }
        .petal:nth-child(5) { transform: rotate(180deg); }
        .petal:nth-child(6) { transform: rotate(225deg); }
        .petal:nth-child(7) { transform: rotate(270deg); }
        .petal:nth-child(8) { transform: rotate(315deg); }

        /* Centro de la flor */
        .flower-center {
            position: absolute;
            width: 30px;
            height: 30px;
            background: radial-gradient(#ffd54f, #ffb300);
            border-radius: 50%;
            bottom: 0;
            left: 25px;
        }

        /* --- Animaciones --- */
        @keyframes grow-stem {
            from { height: 0; }
        }

        @keyframes grow-leaf {
            from { transform: scale(0); opacity: 0; }
            to { transform: scale(1); opacity: 1; }
        }

        @keyframes open-flower {
            from { transform: scale(0); }
            to { transform: scale(1); }
        }

        /* --- Estilos y Posiciones de las Flores --- */

        /* Flor 1 (Rosa) */
        .flower-1 { left: 15%; animation-delay: 6s; }
        .flower-1 .stem { height: 150px; animation-delay: 6s; }
        .flower-1 .petal { background: linear-gradient(to top, #f8bbd0, #f06292); }

        /* Flor 2 (Violeta) */
        .flower-2 { left: 75%; animation-delay: 6.5s; }
        .flower-2 .stem { height: 200px; animation-delay: 6.5s; }
        .flower-2 .petal { background: linear-gradient(to top, #d1c4e9, #9575cd); }
        
        /* Flor 3 (Azul) */
        .flower-3 { left: 50%; animation-delay: 7s; }
        .flower-3 .stem { height: 120px; animation-delay: 7s; }
        .flower-3 .petal { background: linear-gradient(to top, #b3e5fc, #4fc3f7); }

        /* Flor 4 (Amarilla) */
        .flower-4 { left: 30%; animation-delay: 7.5s; }
        .flower-4 .stem { height: 180px; animation-delay: 7.5s; }
        .flower-4 .petal { background: linear-gradient(to top, #fff59d, #ffee58); }

        /* Flor 5 (Naranja) */
        .flower-5 { left: 60%; animation-delay: 8s; }
        .flower-5 .stem { height: 160px; animation-delay: 8s; }
        .flower-5 .petal { background: linear-gradient(to top, #ffcc80, #ff9800); }
        
        /* Flor 6 (Roja) */
        .flower-6 { left: 85%; animation-delay: 8.5s; }
        .flower-6 .stem { height: 140px; animation-delay: 8.5s; }
        .flower-6 .petal { background: linear-gradient(to top, #ef9a9a, #e57373); }
        
        /* Flor 7 (Blanca) */
        .flower-7 { left: 5%; animation-delay: 9s; }
        .flower-7 .stem { height: 190px; animation-delay: 9s; }
        .flower-7 .petal { background: linear-gradient(to top, #f5f5f5, #e0e0e0); }

    </style>
</head>
<body>
    <div class="sky"></div>

    <div class="welcome-message">
        Bienvenida princesa Lady Kristal Collado<br>de parte del señor Juan Fermin
    </div>

    <div class="flower-container">
        <!-- Puedes añadir o quitar flores fácilmente copiando y pegando estos bloques -->
        <div class="flower flower-1">
            <div class="stem">
                <div class="leaf left"></div>
                <div class="leaf right"></div>
            </div>
            <div class="petals">
                <div class="petal"></div><div class="petal"></div><div class="petal"></div>
                <div class="petal"></div><div class="petal"></div><div class="petal"></div>
                <div class="petal"></div><div class="petal"></div>
                <div class="flower-center"></div>
            </div>
        </div>
        
        <div class="flower flower-2">
            <div class="stem">
                <div class="leaf left"></div>
                <div class="leaf right"></div>
            </div>
            <div class="petals">
                <div class="petal"></div><div class="petal"></div><div class="petal"></div>
                <div class="petal"></div><div class="petal"></div><div class="petal"></div>
                <div class="petal"></div><div class="petal"></div>
                <div class="flower-center"></div>
            </div>
        </div>

        <div class="flower flower-3">
            <div class="stem">
                <div class="leaf left"></div>
            </div>
            <div class="petals">
                <div class="petal"></div><div class="petal"></div><div class="petal"></div>
                <div class="petal"></div><div class="petal"></div><div class="petal"></div>
                <div class="petal"></div><div class="petal"></div>
                <div class="flower-center"></div>
            </div>
        </div>

        <div class="flower flower-4">
            <div class="stem">
                <div class="leaf right"></div>
            </div>
            <div class="petals">
                <div class="petal"></div><div class="petal"></div><div class="petal"></div>
                <div class="petal"></div><div class="petal"></div><div class="petal"></div>
                <div class="petal"></div><div class="petal"></div>
                <div class="flower-center"></div>
            </div>
        </div>

        <div class="flower flower-5">
            <div class="stem">
                <div class="leaf left"></div>
                <div class="leaf right"></div>
            </div>
            <div class="petals">
                <div class="petal"></div><div class="petal"></div><div class="petal"></div>
                <div class="petal"></div><div class="petal"></div><div class="petal"></div>
                <div class="petal"></div><div class="petal"></div>
                <div class="flower-center"></div>
            </div>
        </div>
        
        <div class="flower flower-6">
            <div class="stem">
                <div class="leaf left"></div>
            </div>
            <div class="petals">
                <div class="petal"></div><div class="petal"></div><div class="petal"></div>
                <div class="petal"></div><div class="petal"></div><div class="petal"></div>
                <div class="petal"></div><div class="petal"></div>
                <div class="flower-center"></div>
            </div>
        </div>

        <div class="flower flower-7">
            <div class="stem">
                <div class="leaf right"></div>
            </div>
            <div class="petals">
                <div class="petal"></div><div class="petal"></div><div class="petal"></div>
                <div class="petal"></div><div class="petal"></div><div class="petal"></div>
                <div class="petal"></div><div class="petal"></div>
                <div class="flower-center"></div>
            </div>
        </div>
    </div>

</body>
</html>
