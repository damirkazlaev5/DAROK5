<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <title>Мой сайт</title>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body {
      font-family: Arial, sans-serif;
      overflow: hidden;
      position: relative;
    }
    /* Анимация градиента */
    .gradient {
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: linear-gradient(45deg, #ff4e00, #ff9500, #ff4e00);
      background-size: 400% 400%;
      animation: gradientAnim 10s ease infinite;
    }
    @keyframes gradientAnim {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }
    /* Вкладки */
    .tabs {
      position: relative;
      z-index: 10;
      padding: 1rem;
      display: flex;
      justify-content: center;
    }
    .tab {
      padding: 0.75rem 1.5rem;
      margin: 0 0.5rem;
      background: rgba(255,255,255,0.2);
      border-radius: 0.5rem;
      cursor: pointer;
      transition: background 0.3s;
    }
    .tab:hover { background: rgba(255,255,255,0.4); }
    .tab.active { background: rgba(255,255,255,0.6); }
    /* Контент вкладок */
    .content {
      position: relative;
      z-index: 10;
      color: white;
      padding: 2rem;
      text-align: center;
      display: none;
    }
    .content.active { display: block; }
    .content img {
      max-width: 100%;
      height: auto;
      border-radius: 1rem;
      margin: 1rem 0;
    }
    .link-img {
      width: 100px;
      height: 100px;
      object-fit: cover;
      border-radius: 50%;
      margin: 1rem;
    }
    .video-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 1rem;
      margin-top: 1rem;
    }
    .video-item {
      border-radius: 0.5rem;
      overflow: hidden;
      cursor: pointer;
    }
    .video-item img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
    /* Снежинки */
    .snowflake {
      position: absolute;
      color: white;
      pointer-events: none;
      user-select: none;
      z-index: 5;
    }
  </style>
</head>
<body>
  <div class="gradient"></div>

  <!-- Вкладки -->
  <div class="tabs">
    <div class="tab active" onclick="showTab('about')">Обо мне</div>
    <div class="tab" onclick="showTab('scratch')">О Scratch</div>
    <div class="tab" onclick="showTab('lessons')">Уроки</div>
  </div>

  <!-- Контент вкладок -->
  <div id="about" class="content active">
    <h1>Обо мне</h1>
    <img src="https://via.placeholder.com/300" alt="Моё фото">
    <p>Здесь можно написать пару слов о себе.</p>
  </div>

  <div id="scratch" class="content">
    <h1>О Scratch</h1>
    <a href="https://scratch.mit.edu" target="_blank">
      <img class="link-img" src="https://via.placeholder.com/100?text=Scratch" alt="Scratch">
    </a>
    <p>Scratch — это визуальный язык программирования для детей и начинающих. Позволяет создавать анимации, игры и интерактивные истории.</p>
  </div>

  <div id="lessons" class="content">
    <h1>Уроки</h1>
    <div class="video-grid">
      <div class="video-item" onclick="window.open('https://vk.com/video...', '_blank')">
        <img src="https://via.placeholder.com/150?text=Урок+1" alt="Урок 1">
      </div>
      <div class="video-item" onclick="window.open('https://vk.com/video...', '_blank')">
        <img src="https://via.placeholder.com/150?text=Урок+2" alt="Урок 2">
      </div>
      <!-- Добавьте больше уроков по аналогии -->
    </div>
  </div>

  <script>
    // Переключение вкладок
    function showTab(tabId) {
      document.querySelectorAll('.content').forEach(tab => {
        tab.classList.toggle('active', tab.id === tabId);
      });
      document.querySelectorAll('.tab').forEach(btn => {
        btn.classList.toggle('active', btn.textContent.includes(
          document.getElementById(tabId).querySelector('h1').textContent
        ));
      });
    }

    // Создание снежинок
    function createSnowflake() {
      const snowflake = document.createElement('div');
      snowflake.className = 'snowflake';
      snowflake.textContent = '❄'; // или другой символ снежинки
      snowflake.style.fontSize = `${Math.random() * 20 + 10}px`;
      snowflake.style.left = `${Math.random() * window.innerWidth}px`;
      snowflake.style.top = '-10px';
      snowflake.style.opacity = Math.random();
      document.body.appendChild(snowflake);

      let pos = 0;
      const speed = Math.random() * 3 + 1;
      const sway = Math.random() * 2 - 1;

      function fall() {
        pos += speed;
        snowflake.style.top = `${pos}px`;
        snowflake.style.left = `${parseFloat(snowflake.style.left) + sway}px`;

        if (pos < window.innerHeight) {
          requestAnimationFrame(fall);
        } else {
          snowflake.remove();
        }
      }
      requestAnimationFrame(fall);
    }

    // Запуск снегопада
    setInterval(createSnowflake, 300);
  </script>
</body>
</html>
