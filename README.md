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
    <h2>To My Young Beautiful Lady</h2>
        <p>Ксюшенька, поздравляю тебя с праздником весны и Международным женским днём! 💐</p>
    <p>Это день весны, красоты и тепла, и, что самое удивительное, ты несешь в себе все эти качества ✨ Ведь от твоей женской энергии пробуждается весна на душе - все внутри расцветает, а холодные лучи солнца сменяются на более мягкие, теплые и пробуждают к жизни все вокруг!</p>
    <p>Пусть в этот день между нами и стоит большой океан, но даже он меркнет перед теплотой тех чувств, которые я испытываю к тебе ❤️ Добрые слова, мысли, поступки находят путь до наших с тобой сердец, невзирая ни на что!</p>
    <p>Ангел, оставайся такой же удивительной, вдохновляющей и нежной. Пусть в твоём сердце всегда будет тепло, как в самый ласковый весенний день 🤍</p>
    <p>Безумно скучаю, ценю и дорожу тобой. Обнимаю крепко и целую во все твои любимые места 😘💋</p>
    <p>С заботой и любовью,<br>Д.</p>
    <!-- Изображение, которое отображается при верном пароле (можно заменить на своё) -->
    <img src="IMG_1696.jpeg" alt="Secret Image" />
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
