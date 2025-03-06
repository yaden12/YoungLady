DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Password Protected Page</title>
  <style>
    /* Простые стили для оформления */
    body {
      font-family: Arial, sans-serif;
      background-color: #f4f4f4;
      margin: 0;
      padding: 0;
      text-align: center;
    }
    #login-box {
      background-color: #fff;
      max-width: 300px;
      margin: 100px auto;
      padding: 20px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    #login-box p {
      margin: 0 0 10px;
      font-size: 1.1em;
    }
    #password-input {
      width: 100%;
      padding: 8px;
      box-sizing: border-box;
      font-size: 1em;
      margin-bottom: 10px;
    }
    #submit-btn {
      width: 100%;
      padding: 10px;
      font-size: 1em;
      border: none;
      border-radius: 4px;
      background-color: #5cb85c;
      color: #fff;
      cursor: pointer;
    }
    #submit-btn:hover {
      background-color: #4cae4c;
    }
    #message {
      color: red;
      margin-top: 10px;
      height: 1.2em; /* Резервируем место для сообщения */
    }
    #protected-content {
      display: none; /* Скрываем контент по умолчанию */
      max-width: 600px;
      margin: 50px auto;
      text-align: center;
    }
    #protected-content img {
      max-width: 100%;
      height: auto;
    }
  </style>
</head>
<body>
  <div id="login-box">
    <p>Введите пароль:</p>
    <form id="login-form">
      <input type="password" id="password-input" placeholder="Пароль" required />
      <button type="submit" id="submit-btn">Войти</button>
    </form>
    <p id="message"></p>
  </div>
  
  <div id="protected-content">
    <h2>Секретный контент</h2>
    <p>Поздравляем! Вы ввели правильный пароль и получили доступ к защищённому контенту.</p>
    <!-- Изображение, которое отображается при верном пароле (можно заменить на своё) -->
    <img src="https://placekitten.com/400/300" alt="Secret Image" />
    <p>Эту картинку и текст видят только те, кто знает пароль.</p>
  </div>
  
  <script>
    // JavaScript для проверки пароля
    const CORRECT_PASSWORD = "5466"; // Пароль (измените при необходимости)
    
    document.getElementById("login-form").addEventListener("submit", function(event) {
      event.preventDefault(); // Отменяем стандартное действие формы (перезагрузку)
      const enteredPassword = document.getElementById("password-input").value;
      
      if (enteredPassword === CORRECT_PASSWORD) {
        // Пароль верный – показываем защищённый контент и скрываем форму ввода
        document.getElementById("protected-content").style.display = "block";
        document.getElementById("login-box").style.display = "none";
      } else {
        // Пароль неверный – показываем сообщение об ошибке
        document.getElementById("message").textContent = "Неверный пароль. Попробуйте снова.";
        document.getElementById("password-input").value = "";
        document.getElementById("password-input").focus();
      }
    });
  </script>
</body>
</html>
