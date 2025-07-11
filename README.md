<!DOCTYPE html>
<html lang="ru">

<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Правила чата</title>
  <meta name="description" content="Правила чата: соблюдение, модерация, наказания, политика." />
  <meta name="keywords" content="чат, правила, модерация, наказания, политика" />
  <link rel="preconnect" href="https://fonts.googleapis.com" crossorigin />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&family=Roboto+Slab:wght@700&display=swap" rel="stylesheet" />
  <style>
    /* Весь ваш оригинальный CSS без изменений */
    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
      margin: 0;
      line-height: 1.6;
      color: #222;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%);
      min-height: 100vh;
      padding-top: 72px;
      box-sizing: border-box;
      display: flex;
      justify-content: center;
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
      overflow-x: hidden;
      /* --- ДОБАВЛЕНО: плавный параллакс для фона --- */
      background-attachment: fixed;
      background-position: center center;
      transition: background-position 0.3s ease;
    }

    #search-container {
      position: fixed;
      top: 0;
      left: 50%;
      transform: translateX(-50%);
      background: rgba(255 255 255 / 0.95);
      backdrop-filter: blur(12px);
      max-width: 900px;
      width: 100%;
      padding: 12px 20px;
      box-sizing: border-box;
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 9999;
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.12);
      user-select: none;
    }

    #search-input {
      width: 100%;
      max-width: 400px;
      padding: 10px 40px 10px 14px;
      font-size: 1.1em;
      border: 2px solid #4f46e5;
      border-radius: 12px;
      outline-offset: 2px;
      transition: border-color 0.3s ease;
      font-family: 'Inter', sans-serif;
      color: #2c2f48;
      background: #fefefe;
      box-shadow: 0 2px 8px rgba(79, 70, 229, 0.15);
      position: relative;
    }

    #search-input::placeholder {
      color: #a5b4fc;
    }

    #search-input:focus {
      border-color: #6366f1;
      box-shadow: 0 0 8px #6366f1;
      background: #fff;
    }

    #clear-button {
      position: absolute;
      right: 30px;
      background: transparent;
      border: none;
      cursor: pointer;
      font-size: 1.5em;
      color: #4f46e5;
      padding: 0;
      line-height: 1;
      user-select: none;
      display: none;
      transition: color 0.3s ease;
      z-index: 10;
    }

    #clear-button:hover,
    #clear-button:focus {
      color: #6366f1;
      outline: none;
    }

    main {
      background: rgba(255, 255, 255, 0.95);
      backdrop-filter: blur(12px);
      border-radius: 12px;
      box-shadow: 0 8px 30px rgba(0, 0, 0, 0.15);
      max-width: 900px;
      width: 100%;
      padding: 30px 40px;
      box-sizing: border-box;
      color: #374151;
      animation: slideUpScale 0.6s cubic-bezier(0.34, 1.56, 0.64, 1);
      user-select: text;
      outline-offset: 4px;
      /* --- ДОБАВЛЕНО: плавное появление --- */
      opacity: 0;
      animation-fill-mode: forwards;
      animation-name: fadeInMain;
      animation-duration: 0.8s;
      animation-timing-function: ease;
      animation-delay: 0.3s;
    }

    @keyframes slideUpScale {
      from {
        opacity: 0;
        transform: translateY(15px) scale(0.95);
      }

      to {
        opacity: 1;
        transform: translateY(0) scale(1);
      }
    }

    @keyframes fadeInMain {
      to {
        opacity: 1;
      }
    }

    /* Анимация градиента для h1 */
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

    h1 {
      font-family: 'Roboto Slab', serif;
      font-size: 2.4em;
      margin-bottom: 0.4em;
      display: block;
      color: transparent;
      background: linear-gradient(270deg, #ff6b6b, #fbc531, #4cd137, #00a8ff, #9c88ff, #ff6b6b);
      background-size: 1200% 1200%;
      -webkit-background-clip: text;
      background-clip: text;
      animation: rainbowGradient 10s ease infinite;
      text-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
      user-select: none;
    }

    /* Красивый текст под h1 */
    main>p:first-of-type {
      font-family: 'Inter', sans-serif;
      font-size: 1.2em;
      color: #2c2f48;
      margin-top: 0;
      margin-bottom: 2em;
      max-width: 700px;
      line-height: 1.5;
      user-select: text;
    }

    /* Убираем svg иконки из h2 и h3 */
    h2 svg,
    h3 svg {
      display: none !important;
    }

    /* Убираем flex и gap у h2 и h3 */
    h2,
    h3 {
      display: block;
      margin-top: 48px;
      margin-bottom: 14px;
      font-weight: 700;
      font-size: 1.5em;
      user-select: none;
      text-shadow: 0 0 1px rgba(79, 70, 229, 0.3);
      opacity: 0;
      transform: translateY(20px);
      transition: opacity 0.6s ease, transform 0.6s ease;
      cursor: default;
      background: linear-gradient(270deg, #7c3aed, #a78bfa);
      background-size: 600% 600%;
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      animation: rainbowGradient 15s ease infinite;
    }

    h3 {
      margin-top: 28px;
      margin-bottom: 8px;
      font-weight: 600;
      font-size: 1.15em;
      opacity: 0;
      transform: translateY(20px);
      transition: opacity 0.6s ease, transform 0.6s ease;
      user-select: none;
      cursor: default;
      background: linear-gradient(270deg, #5b21b6, #c4b5fd);
      background-size: 600% 600%;
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      animation: rainbowGradient 15s ease infinite;
    }

    h2.visible,
    h3.visible {
      opacity: 1;
      transform: translateY(0);
    }

    /* Убираем иконки из оглавления */
    nav ul li svg {
      display: none !important;
    }

    /* Иконка в заголовке оглавления с анимацией */
    .toc-header {
      display: flex;
      align-items: center;
      gap: 8px;
      font-weight: 700;
      font-size: 1.3em;
      color: #4f46e5;
      cursor: pointer;
      padding: 8px 12px;
      border-radius: 10px;
      background: linear-gradient(270deg, #c7d2fe, #a5b4fc, #c7d2fe);
      background-size: 600% 600%;
      animation: rainbowGradient 15s ease infinite;
      box-shadow:
        inset 0 1px 0 rgba(255 255 255 / 0.6),
        0 4px 8px rgba(79, 70, 229, 0.2);
      transition:
        background 0.3s ease,
        color 0.3s ease,
        box-shadow 0.3s ease;
      user-select: none;
      max-width: 100%;
      user-select: none;
      outline-offset: 4px;
    }

    .toc-header:hover,
    .toc-header:focus {
      background: linear-gradient(270deg, #a5b4fc, #6366f1, #a5b4fc);
      color: #e0e7ff;
      outline: none;
      box-shadow:
        inset 0 1px 0 rgba(255 255 255 / 0.9),
        0 6px 15px rgba(55, 48, 163, 0.5);
    }

    nav ul {
      padding-left: 0;
      list-style: none;
      margin-top: 12px;
      max-height: 500px;
      overflow: hidden;
      transition: max-height 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    }

    nav ul.collapsed {
      max-height: 0;
      margin-top: 0;
      padding-top: 0;
      padding-bottom: 0;
      overflow: hidden;
      transition: max-height 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    }

    nav ul li {
      margin-bottom: 12px;
      display: flex;
      align-items: center;
      gap: 0;
      padding-left: 0;
      border-left: 3px solid transparent;
      transition: border-color 0.3s ease;
    }

    nav ul li:hover,
    nav ul li:focus-within {
      border-left-color: #4f46e5;
      background: rgba(79, 70, 229, 0.1);
      border-radius: 6px;
    }

    nav ul li a {
      text-decoration: none;
      color: #4f46e5;
      font-weight: 600;
      font-size: 1.05em;
      transition: color 0.3s;
      flex-grow: 1;
      font-family: 'Inter', sans-serif;
      user-select: none;
      background: linear-gradient(270deg, #7c3aed, #a78bfa);
      background-size: 600% 600%;
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      animation: rainbowGradient 15s ease infinite;
    }

    nav ul li a:hover,
    nav ul li a:focus {
      color: #3730a3;
      outline: none;
      text-decoration: underline;
      background: none;
    }

    p {
      font-family: 'Inter', sans-serif;
      margin-bottom: 1.2em;
      font-size: 1.05em;
      color: #4b5563;
      letter-spacing: 0.02em;
      opacity: 0;
      transform: translateY(20px);
      transition: opacity 0.6s ease, transform 0.6s ease;
      user-select: text;
    }

    p.visible {
      opacity: 1;
      transform: translateY(0);
    }

    ul {
      font-family: 'Inter', sans-serif;
      padding-left: 1.4em;
      margin-bottom: 1.5em;
      color: #4b5563;
      font-size: 1.05em;
      letter-spacing: 0.02em;
      opacity: 0;
      transform: translateY(20px);
      transition: opacity 0.6s ease, transform 0.6s ease;
      user-select: text;
    }

    ul.visible {
      opacity: 1;
      transform: translateY(0);
    }

    ul li {
      margin-bottom: 0.8em;
    }

    strong {
      font-family: 'Inter', sans-serif;
      color: #1e293b;
      font-weight: 700;
    }

    em {
      font-family: 'Inter', sans-serif;
      color: #6b7280;
      font-style: italic;
    }

    footer {
      font-family: 'Inter', sans-serif;
      margin-top: 40px;
      font-size: 0.9em;
      color: #6b7280;
      text-align: center;
      user-select: none;
      letter-spacing: 0.02em;
    }

    mark {
      background-color: #a5b4fc;
      color: #1e293b;
      font-weight: 700;
      border-radius: 3px;
      padding: 0 2px;
      /* --- ДОБАВЛЕНО: анимация пульсации --- */
      box-shadow: 0 0 6px #7c3aed88;
      animation: pulseHighlight 2s infinite;
      transition: box-shadow 0.3s ease;
    }

    mark:hover {
      box-shadow: 0 0 12px #7c3aedcc;
    }

    @keyframes pulseHighlight {
      0%,
      100% {
        background-color: #a5b4fc;
      }

      50% {
        background-color: #c7d2fe;
      }
    }

    #no-results {
      font-family: 'Inter', sans-serif;
      text-align: center;
      color: #9ca3af;
      font-size: 1.1em;
      margin-top: 20px;
      display: none;
      user-select: none;
    }

    #back-to-top {
      position: fixed;
      bottom: 30px;
      right: 30px;
      background: #4f46e5;
      color: white;
      border: none;
      border-radius: 50%;
      width: 44px;
      height: 44px;
      cursor: pointer;
      box-shadow: 0 4px 12px rgba(79, 70, 229, 0.4);
      font-size: 24px;
      display: none;
      align-items: center;
      justify-content: center;
      z-index: 10000;
      user-select: none;
      transition: background-color 0.3s ease, box-shadow 0.3s ease, transform 0.3s ease;
      /* --- ДОБАВЛЕНО: плавное появление и анимация при наведении --- */
    }

    #back-to-top.show {
      display: flex !important;
      opacity: 1;
      transition: opacity 0.4s ease;
    }

    #back-to-top:hover,
    #back-to-top:focus {
      background-color: #6366f1;
      outline: none;
      box-shadow: 0 0 12px #6366f1;
      transform: scale(1.1);
    }

    /* Анимация иконки оглавления */
    @keyframes icon-spin {
      0% {
        transform: rotate(0deg);
      }

      50% {
        transform: rotate(15deg);
      }

      100% {
        transform: rotate(0deg);
      }
    }

    .toc-icon {
      width: 24px;
      height: 24px;
      fill: #4f46e5;
      animation: icon-spin 3s ease-in-out infinite;
      user-select: none;
      flex-shrink: 0;
    }

    @media (max-width: 700px) {
      body {
        margin: 10px;
        padding: 0;
      }

      main {
        padding: 20px 24px;
      }

      h1 {
        font-size: 1.9em;
      }

      h2 {
        font-size: 1.3em;
      }

      h3 {
        font-size: 1.1em;
      }

      nav {
        padding: 15px 18px;
      }

      #search-input {
        max-width: 100%;
        font-size: 1em;
        padding-right: 36px;
      }

      #clear-button {
        right: 10px;
      }

      #back-to-top {
        bottom: 20px;
        right: 20px;
        width: 40px;
        height: 40px;
        font-size: 20px;
      }
    }

    /* --- ДОБАВЛЕНО: кнопка переключения темы --- */
    #theme-toggle {
      position: fixed;
      top: 10px;
      right: 10px;
      font-size: 1.6em;
      background: transparent;
      border: none;
      cursor: pointer;
      color: #4f46e5;
      user-select: none;
      z-index: 10001;
      transition: color 0.3s ease;
      outline-offset: 4px;
    }

    #theme-toggle:hover,
    #theme-toggle:focus {
      color: #7c3aed;
      outline: none;
    }

    /* --- ДОБАВЛЕНО: стиль для темной темы --- */
    body.dark {
      background: #1e293b;
      color: #cbd5e1;
    }

    body.dark main {
      background: rgba(30, 41, 59, 0.85);
      color: #e0e7ff;
      box-shadow: 0 8px 30px rgba(165, 180, 252, 0.3);
    }

    body.dark p,
    body.dark ul,
    body.dark li {
      color: #cbd5e1;
    }

    body.dark mark {
      background-color: #4338ca;
      color: #e0e7ff;
      box-shadow: 0 0 8px #a5b4fccc;
    }

    body.dark #search-container {
      background: rgba(49, 46, 129, 0.9);
      box-shadow: 0 2px 8px rgba(165, 180, 252, 0.4);
    }

    body.dark #search-input {
      background: #312e81;
      color: #e0e7ff;
      border-color: #818cf8;
      box-shadow: 0 2px 8px rgba(165, 180, 252, 0.3);
    }

    body.dark #search-input::placeholder {
      color: #a5b4fc;
    }

    body.dark #clear-button {
      color: #a5b4fc;
    }

    body.dark nav ul li:hover,
    body.dark nav ul li:focus-within {
      background: rgba(165, 180, 252, 0.15);
      border-left-color: #a5b4fc;
    }

    body.dark nav ul li a {
      background: linear-gradient(270deg, #818cf8, #a5b4fc);
      background-size: 600% 600%;
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      animation: rainbowGradient 15s ease infinite;
    }

    body.dark nav ul li a:hover,
    body.dark nav ul li a:focus {
      color: #c7d2fe;
      background: none;
      text-decoration: underline;
    }

    body.dark #back-to-top {
      background: #818cf8;
      box-shadow: 0 4px 12px rgba(129, 140, 248, 0.6);
    }

    body.dark #back-to-top:hover,
    body.dark #back-to-top:focus {
      background-color: #a5b4fc;
      box-shadow: 0 0 12px #a5b4fc;
    }
  </style>
</head>

<body>
  <div id="search-container">
    <input type="search" id="search-input" aria-label="Поиск по правилам" placeholder="Поиск по правилам..." autocomplete="off" spellcheck="false" />
    <button id="clear-button" aria-label="Очистить поиск" title="Очистить поиск">&times;</button>
  </div>

  <!-- --- ДОБАВЛЕНО: кнопка переключения темы --- -->
  <button id="theme-toggle" aria-label="Переключить тему">🌓</button>

  <main id="main-content" tabindex="-1">
    <h1>Правила чата</h1>

    <p>Каждый вошедший пользователь добровольно принимает правила нашего чата и обязуется их соблюдать.</p>

    <nav aria-label="Оглавление">
      <div class="toc-header" role="button" tabindex="0" aria-expanded="true" aria-controls="toc-list" id="toc-toggle">
        <svg class="toc-icon" viewBox="0 0 24 24" aria-hidden="true" focusable="false">
          <path d="M4 6h16M4 12h16M4 18h16" stroke="currentColor" stroke-width="2" stroke-linecap="round" />
        </svg>
        Содержание
      </div>
      <ul id="toc-list" tabindex="-1">
        <li>
          <a href="#ne-zhelatelno">Не желательно</a>
        </li>
        <li>
          <a href="#zapreshchaetsya">Запрещается</a>
        </li>
        <li>
          <a href="#dopolneniya-po-moderatoram">Важные дополнения по работе модераторов и контролю качества их действий</a>
        </li>
        <li>
          <a href="#nakazaniya">Наказания</a>
        </li>
        <li>
          <a href="#politika">Политика модераторов</a>
        </li>
      </ul>
    </nav>

    <section id="samoe-vazhnoe">
      <h2>Самое важное</h2>
      <p><strong>Каждый участник чата обязан уважать других, соблюдать правила и поддерживать дружелюбную атмосферу.</strong></p>
      <p>Нарушение этого принципа ведёт к предупреждениям и, при повторении — к более строгим мерам вплоть до бана.</p>
    </section>

    <section id="ne-zhelatelno">
      <h2>Не желательно</h2>

      <h3>1. Использование большого количества ненормативной лексики <button class="copy-btn" title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Предупреждение</p>
      <p><strong>Пояснение:</strong> Мы понимаем, что иногда эмоции берут верх, но старайтесь не злоупотреблять матом. Если вы используете ненормативную лексику редко и без оскорблений — это не проблема.</p>
      <p><strong>Пример:</strong> «Вот это классно!» — нормально; «Ты полный [нецензурное слово]» — повод для предупреждения.</p>

      <h3>2. Рекламировать другие группы/каналы <button class="copy-btn" title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Предупреждение</p>
      <p><strong>Пояснение:</strong> Реклама чужих ресурсов без согласия администрации мешает общению. Если хотите поделиться полезным каналом — сначала свяжитесь с администратором (@lia_os).</p>
      <p><strong>Пример:</strong> «Подпишитесь на мой канал!» — запрещено без разрешения.</p>

      <h3>3. Начинать ссоры, старайтесь поддерживать комфорт в чате <button class="copy-btn" title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Предупреждение или мут (в зависимости от интенсивности)</p>
      <p><strong>Пояснение:</strong> Споры бывают, но если они переходят в оскорбления или мешают другим — сначала предупредим, а при повторе временно ограничим возможность писать (мут).</p>
      <p><strong>Пример:</strong> «Ты неправ!» — нормально, «Ты идиот!» — повод для наказания.</p>

      <!-- Пункт 4 исключён согласно вашему запросу -->

      <h3>5. Оскорбление персонажей, уважайте чувства и вкусы других <button class="copy-btn" title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Предупреждение или мут</p>
      <p><strong>Пояснение:</strong> Критика — нормально, а личные оскорбления — нет.</p>
      <p><strong>Пример:</strong> «Мне не нравится этот персонаж» — допустимо, «Этот персонаж — дурак» — нарушение.</p>

      <h3>6. Пересылка личных сообщений другого человека в беседу <button class="copy-btn" title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Предупреждение</p>
      <p><strong>Пояснение:</strong> Личные сообщения другого участника нельзя пересылать в общий чат без согласия обеих сторон. Если оба участника переписки являются членами группы, часть переписки пересылается только с одобрения обеих сторон. Это помогает сохранять приватность и уважать личное пространство.</p>
      <p><strong>Пример:</strong> Пересылать скриншоты или сообщения из личных диалогов без разрешения — запрещено.</p>
    </section>

    <section id="zapreshchaetsya">
      <h2>Запрещается</h2>

      <h3>1. Обсуждение политики и публикация любого контента, связанного с политикой <button class="copy-btn" title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Бан</p>
      <p><strong>Пояснение:</strong> Политика часто вызывает конфликты и разделение. Чтобы сохранить дружелюбную атмосферу, такие темы запрещены.</p>
      <p><strong>Пример:</strong> обсуждение выборов, политических лидеров и т.п.</p>

      <h3>2. Оскорбления <button class="copy-btn" title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Предупреждение, при повторе — мут или бан</p>
      <p><strong>Пояснение:</strong> Шутки — хорошо, но если кому-то неприятно — защитим его.</p>
      <p><strong>Пример:</strong> «Ты такой смешной дурачок» — шутка, но если это обидело — последует предупреждение.</p>

      <h3>3. Публикация порнографического и околопорнографического контента <button class="copy-btn" title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Бан</p>
      <p><strong>Пояснение:</strong> Нарушает правила приличия и закон.</p>
      <p><strong>Пример:</strong> откровенные фото, видео или ссылки.</p>

      <h3>4. Публикация треш-контента (стикеры/видео/гиф с расчлененкой и тому подобное) <button class="copy-btn" title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Бан</p>
      <p><strong>Пояснение:</strong> Шокирующие материалы могут травмировать участников.</p>
      <p><strong>Пример:</strong> видео с насилием или жестокостью.</p>

      <h3>5. Поднятие тем, нарушающих законы РФ (экстремизм, терроризм, пропаганда наркотиков, оскорбление чувств верующих и др.) <button class="copy-btn" title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Бан</p>
      <p><strong>Пояснение:</strong> Такие темы запрещены законом и чатом.</p>
      <p><strong>Пример:</strong> призывы к насилию, обсуждение запрещённых веществ.</p>

      <h3>6. Спам / флуд (часто повторяющиеся сообщения, сообщения без смысла) <button class="copy-btn" title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Мут</p>
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

    <div id="no-results" role="alert" aria-live="polite">Ничего не найдено.</div>

    <footer>
      <p>Если у вас есть вопросы или нужна помощь — обращайтесь к администрации (<strong>@lia_os</strong>).</p>
    </footer>
  </main>

  <button id="back-to-top" aria-label="Наверх" title="Наверх" type="button">&#8679;</button>

  <script>
    (function () {
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

    document.addEventListener('DOMContentLoaded', () => {
      const elements = document.querySelectorAll('h2, h3, p, ul');
      const observer = new IntersectionObserver((entries, obs) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            entry.target.classList.add('visible');
            obs.unobserve(entry.target);
          }
        });
      }, {
        threshold: 0.15
      });

      elements.forEach(el => {
        observer.observe(el);
      });
    });

    document.addEventListener('DOMContentLoaded', () => {
      const searchInput = document.getElementById('search-input');
      const mainContent = document.getElementById('main-content');
      const noResults = document.getElementById('no-results');
      const clearButton = document.getElementById('clear-button');

      function clearHighlights(element) {
        const marks = element.querySelectorAll('mark');
        marks.forEach(mark => {
          const parent = mark.parentNode;
          parent.replaceChild(document.createTextNode(mark.textContent), mark);
          parent.normalize();
        });
      }

      function highlightText(node, query) {
        if (node.nodeType === 3) {
          const val = node.nodeValue;
          const valLower = val.toLowerCase();
          const queryLower = query.toLowerCase();
          let index = valLower.indexOf(queryLower);
          if (index >= 0) {
            const frag = document.createDocumentFragment();
            let lastIndex = 0;
            while (index >= 0) {
              if (index > lastIndex) {
                frag.appendChild(document.createTextNode(val.substring(lastIndex, index)));
              }
              const mark = document.createElement('mark');
              mark.textContent = val.substring(index, index + query.length);
              frag.appendChild(mark);
              lastIndex = index + query.length;
              index = valLower.indexOf(queryLower, lastIndex);
            }
            if (lastIndex < val.length) {
              frag.appendChild(document.createTextNode(val.substring(lastIndex)));
            }
            node.parentNode.replaceChild(frag, node);
            return 1;
          }
        } else if (node.nodeType === 1 && node.childNodes && !['SCRIPT', 'STYLE', 'MARK'].includes(node.tagName)) {
          for (let i = 0; i < node.childNodes.length; i++) {
            i += highlightText(node.childNodes[i], query);
          }
        }
        return 0;
      }

      function showAll() {
        const sections = mainContent.querySelectorAll('section');
        sections.forEach(section => {
          section.style.display = '';
        });
        const introParagraphs = Array.from(mainContent.children).filter(el =>
          el.tagName === 'P' && !el.closest('section')
        );
        introParagraphs.forEach(p => {
          p.style.display = '';
        });
        noResults.style.display = 'none';
      }

      function doSearch() {
        const query = searchInput.value.trim();
        clearHighlights(mainContent);

        if (query.length < 2) {
          showAll();
          clearButton.style.display = query.length > 0 ? 'inline' : 'none';
          noResults.style.display = 'none';
          return;
        }

        clearButton.style.display = 'inline';

        const sections = mainContent.querySelectorAll('section');
        let anyMatch = false;

        sections.forEach(section => {
          const text = section.textContent.toLowerCase();
          if (text.includes(query.toLowerCase())) {
            highlightText(section, query);
            section.style.display = '';
            anyMatch = true;
          } else {
            section.style.display = 'none';
          }
        });

        const introParagraphs = Array.from(mainContent.children).filter(el =>
          el.tagName === 'P' && !el.closest('section')
        );
        introParagraphs.forEach(p => {
          const text = p.textContent.toLowerCase();
          if (text.includes(query.toLowerCase())) {
            highlightText(p, query);
            p.style.display = '';
            anyMatch = true;
          } else {
            p.style.display = 'none';
          }
        });

        noResults.style.display = anyMatch ? 'none' : 'block';
      }

      let debounceTimeout;
      searchInput.addEventListener('input', () => {
        clearTimeout(debounceTimeout);
        debounceTimeout = setTimeout(doSearch, 250);
      });

      clearButton.addEventListener('click', () => {
        searchInput.value = '';
        clearButton.style.display = 'none';
        clearHighlights(mainContent);
        showAll();
        searchInput.focus();
      });

      clearButton.style.display = 'none';
    });

    // --- ДОБАВЛЕНО: кнопки копирования правил ---
    document.addEventListener('DOMContentLoaded', () => {
      document.querySelectorAll('.copy-btn').forEach(btn => {
        btn.addEventListener('click', () => {
          // Копируем текст заголовка (без кнопки)
          const h3 = btn.parentElement;
          if (!h3) return;
          // Получаем текст без кнопки
          const text = Array.from(h3.childNodes)
            .filter(n => n.nodeType === 3) // текстовые узлы
            .map(n => n.textContent.trim())
            .join(' ');
          if (!text) return;
          navigator.clipboard.writeText(text).then(() => {
            const original = btn.textContent;
            btn.textContent = '✔️';
            setTimeout(() => {
              btn.textContent = original;
            }, 1500);
          }).catch(() => {
            alert('Не удалось скопировать правило.');
          });
        });
      });
    });

    // --- ДОБАВЛЕНО: плавный параллакс фон при прокрутке ---
    window.addEventListener('scroll', () => {
      const scroll = window.pageYOffset || document.documentElement.scrollTop;
      document.body.style.backgroundPosition = `center ${-scroll * 0.3}px`;
    });

    // --- ДОБАВЛЕНО: подсветка активного пункта меню при скролле ---
    document.addEventListener('DOMContentLoaded', () => {
      const sections = document.querySelectorAll('section[id]');
      const tocLinks = document.querySelectorAll('nav ul li a');

      function onScroll() {
        let current = '';
        const scrollY = window.pageYOffset || document.documentElement.scrollTop;
        sections.forEach(section => {
          const sectionTop = section.offsetTop - 80;
          if (scrollY >= sectionTop) {
            current = section.id;
          }
        });
        tocLinks.forEach(link => {
          link.classList.remove('active');
          if (link.getAttribute('href') === '#' + current) {
            link.classList.add('active');
          }
        });
      }
      window.addEventListener('scroll', onScroll);
      onScroll();
    });

    // --- ДОБАВЛЕНО: плавный скролл по меню (уже есть, но дублирую для безопасности) ---
    document.addEventListener('DOMContentLoaded', () => {
      document.querySelectorAll('nav ul li a').forEach(anchor => {
        anchor.addEventListener('click', e => {
          e.preventDefault();
          const targetId = anchor.getAttribute('href').substring(1);
          const target = document.getElementById(targetId);
          if (!target) return;
          window.scrollTo({
            top: target.getBoundingClientRect().top + window.pageYOffset - 60,
            behavior: 'smooth'
          });
        });
      });
    });

    // --- ДОБАВЛЕНО: кнопка "Наверх" плавно появляется и работает ---
    document.addEventListener('DOMContentLoaded', () => {
      const backToTopBtn = document.getElementById('back-to-top');

      window.addEventListener('scroll', () => {
        if (window.pageYOffset > 300) {
          backToTopBtn.classList.add('show');
        } else {
          backToTopBtn.classList.remove('show');
        }
      });

      backToTopBtn.addEventListener('click', () => {
        window.scrollTo({
          top: 0,
          behavior: 'smooth'
        });
        document.getElementById('search-input').focus();
      });
    });

    // --- ДОБАВЛЕНО: переключение темной/светлой темы ---
    document.addEventListener('DOMContentLoaded', () => {
      const themeToggle = document.getElementById('theme-toggle');

      function setTheme(dark) {
        if (dark) {
          document.body.classList.add('dark');
          localStorage.setItem('darkTheme', 'true');
        } else {
          document.body.classList.remove('dark');
          localStorage.setItem('darkTheme', 'false');
        }
      }

      themeToggle.addEventListener('click', () => {
        setTheme(!document.body.classList.contains('dark'));
      });

      // Автовыбор темы из localStorage
      if (localStorage.getItem('darkTheme') === 'true') {
        setTheme(true);
      }
    });
  </script>
</body>

</html>
