<html lang="ru">

<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Правила чата</title>
  <meta name="description" content="Правила чата: соблюдение, модерация, наказания, политика." />
  <meta name="keywords" content="чат, правила, модерация, наказания, политика" />
  //fonts.googleapis.com" crossorigin />
  //fonts.gstatic.com" crossorigin />
  //fonts.googleapis.com/css2?family=Inter:wght@400;600;700&family=Roboto+Slab:wght@700&display=swap"
    rel="stylesheet" />
  <style>
    /* === Общие стили === */
    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial,
        sans-serif;
      margin: 0;
      line-height: 1.6;
      color: #cbd5e1;
      min-height: 100vh;
      padding-top: 100px;
      box-sizing: border-box;
      display: flex;
      justify-content: center;
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
      overflow-x: hidden;

      background-color: #0b1a2d;
      background-image: url('https://www.transparenttextures.com/patterns/stardust.png');
      background-repeat: repeat;
      background-size: auto;

      position: relative;
      z-index: 0;
    }

    /* === Фоновые облака === */
    #background-container {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      pointer-events: none;
      z-index: 0;
      overflow: hidden;
      background: transparent;
    }

    .cloud {
      position: absolute;
      top: 0;
      background-repeat: no-repeat;
      background-size: contain;
      opacity: 0.25;
      animation-timing-function: linear;
      filter: drop-shadow(0 0 6px rgba(107, 122, 140, 0.5));
      user-select: none;
      pointer-events: none;
      will-change: transform;
      animation: cloudMove linear infinite;
    }

    .cloud.small {
      width: 100px;
      height: 60px;
    }

    .cloud.medium {
      width: 180px;
      height: 100px;
    }

    .cloud.large {
      width: 280px;
      height: 150px;
    }

    .cloud1 {
      background-image: url("image/svg+xml,%3csvg width='280' height='150' viewBox='0 0 280 150' fill='none' xmlns='http://www.w3.org/2000/svg'%3e%3cellipse cx='140' cy='75' rx='120' ry='60' fill='%236b7a8c' fill-opacity='0.2'/%3e%3c/svg%3e");
      border-radius: 120px / 60px;
    }

    .cloud2 {
      background-image: url("image/svg+xml,%3csvg width='180' height='100' viewBox='0 0 180 100' fill='none' xmlns='http://www.w3.org/2000/svg'%3e%3ccircle cx='60' cy='50' r='40' fill='%236b7a8c' fill-opacity='0.15'/%3e%3ccircle cx='110' cy='50' r='50' fill='%236b7a8c' fill-opacity='0.15'/%3e%3c/svg%3e");
      border-radius: 100px / 50px;
    }

    .cloud3 {
      background-image: url("image/svg+xml,%3csvg width='100' height='60' viewBox='0 0 100 60' fill='none' xmlns='http://www.w3.org/2000/svg'%3e%3ccircle cx='40' cy='30' r='20' fill='%236b7a8c' fill-opacity='0.15'/%3e%3ccircle cx='70' cy='30' r='30' fill='%236b7a8c' fill-opacity='0.15'/%3e%3c/svg%3e");
      border-radius: 60px / 30px;
    }

    .cloud1.large {
      animation-duration: 120s;
      top: 10vh;
      left: -300px;
    }

    .cloud2.medium {
      animation-duration: 90s;
      top: 25vh;
      left: -180px;
      animation-delay: 30s;
    }

    .cloud3.small {
      animation-duration: 75s;
      top: 40vh;
      left: -100px;
      animation-delay: 15s;
    }

    .cloud1.medium {
      animation-duration: 110s;
      top: 55vh;
      left: -250px;
      animation-delay: 45s;
    }

    .cloud2.small {
      animation-duration: 95s;
      top: 70vh;
      left: -150px;
      animation-delay: 60s;
    }

    @keyframes cloudMove {
      0% {
        transform: translateX(0);
      }

      100% {
        transform: translateX(110vw);
      }
    }

    /* Иконки (частицы) */
    #particles-container {
      position: fixed;
      bottom: 0;
      left: 0;
      width: 100vw;
      height: 40vh;
      pointer-events: none;
      z-index: 1;
      overflow: visible;
      will-change: transform;
      background: transparent;
    }

    /* Основной контент */
    main {
      background: rgba(11, 26, 45, 0.75);
      backdrop-filter: blur(12px);
      border-radius: 12px;
      box-shadow: 0 8px 30px rgba(124, 58, 237, 0.5);
      max-width: 900px;
      width: 100%;
      padding: 30px 40px;
      box-sizing: border-box;
      color: #cbd5e1;
      animation: fadeInMain 0.8s ease forwards;
      user-select: text;
      outline-offset: 4px;
      text-align: left;
      margin-top: 20px;
      position: relative;
      z-index: 10;
    }

    @keyframes fadeInMain {
      from {
        opacity: 0;
        transform: translateY(15px) scale(0.95);
      }

      to {
        opacity: 1;
        transform: translateY(0) scale(1);
      }
    }

    h1 {
      font-family: 'Roboto Slab', serif;
      font-size: 2.4em;
      margin-bottom: 0.4em;
      color: transparent;
      background: linear-gradient(270deg, #ff6b6b, #fbc531, #4cd137, #00a8ff, #9c88ff, #ff6b6b);
      background-size: 1200% 1200%;
      -webkit-background-clip: text;
      background-clip: text;
      animation: rainbowGradient 10s ease infinite;
      text-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
      user-select: none;
      text-align: center;
    }

    @keyframes rainbowGradient {
      0% {
        background-position: 0% 50%;
      }

      50% {
        background-position: 100% 50%;
      }

      100% {
        background-position: 0% 50%;
      }
    }

    main>p:first-of-type {
      font-family: 'Inter', sans-serif;
      font-size: 1.2em;
      color: #a0aec0;
      margin-top: 0;
      margin-bottom: 2em;
      max-width: 700px;
      line-height: 1.5;
      user-select: text;
      text-align: center;
    }

    h2:not(:first-of-type),
    h3:not(:first-of-type) {
      border-top: 2px solid;
      border-image-slice: 1;
      border-image-source: linear-gradient(90deg, #7c3aed, #a78bfa);
      border-style: solid;
      padding-top: 16px;
      margin-top: 48px;
      user-select: none;
      cursor: default;
      font-weight: 700;
    }

    h2:not(:first-of-type) {
      text-align: center;
      font-size: 1.6em;
      color: transparent;
      background-image: linear-gradient(270deg, #7c3aed, #a78bfa);
      background-size: 600% 600%;
      -webkit-background-clip: text;
      background-clip: text;
      animation: rainbowGradient 15s ease infinite;
      text-shadow: 0 0 2px rgba(124, 58, 237, 0.3);
    }

    /* Исправленные стили для h3 - видимый текст с тенью, без прозрачности и градиентов */
    section h3 {
      border: none !important;
      padding: 0 !important;
      margin-bottom: 0.5em;
      color: #d8b4fe;
      background: none !important;
      -webkit-background-clip: unset !important;
      background-clip: unset !important;
      text-shadow:
        0 0 4px rgba(168, 85, 247, 0.7),
        0 0 8px rgba(168, 85, 247, 0.5);
      font-weight: 700;
      font-family: 'Inter', sans-serif;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    p,
    ul {
      font-family: 'Inter', sans-serif;
      font-size: 1.05em;
      color: #cbd5e1;
      letter-spacing: 0.02em;
      user-select: text;
      text-align: left;
    }

    ul {
      padding-left: 1.4em;
      margin-bottom: 1.5em;
    }

    ul li {
      margin-bottom: 0.8em;
      border-bottom: none;
    }

    strong {
      font-family: 'Inter', sans-serif;
      color: #d8b4fe;
      font-weight: 700;
    }

    em {
      font-family: 'Inter', sans-serif;
      color: #a0aec0;
      font-style: italic;
    }

    footer {
      font-family: 'Inter', sans-serif;
      margin-top: 40px;
      font-size: 0.9em;
      color: #9ca3af;
      text-align: center;
      user-select: none;
      letter-spacing: 0.02em;
      position: relative;
      z-index: 10;
    }

    mark {
      background-color: #7c3aed88;
      color: #e0e7ff;
      font-weight: 700;
      border-radius: 3px;
      padding: 0 2px;
      box-shadow: none;
      animation: none;
      transition: background-color 0.3s ease;
    }

    mark:hover {
      background-color: #a78bfaaa;
      box-shadow: none;
    }

    #no-results {
      font-family: 'Inter', sans-serif;
      text-align: center;
      color: #9ca3af;
      font-size: 1.1em;
      margin-top: 20px;
      display: none;
      user-select: none;
      position: relative;
      z-index: 10;
    }

    #back-to-top {
      display: none !important;
    }

    #signature {
      margin-top: 60px;
      text-align: center;
      user-select: none;
      position: relative;
      z-index: 10;
    }

    #signature p {
      font-family: 'Roboto Slab', serif;
      font-weight: 700;
      font-size: 1.4em;
      background: linear-gradient(270deg, #ff6b6b, #fbc531, #4cd137, #00a8ff, #9c88ff);
      background-size: 600% 600%;
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      animation: rainbowGradient 10s ease infinite;
      margin: 0;
    }

    a {
      color: #a78bfa;
      text-decoration: none;
      animation: pulseGlow 4s ease-in-out infinite;
      transition: color 0.3s ease;
    }

    a:hover,
    a:focus {
      text-decoration: underline;
      color: #d8b4fe;
      outline: none;
    }

    button {
      background-color: #7c3aed;
      color: white;
      border: none;
      border-radius: 6px;
      padding: 8px 16px;
      font-weight: 700;
      cursor: pointer;
      transition: background-color 0.3s ease;
      user-select: none;
      animation: pulseGlow 4s ease-in-out infinite;
      outline-offset: 2px;
    }

    button:hover,
    button:focus {
      background-color: #a78bfa;
      outline: none;
    }

    textarea,
    input {
      font-family: inherit;
      font-size: 14px;
      padding: 8px;
      border-radius: 6px;
      border: 1px solid #4c1d95;
      background-color: #1e293b;
      color: #e0e7ff;
      resize: vertical;
      width: 100%;
      box-sizing: border-box;
    }

    textarea::placeholder,
    input::placeholder {
      color: #9ca3af;
    }

    #search-container {
      position: fixed;
      top: 0;
      left: 50%;
      transform: translateX(-50%);
      background: rgba(11, 26, 45, 0.95);
      backdrop-filter: blur(12px);
      max-width: 900px;
      width: 100%;
      padding: 12px 20px;
      box-sizing: border-box;
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 10000;
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.5);
      user-select: none;
      color: #cbd5e1;
    }

    #search-input {
      width: 100%;
      max-width: 400px;
      padding: 10px 40px 10px 14px;
      font-size: 1.1em;
      border: 2px solid #7c3aed;
      border-radius: 12px;
      outline-offset: 2px;
      transition: border-color 0.3s ease;
      font-family: 'Inter', sans-serif;
      color: #e0e7ff;
      background: #1e293b;
      box-shadow: 0 2px 8px rgba(124, 58, 237, 0.15);
      position: relative;
    }

    #search-input::placeholder {
      color: #a5b4fc;
    }

    #search-input:focus {
      border-color: #a78bfa;
      box-shadow: 0 0 8px #a78bfa;
      background: #2c2f48;
      color: #fefefe;
    }

    #clear-button {
      position: absolute;
      right: 30px;
      background: transparent;
      border: none;
      cursor: pointer;
      font-size: 1.5em;
      color: #a78bfa;
      padding: 0;
      line-height: 1;
      user-select: none;
      display: none;
      transition: color 0.3s ease;
      z-index: 10;
      outline-offset: 2px;
      animation: pulseGlow 4s ease-in-out infinite;
    }

    #clear-button:hover,
    #clear-button:focus {
      color: #d8b4fe;
      outline: none;
    }

    /* === Блок навигации (без анимаций) === */
   
/* === Блок навигации (без анимаций) === */
nav {
  background: transparent;
  padding: 10px 20px;
  border-radius: 12px;
  max-width: 900px;
  margin: 0 auto 40px;
  user-select: none;
  color: #cbd5e1;
  box-shadow: 0 0 12px rgb(124 58 237 / 0.4);
  font-weight: 600;
  font-family: 'Inter', sans-serif;
  font-size: 1.1em;
  text-align: center;
  position: relative;
  z-index: 10;
}

nav .toc-header {
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 12px;
  margin-bottom: 12px;
  user-select: none;
  color: #a78bfa;
  font-weight: 700;
  font-size: 1.3em;
  outline-offset: 2px;
  transition: color 0.3s ease;
}

nav .toc-header:hover,
nav .toc-header:focus {
  color: #d8b4fe;
  outline: none;
}

nav .toc-header svg {
  stroke: currentColor;
  stroke-width: 2.5;
  width: 30px;
  height: 30px;
  transition: stroke 0.3s ease;
  user-select: none;
}

/* Список навигации без анимаций и переходов, пункты в строку по центру */
nav ul.toc-list {
  list-style: none;
  padding: 0;
  margin: 0;
  max-height: none !important;
  overflow: visible !important;
  user-select: text;
  opacity: 1 !important;
  transform: none !important;
  pointer-events: auto !important;
  transition: none !important;
  display: block !important;

  text-align: center;
}

nav ul.toc-list.collapsed {
  display: none !important;
  max-height: 0 !important;
  overflow: hidden !important;
  opacity: 0 !important;
  transform: none !important;
  pointer-events: none !important;
  transition: none !important;
}

nav ul.toc-list li {
  display: inline-block;
  margin: 0 12px;
  opacity: 1 !important;
  transform: none !important;
  animation: none !important;
  animation-fill-mode: none !important;
  animation-name: none !important;
  animation-duration: 0s !important;
  animation-timing-function: none !important;
  animation-delay: 0s !important;
  border-top: 1.5px solid transparent;
  border-bottom: 1.5px solid transparent;
  padding: 4px 0;
}

nav ul.toc-list li a {
  color: #cbd5e1;
  text-decoration: none;
  display: inline-block;
  width: fit-content;
  transition: color 0.3s ease, border-color 0.3s ease;
}

nav ul.toc-list li a:hover,
nav ul.toc-list li a:focus,
nav ul.toc-list li a.active {
  border-top-color: #a78bfa;
  border-bottom-color: #a78bfa;
  outline: none;
  color: #a78bfa;
}

/* === Анимация кнопок копирования === */
.copy-btn {
  background: transparent;
  border: none;
  cursor: pointer;
  font-size: 1.2em;
  transition: transform 0.25s ease, color 0.3s ease;
  color: #a78bfa;
  user-select: none;
  padding: 0 6px;
  border-radius: 4px;
  outline-offset: 2px;
  box-shadow: 0 0 4px transparent;
}

.copy-btn:hover,
.copy-btn:focus {
  color: #d8b4fe;
  transform: translateY(-2px) scale(1.1);
  box-shadow:
    0 0 6px #a78bfa,
    0 0 10px #d8b4fe;
  outline: none;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
}

.copy-btn:active {
  transform: translateY(0) scale(0.95);
  box-shadow: none;
}

/* === Пульсирующее свечение для ссылок и кнопок === */
@keyframes pulseGlow {
  0%,
  100% {
    box-shadow: 0 0 0 rgba(167, 139, 250, 0);
  }

  50% {
    box-shadow: 0 0 8px rgba(167, 139, 250, 0.6);
  }
}

/* === Анимация частиц-звёздочек внизу === */
.particle {
  position: absolute;
  border-radius: 50%;
  background: radial-gradient(circle at center, #a78bfa, transparent);
  opacity: 0.8;
  animation-name: twinkle;
  animation-iteration-count: infinite;
  animation-timing-function: ease-in-out;
}

@keyframes twinkle {
  0%,
  100% {
    opacity: 0.6;
    transform: scale(1);
  }

  50% {
    opacity: 1;
    transform: scale(1.3);
  }
}

/* === Плавное появление секций при скролле === */
section,
p,
ul {
  opacity: 0;
  transform: translateY(20px);
  transition: opacity 0.6s ease, transform 0.6s ease;
}

section.visible,
p.visible,
ul.visible {
  opacity: 1;
  transform: translateY(0);
}
</style>

</head>

<body>
  <div id="search-container">
    <input type="search" id="search-input" aria-label="Поиск по правилам" placeholder="Поиск по правилам..."
      autocomplete="off" spellcheck="false" />
    <button id="clear-button" aria-label="Очистить поиск" title="Очистить поиск">&times;</button>
  </div>

  <div id="background-container" aria-hidden="true" aria-label="Фоновая анимация облаков и иконок">
    <div class="cloud cloud1 large"></div>
    <div class="cloud cloud2 medium"></div>
    <div class="cloud cloud3 small"></div>
    <div class="cloud cloud1 medium"></div>
    <div class="cloud cloud2 small"></div>
  </div>

  <main id="main-content" tabindex="-1">
    <h1>Правила чата</h1>

    <p>Каждый вошедший пользователь добровольно принимает правила нашего чата и обязуется их соблюдать.</p>

    <nav aria-label="Оглавление">
      <div class="toc-header" role="button" tabindex="0" aria-expanded="true" aria-controls="toc-list" id="toc-toggle">
        <svg class="toc-icon" viewBox="0 0 24 24" aria-hidden="true" focusable="false" fill="none" stroke="currentColor"
          stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <line x1="3" y1="6" x2="21" y2="6"></line>
          <line x1="3" y1="12" x2="21" y2="12"></line>
          <line x1="3" y1="18" x2="21" y2="18"></line>
        </svg>
        Навигация
      </div>
      <ul id="toc-list" tabindex="-1" class="toc-list">
        <li><a href="#ne-zhelatelno">Не желательно</a></li>
        <li><a href="#zapreshchaetsya">Запрещается</a></li>
        <li><a href="#dopolneniya-po-moderatoram">Важные дополнения по работе модераторов и контролю качества их действий</a>
        </li>
        <li><a href="#nakazaniya">Наказания</a></li>
        <li><a href="#politika">Политика модераторов</a></li>
      </ul>
    </nav>

    <!-- Основное содержимое правил -->
    <section id="samoe-vazhnoe">
      <h2>Самое важное</h2>
      <p><strong>Каждый участник чата обязан уважать других, соблюдать правила и поддерживать дружелюбную атмосферу.</strong>
      </p>
      <p>Нарушение этого принципа ведёт к предупреждениям и, при повторении — к более строгим мерам вплоть до бана.</p>
    </section>

    <section id="ne-zhelatelno">
      <h3>1. Использование большого количества ненормативной лексики <button class="copy-btn"
          title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Предупреждение</p>
      <p><strong>Пояснение:</strong> Мы понимаем, что иногда эмоции берут верх, но старайтесь не злоупотреблять матом. Если
        вы используете ненормативную лексику редко и без оскорблений — это не проблема.</p>
      <p><strong>Пример:</strong> «Вот это классно!» — нормально; «Ты полный [нецензурное слово]» — повод для предупреждения.
      </p>

      <h3>2. Рекламировать другие группы/каналы <button class="copy-btn" title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Предупреждение</p>
      <p><strong>Пояснение:</strong> Реклама чужих ресурсов без согласия администрации мешает общению. Если хотите поделиться
        полезным каналом — сначала свяжитесь с администратором (@lia_os).</p>
      <p><strong>Пример:</strong> «Подпишитесь на мой канал!» — запрещено без разрешения.</p>

      <h3>3. Начинать ссоры, старайтесь поддерживать комфорт в чате <button class="copy-btn" title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Предупреждение или мут (в зависимости от интенсивности)</p>
      <p><strong>Пояснение:</strong> Споры бывают, но если они переходят в оскорбления или мешают другим — сначала предупредим,
        а при повторе временно ограничим возможность писать (мут).</p>
      <p><strong>Пример:</strong> «Ты неправ!» — нормально, «Ты идиот!» — повод для наказания.</p>

      <h3>
        4. Flash — видео/голосовые (редкие громкие звуки, резко мерцающие видео)
        <button class="copy-btn" title="Скопировать правило">📋</button>
      </h3>
      <p><strong>Наказание:</strong> Мут</p>
      <p><strong>Пояснение:</strong> Такие материалы могут раздражать или вредить здоровью участников (например, вызывать головную боль). Поэтому за их публикацию временно ограничивается возможность писать.</p>

      <h3>5. Оскорбление персонажей, уважайте чувства и вкусы других <button class="copy-btn" title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Предупреждение или мут</p>
      <p><strong>Пояснение:</strong> Критика — нормально, а личные оскорбления — нет.</p>
      <p><strong>Пример:</strong> «Мне не нравится этот персонаж» — допустимо, «Этот персонаж — дурак» — нарушение.</p>

      <h3>6. Пересылка личных сообщений другого человека в беседу <button class="copy-btn" title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Предупреждение</p>
      <p><strong>Пояснение:</strong> Личные сообщения другого участника нельзя пересылать в общий чат без согласия обеих
        сторон. Если оба участника переписки являются членами группы, часть переписки пересылается только с одобрения обеих
        сторон. Это помогает сохранять приватность и уважать личное пространство.</p>
      <p><strong>Пример:</strong> Пересылать скриншоты или сообщения из личных диалогов без разрешения — запрещено.</p>
    </section>

    <section id="zapreshchaetsya">
      <h2>Запрещается</h2>

      <h3>1. Обсуждение политики и публикация любого контента, связанного с политикой <button class="copy-btn"
          title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Бан</p>
      <p><strong>Пояснение:</strong> Политика часто вызывает конфликты и разделение. Чтобы сохранить дружелюбную атмосферу,
        такие темы запрещены.</p>
      <p><strong>Пример:</strong> обсуждение выборов, политических лидеров и т.п.</p>

      <h3>2. Оскорбления <button class="copy-btn" title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Предупреждение, при повторе — мут или бан</p>
      <p><strong>Пояснение:</strong> Шутки — хорошо, но если кому-то неприятно — защитим его.</p>
      <p><strong>Пример:</strong> «Ты такой смешной дурачок» — шутка, но если это обидело — последует предупреждение.</p>

      <h3>3. Публикация порнографического и околопорнографического контента <button class="copy-btn"
          title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Бан</p>
      <p><strong>Пояснение:</strong> Нарушает правила приличия и закон.</p>
      <p><strong>Пример:</strong> откровенные фото, видео или ссылки.</p>

      <h3>4. Публикация треш-контента (стикеры/видео/гиф с расчленenкой и тому подобное) <button class="copy-btn"
          title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Бан</p>
      <p><strong>Пояснение:</strong> Шокирующие материалы могут травмировать участников.</p>
      <p><strong>Пример:</strong> видео с насилием или жестокостью.</p>

      <h3>5. Поднятие тем, нарушающих законы РФ (экстремизм, терроризм, пропаганда наркотиков, оскорбление чувств верующих и др.) <button class="copy-btn"
          title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Бан</p>
      <p><strong>Пояснение:</strong> Такие темы запрещены законом и чатом.</p>
      <p><strong>Пример:</strong> призывы к насилию, обсуждение запрещённых веществ.</p>

      <h3>6. Спам / флуд (часто повторяющиеся сообщения, сообщения без смысла) <button class="copy-btn"
          title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Мут</p>
      <p><strong>Пояснение
      <p><strong>Пояснение:</strong> Чтобы чат был удобен для всех, не стоит засорять его бессмысленными сообщениями.</p>
      <p><strong>Пример:</strong> повторять одну и ту же фразу много раз подряд.</p>

      <h3>7. Публичное осуждение действий администрации / провокация администрации типа «ну давай бань меня» <button class="copy-btn" title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Предупреждение или мут</p>
      <p><strong>Пояснение:</strong> Если есть вопросы к администрации — лучше написать в личку, а не провоцировать конфликт в общем чате.</p>

      <h3>8. Любая дискриминация по расовому/национальному/половому/религиозному признаку <button class="copy-btn" title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Бан</p>
      <p><strong>Пояснение:</strong> Мы за равенство и уважение ко всем.</p>
      <p><strong>Пример:</strong> оскорбления по национальному признаку недопустимы.</p>

      <h3>9. Просьбы перейти по ссылкам/зарегистрироваться на вредоносном сайте <button class="copy-btn" title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Бан</p>
      <p><strong>Пояснение:</strong> Безопасность участников — наш приоритет.</p>
      <p><strong>Пример:</strong> ссылки на мошеннические сайты.</p>
    </section>

    <section id="dopolneniya-po-moderatoram">
      <h2>Важные дополнения по работе модераторов и контролю качества их действий</h2>

      <h3>10. Модераторы обязаны действовать в соответствии с правилами чата и не использовать свои полномочия в личных интересах <button class="copy-btn" title="Скопировать правило">📋</button></h3>
      <p><strong>Пояснение:</strong> Если заметили нарушение или злоупотребление полномочиями (например, необоснованно мутит или банит, игнорирует правила), обратитесь к высшим администраторам или создателю чата (@lia_os). Жалобы рассматриваются, и мы защищаем от несправедливого обращения.</p>

      <h3>11. Перед применением наказания модератор должен дать словесное предупреждение участнику <button class="copy-btn" title="Скопировать правило">📋</button></h3>
      <p><strong>Пояснение:</strong> Если поведение начинает нарушать правила или мешать комфорту, модератор предупреждает: «Пожалуйста, прекратите, иначе последуют меры». Если предупреждение игнорируется — применяется наказание (мут, бан и т.п.). Это помогает избежать конфликтов и даёт шанс исправиться.</p>
    </section>

    <section id="nakazaniya">
      <h2>Наказания</h2>
      <ul>
        <li><strong>Предупреждение</strong> — первое и мягкое наказание. Сообщаем, что поведение не соответствует правилам с объяснением.</li>
        <li><strong>Мут</strong> — временное ограничение возможности писать (несколько минут или часов). Используется при повторных нарушениях или серьёзных проступках. Перед мутом обязательно словесное предупреждение.</li>
        <li><strong>Бан</strong> — удаление из чата с запретом на повторный вход. За серьёзные или неоднократные нарушения.</li>
      </ul>
    </section>

    <section id="politika">
      <h2>Политика модераторов</h2>
      <ul>
        <li>Всегда сначала предупреждайте участников, чтобы дать им шанс исправиться.</li>
        <li>Действуйте объективно и справедливо, руководствуясь правилами, а не личными симпатиями.</li>
        <li>При сомнениях или спорных ситуациях обращайтесь к высшему администратору для консультации.</li>
        <li>Помните, что ваша задача — поддерживать комфорт и безопасность в чате, а не «наказывать» ради наказания.</li>
      </ul>
    </section>

    <!-- Добавленная благодарность -->
    <section id="thanks" aria-label="Благодарность">
      <p>Спасибо, что соблюдаете правила и делаете чат приятным для всех!</p>
    </section>

    <div id="no-results" role="alert" aria-live="polite">Ничего не найдено.</div>

    <section id="signature" aria-label="Подпись автора">
      <p>by Везунчик</p>
    </section>

    <footer>
      <p>Если у вас есть вопросы или нужна помощь — обращайтесь к администрации (<strong>@lia_os</strong>).</p>
    </footer>
  </main>

  <div id="particles-container" aria-hidden="true"></div>

  <script>
    // === Оглавление: раскрытие/скрытие без анимаций ===
    (() => {
      const toggle = document.getElementById('toc-toggle');
      const list = document.getElementById('toc-list');

      function setCollapsed(collapsed) {
        if (collapsed) {
          list.classList.add('collapsed');
          toggle.setAttribute('aria-expanded', 'false');
        } else {
          list.classList.remove('collapsed');
          toggle.setAttribute('aria-expanded', 'true');
        }
      }

      setCollapsed(false);

      toggle.addEventListener('click', () => {
        const isCollapsed = list.classList.contains('collapsed');
        setCollapsed(!isCollapsed);
      });

      toggle.addEventListener('keydown', (e) => {
        if (e.key === 'Enter' || e.key === ' ') {
          e.preventDefault();
          toggle.click();
        }
      });

      // Плавный скролл и фокус по клику на навигацию
      list.querySelectorAll('a').forEach(link => {
        link.addEventListener('click', e => {
          e.preventDefault();
          const targetId = link.getAttribute('href').substring(1);
          const target = document.getElementById(targetId);
          if (target) {
            target.focus({ preventScroll: true });
            window.scrollTo({
              top: target.getBoundingClientRect().top + window.pageYOffset - 60,
              behavior: 'smooth'
            });
          }
        });
      });
    })();

    // === Появление секций при скролле (вверх и вниз) ===
    (() => {
      const elements = [...document.querySelectorAll('section, p, ul')];

      function onScroll() {
        const windowHeight = window.innerHeight;
        const scrollTop = window.pageYOffset || document.documentElement.scrollTop;

        elements.forEach(el => {
          const rect = el.getBoundingClientRect();
          const elTop = rect.top + scrollTop;
          const elBottom = elTop + rect.height;

          // Показываем элемент, если он хотя бы частично виден в viewport с небольшим запасом (50px)
          if ((elBottom > scrollTop + 50) && (elTop < scrollTop + windowHeight - 50)) {
            if (!el.classList.contains('visible')) {
              el.classList.add('visible');
            }
          } else {
            if (el.classList.contains('visible')) {
              el.classList.remove('visible');
            }
          }
        });
      }

      // Инициализируем видимость при загрузке
      window.addEventListener('load', onScroll);
      window.addEventListener('scroll', onScroll);
      window.addEventListener('resize', onScroll);

      // Запуск сразу
      onScroll();
    })();

    // === Поиск по тексту с подсветкой ===
    (() => {
      const searchInput = document.getElementById('search-input');
      const clearButton = document.getElementById('clear-button');
      const mainContent = document.getElementById('main-content');
      const noResults = document.getElementById('no-results');

      // Убираем все <mark>
      function clearHighlights() {
        const marks = mainContent.querySelectorAll('mark');
        marks.forEach(mark => {
          const parent = mark.parentNode;
          parent.replaceChild(document.createTextNode(mark.textContent), mark);
          parent.normalize();
        });
      }

      // Подсветка текста в элементе
      function highlightText(text) {
        if (!text) return;
        // Экранируем спецсимволы для RegExp
        const escaped = text.replace(/[.*+?^${}()|[\]\\]/g, '\\$&');
        const regex = new RegExp(`(${escaped})`, 'gi');

        function walk(node) {
          if (node.nodeType === 3) { // текстовый узел
            const match = node.data.match(regex);
            if (match) {
              const frag = document.createDocumentFragment();
              let lastIndex = 0;
              node.data.replace(regex, (m, offset) => {
                const before = node.data.slice(lastIndex, offset);
                if (before) frag.appendChild(document.createTextNode(before));
                const mark = document.createElement('mark');
                mark.textContent = m;
                frag.appendChild(mark);
                lastIndex = offset + m.length;
              });
              const after = node.data.slice(lastIndex);
              if (after) frag.appendChild(document.createTextNode(after));
              node.parentNode.replaceChild(frag, node);
            }
          } else if (node.nodeType === 1 && node.childNodes && !['SCRIPT', 'STYLE', 'NOSCRIPT', 'MARK', 'BUTTON'].includes(node.tagName)) {
            for (let i = 0; i < node.childNodes.length; i++) {
              walk(node.childNodes[i]);
            }
          }
        }

        walk(mainContent);
      }

      // Фильтрация по тексту
      function filterContent(text) {
        clearHighlights();
        const lowerText = text.toLowerCase();
        let visibleCount = 0;

        [...mainContent.querySelectorAll('section, p, ul')].forEach(el => {
          if (el === noResults) return;
          const textContent = el.textContent.toLowerCase();
          if (textContent.includes(lowerText)) {
            el.classList.add('visible');
            visibleCount++;
          } else {
            el.classList.remove('visible');
          }
        });

        if (visibleCount === 0) {
          noResults.style.display = 'block';
        } else {
          noResults.style.display = 'none';
          highlightText(text);
        }
      }

      // Обработчики событий
      searchInput.addEventListener('input', () => {
        const val = searchInput.value.trim();
        if (val.length > 0) {
          clearButton.style.display = 'inline';
          filterContent(val);
        } else {
          clearButton.style.display = 'none';
          clearHighlights();
          [...mainContent.querySelectorAll('section, p, ul')].forEach(el => el.classList.add('visible'));
          noResults.style.display = 'none';
        }
      });

      clearButton.addEventListener('click', () => {
        searchInput.value = '';
        clearButton.style.display = 'none';
        clearHighlights();
        [...mainContent.querySelectorAll('section, p, ul')].forEach(el => el.classList.add('visible'));
        noResults.style.display = 'none';
        searchInput.focus();
      });

      // Изначально показываем все
      [...mainContent.querySelectorAll('section, p, ul')].forEach(el => el.classList.add('visible'));
    })();

    // === Копирование текста правила по кнопке 📋 ===
    (() => {
      document.querySelectorAll('.copy-btn').forEach(button => {
        button.addEventListener('click', () => {
          const h3 = button.closest('h3');
          if (!h3) return;
          // Клонируем h3 и удаляем кнопку из клона
          const clone = h3.cloneNode(true);
          const btn = clone.querySelector('.copy-btn');
          if (btn) btn.remove();
          const text = clone.textContent.trim();
          navigator.clipboard.writeText(text).then(() => {
            const originalText = button.textContent;
            button.textContent = '✔️';
            setTimeout(() => {
              button.textContent = originalText;
            }, 1500);
          }).catch(() => {
            alert('Не удалось скопировать текст');
          });
        });
      });
    })();

    // === Частицы-звёздочки внизу ===
    (() => {
      const container = document.getElementById('particles-container');
      const PARTICLE_COUNT = 30;

      function createParticle() {
        const p = document.createElement('div');
        p.classList.add('particle');

        // Случайный размер от 4 до 10px
        const size = 4 + Math.random() * 6;
        p.style.width = `${size}px`;
        p.style.height = `${size}px`;

        // Случайное начальное положение по горизонтали и вертикали (в пределах контейнера)
        p.style.left = `${Math.random() * 100}vw`;
        p.style.bottom = `${Math.random() * 40}vh`;

        // Случайная длительность анимации от 2 до 5 секунд
        p.style.animationDuration = `${2 + Math.random() * 3}s`;

        // Случайная задержка для разброса анимации
        p.style.animationDelay = `${Math.random() * 5}s`;

        container.appendChild(p);
      }

      for (let i = 0; i < PARTICLE_COUNT; i++) {
        createParticle();
      }
    })();
  </script>

</body>
</html>
