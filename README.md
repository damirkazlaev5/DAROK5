<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <title>Мой мир Scratch</title>
  <style>
    * {margin:0;padding:0;box-sizing:border-box;}
    body {font-family:sans-serif;background:linear-gradient(135deg,#8b2323,#ff8c00);color:#fff;min-height:100vh;position:relative;overflow:hidden;}
    .snow {position:fixed;top:0;left:0;width:100%;height:100%;pointer-events:none;z-index:1;overflow:hidden;}
    .snowflake,.snowball {position:absolute;opacity:0.8;animation:fall linear infinite;}
    .snowflake {color:#fff;font-size:1em;}
    .snowball {background:#fff;border-radius:50%;}
    @keyframes fall {0%{transform:translateY(0) rotate(0deg);opacity:0}10%,90%{opacity:1}100%{transform:translateY(calc(100vh - 50px)) rotate(360deg);opacity:0}}
    .container {position:relative;z-index:2;max-width:1000px;margin:0 auto;padding:20px;}
    header,h1 {text-align:center;}
    h1 {font-size:2.8em;margin:30px 0 10px;text-shadow:2px 2px 6px rgba(0,0,0,0.6);}
    .nav {display:flex;justify-content:center;gap:20px;margin:25px 0;flex-wrap:wrap;}
    .btn {background:rgba(255,255,255,0.2);color:#fff;border:2px solid #fff;padding:12px 20px;border-radius:30px;cursor:pointer;font-weight:600;transition:all 0.3s;backdrop-filter:blur(5px);}
    .btn:hover {background:#ff8c00;border-color:#ff8c00;transform:translateY(-2px);}
    .section {display:none;padding:30px;background:rgba(255,255,255,0.15);border-radius:15px;margin-top:20px;backdrop-filter:blur(10px);}
    .active {display:block;}
    .about-content {display:flex;align-items:center;gap:40px;margin-top:20px;}
    .about-photo {width:200px;height:200px;border-radius:50%;object-fit:cover;border:5px solid #ff8c00;box-shadow:0 0 20px rgba(255,140,0,0.5);}
    .about-text {flex:1;line-height:1.7;font-size:1.1em;}
    .grid {display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:25px;margin-top:25px;}
    .card {background:rgba(0,0,0,0.2);border-radius:12px;overflow:hidden;text-align:center;transition:transform 0.3s,box-shadow 0.3s;}
    .card:hover {transform:translateY(-5px);box-shadow:0 15px 30px rgba(0,0,0,0.3);}
    .card img,.card a {display:block;}
    .card img {height:160px;object-fit:cover;}
    .card a {padding:15px;color:#fff;font-weight:bold;text-decoration:none;}
    footer {text-align:center;margin-top:50px;padding:25px;font-size:0.9em;opacity:0.8;border-top:1px solid rgba(255,255,255,0.3);}
    @media (max-width:768px) {.about-content{flex-direction:column;text-align:center;}.nav{flex-direction:column;align-items:center;}h1{font-size:2.2em;}}
  </style>
</head>
<body>
  <div class="snow" id="snow"></div>
  <div class="container">
    <header><h1>Мой мир Scratch</h1></header>
    <div class="nav">
      <button class="btn" onclick="showSection('about')">Обо мне</button>
      <button class="btn" onclick="showSection('scratch')">О Scratch</button>
      <button class="btn" onclick="showSection('lessons')">Уроки</button>
    </div>
    <div id="about" class="section active">
      <h2>Обо мне</h2>
      <div class="about-content">
        <img src="https://placehold.co/200x200?text=Me" alt="Фото автора" class="about-photo">
        <div class="about-text">
          <p>Привет! Меня зовут [Ваше имя], и я увлечён программированием в Scratch. Уже [X] лет создаю игры, анимации и интерактивные истории. Верю, что программирование — это творческий процесс, доступный каждому.</p>
          <p>В своих проектах я стараюсь сочетать:</p>
          <ul style="margin-left:20px;">
            <li>Креативность</li><li>Логику</li><li>Красоту дизайна</li><li>Интересную механику</li>
          </ul>
          <p>Моя цель — вдохновлять других на создание собственных проектов в Scratch!</p>
        </div>
      </div>
    </div>
    <div id="scratch" class="section">
      <h2>Что такое Scratch?</h2>
      <div class="grid">
        <div class="card">
          <img src="https://scratch.mit.edu/static/img/scratch-logo.png" alt="Логотип Scratch">
          <a href="https://scratch.mit.edu" target="_blank">Официальный сайт</a>
        </div>
        <div class="card">
          <img src="https://en.scratch-wiki.info/wiki/images/thumb/Scratch_Wiki_Logo.png/80px-Scratch_Wiki_Logo.png" alt="Wiki Scratch">
          <a href="https://ru.scratch-wiki.info" target="_blank">Scratch Wiki</a>
        </div>
        <div class="card">
          <img src="https://scratch.mit.edu/static/img/projects/project-default.png" alt="Проекты Scratch">
          <a href="https://scratch.mit.edu/explore/projects/all" target="_blank">Галерея проектов</a>
        </div>
        <div class="card">
          <img src="https://www.khanacademy.org/images/logo-square.png" alt="Khan Academy">
          <a href="https://www.khanacademy.org/computing/computer-programming/scratch" target="_blank">Уроки на Khan Academy</a>
        </div>
      </div>
    </div>
    <div id="lessons" class="section">
      <h2>Полезные уроки</h2>
      <div class="grid">
        <div class="card">
          <img src="https://i.ytimg.com/vi/dQw4w9WgXcQ/hqdefault.jpg" alt="Урок 1">
          <a href="https://youtube.com/watch?v=dQw4w9WgXcQ" target="_blank">Основы Scratch</a>
        </div>
        <div class="card">
          <img src="https://i.ytimg.com/vi/abc123/hqdefault.jpg" alt="Урок 2">
          <a href="https://youtube.com/watch?v=abc123" target="_blank">Анимация в Scratch</a>
        </div>
        <div class="card">
          <img src="https://i.ytimg.com/vi/def456/hqdefault.jpg" alt="Урок 3">
          <a href="https://youtube.com/watch?v=def456" target="_blank">Создание игр</a>
                  </div>
        <div class="card">
          <img src="https://i.ytimg.com/vi/ghi789/hqdefault.jpg" alt="Урок 4">
          <a href="https://youtube.com/watch?v=ghi789" target="_blank">Продвинутые техники</a>
        </div>
      </div>
    </div>

    <footer>
      © 2025 Мой мир Scratch | Образовательный ресурс
      <p style="margin-top:10px;font-size:0.8em;">
        Scratch — проект MIT Media Lab. Все права на логотип и контент принадлежат их авторам.
      </p>
    </footer>
  </div>

  <script>
    function showSection(id) {
      document.querySelectorAll('.section').forEach(section => {
        section.classList.toggle('active', section.id === id);
      });
    }

    function createSnowElement() {
      const snow = document.getElementById('snow');
      const element = document.createElement('div');
      const isSnowflake = Math.random() > 0.5;

      if (isSnowflake) {
        element.className = 'snowflake';
        element.textContent = '❄';
      } else {
        element.className = 'snowball';
      }

      const size = Math.random() * 20 + 10;
      const left = Math.random() * 100;
      const opacity = Math.random() * 0.7 + 0.3;
      const duration = Math.random() * 10 + 5;
      const delay = Math.random() * 5;

      element.style.width = `${size}px`;
      element.style.height = `${size}px`;
      element.style.left = `${left}%`;
      element.style.opacity = opacity;
      element.style.animationDuration = `${duration}s`;
      element.style.animationDelay = `${delay}s`;

      snow.appendChild(element);

      setTimeout(() => {
        element.remove();
      }, (duration + delay) * 1000);
    }

    setInterval(createSnowElement, 150);

    for (let i = 0; i < 20; i++) {
      createSnowElement();
    }
  </script>
</body>
</html>
