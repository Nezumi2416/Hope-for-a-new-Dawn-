# Hope-for-a-new-Dawn-
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hope for a New Dawn</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            background-color: #34495e;
            font-family: 'Arial', sans-serif;
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            flex-direction: column; /* Alineación vertical */
        }
        .title-container {
            margin: 50px 0; /* Espacio arriba y abajo del título */
        }
        .title {
            font-size: 4rem; /* Tamaño grande para el título */
            color: #e74c3c; /* Color que destaca sobre el fondo oscuro */
            text-shadow: 2px 2px 4px #000000; /* Sombra para resaltar el texto */
        }
        .menu-container, .info-container {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            text-align: center;
        }
        .menu, .info {
            background-color: #2c3e50;
            border-radius: 8px;
            padding: 20px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            transition: transform 0.5s;
        }
        .menu:hover, .info:hover {
            transform: scale(1.05);
        }
        input[type="text"], input[type="password"], .info-content {
            width: 200px;
            padding: 10px;
            margin-bottom: 10px;
            border: none;
            border-radius: 5px;
        }
        .button {
            width: 100%;
            padding: 10px;
            border: none;
            border-radius: 5px;
            background-color: #16a085;
            color: white;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        .button:hover {
            background-color: #1abc9c;
        }
        .error {
            color: red;
            animation: shake 0.5s;
        }
        @keyframes shake {
            0% { transform: translateX(0); }
            25% { transform: translateX(-5px); }
            50% { transform: translateX(5px); }
            75% { transform: translateX(-5px); }
            100% { transform: translateX(0); }
        }
    </style>
</head>
<body>

<div class="title-container">
    <h1 class="title">Hope for a New Dawn</h1>
</div>

<div class="menu-container" id="login-page">
    <div class="menu">
        <input type="text" id="username" placeholder="Usuario">
        <input type="password" id="password" placeholder="Contraseña">
        <button class="button" onclick="login()">Ingresar</button>
        <div id="message"></div>
    </div>
</div>

<div class="info-container" id="info-page" style="display:none;">
    <div class="info">
        <div class="info-title">Bienvenido, Juan</div>
        <div class="info-content">
            Aquí está tu información detallada:
            <ul>
                <li>Nombre: Juan</li>
                <li>Apellido: Mojica</li>
                <li>Ocupación: Desarrollador Web</li>
                <!-- Agrega más información detallada aquí -->
            </ul>
        </div>
    </div>
</div>

<script>
    function login() {
        var username = document.getElementById('username').value;
        var password = document.getElementById('password').value;
        var message = document.getElementById('message');
        var loginPage = document.getElementById('login-page');
        var infoPage = document.getElementById('info-page');
        if(username === 'Juan' && password === 'Mojica') {
            loginPage.style.display = 'none';
            infoPage.style.display = 'flex';
        } else {
            message.textContent = '¡Datos incorrectos!';
            message.classList.add('error');
            setTimeout(function() {
                message.textContent = '';
                message.classList.remove('error');
            }, 2000);
        }
    }
</script>

</body>
</html>
