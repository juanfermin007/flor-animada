<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Un Mensaje Especial para Ti</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #fce4ec; /* Un fondo rosa claro */
            margin: 0;
            overflow: hidden;
            font-family: ' cursive', sans-serif;
        }

        .welcome-message {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 2.5em;
            color: #c2185b; /* Un color de texto más oscuro */
            text-align: center;
            animation: fade-in-out 5s forwards;
            z-index: 10;
        }

        .flower {
            position: relative;
            width: 300px;
            height: 300px;
            opacity: 0;
            animation: fade-in-flower 1s 4.5s forwards;
        }

        .petal {
            position: absolute;
            width: 100px;
            height: 150px;
            background-color: #f8bbd0; /* Color del pétalo */
            border-radius: 50% 50% 0 0;
            transform-origin: bottom center;
            animation: draw-petal 3s ease-out forwards;
            opacity: 0;
        }

        .petal1 {
            top: 0;
            left: 100px;
            transform: rotate(0deg);
            animation-delay: 5s;
        }

        .petal2 {
            top: 45px;
            left: 145px;
            transform: rotate(60deg);
            animation-delay: 5.5s;
        }

        .petal3 {
            top: 105px;
            left: 145px;
            transform: rotate(120deg);
            animation-delay: 6s;
        }

        .petal4 {
            top: 150px;
            left: 100px;
            transform: rotate(180deg);
            animation-delay: 6.5s;
        }

        .petal5 {
            top: 105px;
            left: 55px;
            transform: rotate(240deg);
            animation-delay: 7s;
        }

        .petal6 {
            top: 45px;
            left: 55px;
            transform: rotate(300deg);
            animation-delay: 7.5s;
        }

        .center {
            position: absolute;
            width: 80px;
            height: 80px;
            background-color: #ffeb3b; /* Color del centro de la flor */
            border-radius: 50%;
            top: 110px;
            left: 110px;
            transform: scale(0);
            animation: grow-center 1s ease-out 8s forwards;
        }

        .stem {
            position: absolute;
            width: 10px;
            height: 0;
            background-color: #4caf50; /* Color del tallo */
            top: 300px;
            left: 145px;
            animation: draw-stem 1s ease-out 8.5s forwards;
        }

        .leaf {
            position: absolute;
            width: 0;
            height: 0;
            background-color: #66bb6a; /* Color de la hoja */
            top: 380px;
            left: 155px;
            border-radius: 0 50%;
            animation: draw-leaf 1s ease-out 9s forwards;
        }

        .leaf2 {
            left: 85px;
            transform: rotate(120deg);
            animation-delay: 9.5s;
        }

        @keyframes fade-in-out {
            0% {
                opacity: 0;
            }
            20% {
                opacity: 1;
            }
            80% {
                opacity: 1;
            }
            100% {
                opacity: 0;
            }
        }

        @keyframes fade-in-flower {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }

        @keyframes draw-petal {
            0% {
                height: 0;
                opacity: 0;
            }
            100% {
                height: 150px;
                opacity: 1;
            }
        }

        @keyframes grow-center {
            0% {
                transform: scale(0);
            }
            100% {
                transform: scale(1);
            }
        }

        @keyframes draw-stem {
            0% {
                height: 0;
            }
            100% {
                height: 200px;
            }
        }

        @keyframes draw-leaf {
            0% {
                width: 0;
                height: 0;
            }
            100% {
                width: 60px;
                height: 30px;
            }
        }
    </style>
</head>
<body>

    <div class="welcome-message">
        Bienvenida princesa Lady Kristal Collado<br>de parte del señor Juan Fermin
    </div>

    <div class="flower">
        <div class="petal petal1"></div>
        <div class="petal petal2"></div>
        <div class="petal petal3"></div>
        <div class="petal petal4"></div>
        <div class="petal petal5"></div>
        <div class="petal petal6"></div>
        <div class="center"></div>
        <div class="stem"></div>
        <div class="leaf leaf1"></div>
        <div class="leaf leaf2"></div>
    </div>

</body>
</html>
