<html lang="ru">

<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Правила чата</title>
  <meta name="description" content="Правила чата: соблюдение, модерация, наказания, политика." />
  <meta name="keywords" content="чат, правила, модерация, наказания, политика" />
  <link rel="preconnect" href="https://fonts.googleapis.com" crossorigin />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link
    href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&family=Roboto+Slab:wght@700&display=swap"
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
      color: #222;
      min-height: 100vh;
      padding-top: 100px;
      box-sizing: border-box;
      display: flex;
      justify-content: center;
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
      overflow-x: hidden;

      /* Новый фон: спокойный голубовато-зеленый с легкой текстурой */
      background-color: #a7c7c7;
      background-image:
        url("https://www.transparenttextures.com/patterns/asfalt-light.png");
      background-repeat: repeat;
      background-size: auto;

      position: relative;
      z-index: 0;
    }

    /* Улучшенные волны — выше, ярче, контрастнее и быстрее */
    body::before,
    body::after {
      content: "";
      position: fixed;
      left: 0;
      width: 100vw;
      height: 280px; /* увеличена высота */
      background-repeat: repeat-x;
      background-size: 2200px 280px;
      bottom: 0;
      z-index: 0;
      pointer-events: none;
      opacity: 0.6; /* увеличена непрозрачность */
      animation-timing-function: linear;
      background-image: url("data:image/svg+xml,%3csvg width='2200' height='280' viewBox='0 0 2200 280' fill='none' xmlns='http://www.w3.org/2000/svg'%3e%3cpath fill='%23ffffff' fill-opacity='0.3' d='M0 140c110-140 220 140 330 140s220-280 330-280 220 280 330 280 220-280 330-280 220 280 330 280 220-280 330-280v140H0z'/%3e%3c/svg%3e");
    }

    body::before {
      bottom: 0;
      opacity: 0.6;
      animation-name: waveMove1;
      animation-duration: 6s; /* быстрее */
      animation-iteration-count: infinite;
    }

    body::after {
      bottom: 40px; /* чуть выше */
      opacity: 0.45;
      animation-name: waveMove2;
      animation-duration: 4s; /* быстрее */
      animation-iteration-count: infinite;
    }

    @keyframes waveMove1 {
      0% {
        background-position-x: 0;
      }

      100% {
        background-position-x: 2200px;
      }
    }

    @keyframes waveMove2 {
      0% {
        background-position-x: 0;
      }

      100% {
        background-position-x: -2200px;
      }
    }

    /* === Поиск === */
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
      z-index: 10000;
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

    /* === Основной контент === */
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

    main>p:first-of-type {
      font-family: 'Inter', sans-serif;
      font-size: 1.2em;
      color: #2c2f48;
      margin-top: 0;
      margin-bottom: 2em;
      max-width: 700px;
      line-height: 1.5;
      user-select: text;
      text-align: center;
    }

    h2 svg,
    h3 svg {
      display: none !important;
    }

    nav[aria-label="Оглавление"] {
      margin-bottom: 2.5em;
      border-radius: 14px;
      background: linear-gradient(135deg, #7c3aed 0%, #a78bfa 100%);
      box-shadow: 0 8px 20px rgba(124, 58, 237, 0.4);
      max-width: 900px;
      user-select: none;
      font-family: 'Inter', sans-serif;
      position: relative;
      z-index: 10;
    }

    .toc-header {
      display: flex;
      align-items: center;
      gap: 10px;
      font-weight: 700;
      font-size: 1.5em;
      color: #fff;
      cursor: pointer;
      padding: 14px 24px;
      border-radius: 14px 14px 0 0;
      background: linear-gradient(90deg, #d8b4fe, #7c3aed);
      box-shadow: inset 0 3px 6px rgba(255 255 255 / 0.25);
      transition: background 0.3s ease;
      user-select: none;
    }

    .toc-header:hover,
    .toc-header:focus {
      background: linear-gradient(90deg, #a78bfa, #6d28d9);
      outline: none;
      box-shadow:
        inset 0 3px 8px rgba(255 255 255 / 0.4),
        0 0 12px #a78bfaaa;
    }

    .toc-icon {
      width: 28px;
      height: 28px;
      stroke: #f3e8ff;
      animation: icon-spin 4s ease-in-out infinite;
      flex-shrink: 0;
      user-select: none;
    }

    nav ul.toc-list {
      margin: 0;
      padding: 0;
      list-style: none;
      max-height: 500px;
      overflow-y: auto;
      background: #faf5ff;
      border-radius: 0 0 14px 14px;
      box-shadow: inset 0 0 12px #a78bfa88;
      transition: max-height 0.4s cubic-bezier(0.4, 0, 0.2, 1);
      position: relative;
      z-index: 10;
    }

    nav ul.toc-list.collapsed {
      max-height: 0;
      padding: 0;
      overflow: hidden;
    }

    nav ul.toc-list li {
      border-bottom: 1.5px dotted #a78bfa;
      transition: background-color 0.25s ease;
    }

    nav ul.toc-list li:last-child {
      border-bottom: none;
    }

    nav ul.toc-list li a {
      display: block;
      padding: 14px 28px;
      font-weight: 600;
      font-size: 1.1em;
      color: #5b21b6;
      background: linear-gradient(270deg, #7c3aed, #a78bfa);
      background-size: 600% 600%;
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      animation: rainbowGradient 15s ease infinite;
      text-decoration: none;
      user-select: none;
      border-radius: 0 0 0 0;
      transition: background-color 0.3s ease, color 0.3s ease;
      text-align: left;
    }

    nav ul.toc-list li a:hover,
    nav ul.toc-list li a:focus {
      color: #4c1d95;
      background: none;
      text-decoration: underline;
      outline: none;
      background-color: #ede9fe;
      user-select: text;
    }

    nav ul.toc-list li a.active {
      background-color: #c4b5fd;
      color: #4c1d95 !important;
      font-weight: 700;
      box-shadow: 0 0 10px #a78bfacc;
      border-radius: 10px 0 0 10px;
      user-select: text;
    }

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

    section+section {
      border-top: 3px dashed;
      border-image-slice: 1;
      border-image-source: linear-gradient(to right,
        #ff6b6b,
        #fbc531,
        #4cd137,
        #00a8ff,
        #9c88ff);
      margin-top: 48px;
      padding-top: 32px;
    }

    h2:not(:first-of-type) {
      border-top: 3px dashed;
      border-image-slice: 1;
      border-image-source: linear-gradient(to right,
        #f093fb,
        #6a11cb,
        #2575fc);
      padding-top: 24px;
      margin-top: 48px;
      text-align: center;
      user-select: none;
    }

    h3:not(:first-of-type) {
      border-top: 2px dotted;
      border-image-slice: 1;
      border-image-source: linear-gradient(to right,
        #fcd34d,
        #f97316);
      padding-top: 12px;
      margin-top: 28px;
      user-select: none;
      text-align: left;
    }

    ul li:not(:last-child) {
      border-bottom: 1.5px dotted;
      border-image-slice: 1;
      border-image-source: linear-gradient(to right,
        #34d399,
        #3b82f6);
      padding-bottom: 6px;
      margin-bottom: 6px;
    }

    h2,
    h3 {
      font-weight: 700;
      user-select: none;
      cursor: default;
      background-clip: text;
      -webkit-background-clip: text;
      color: transparent;
      animation: rainbowGradient 15s ease infinite;
      text-shadow: 0 0 2px rgba(124, 58, 237, 0.3);
    }

    h2 {
      font-size: 1.6em;
      background-image: linear-gradient(270deg, #7c3aed, #a78bfa);
    }

    h3 {
      font-size: 1.25em;
      background-image: linear-gradient(270deg, #5b21b6, #c4b5fd);
    }

    p,
    ul {
      font-family: 'Inter', sans-serif;
      font-size: 1.05em;
      color: #4b5563;
      letter-spacing: 0.02em;
      opacity: 0;
      transform: translateY(20px);
      transition: opacity 0.6s ease, transform 0.6s ease;
      user-select: text;
      text-align: left;
    }

    p.visible,
    ul.visible {
      opacity: 1;
      transform: translateY(0);
    }

    ul {
      padding-left: 1.4em;
      margin-bottom: 1.5em;
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
      position: relative;
      z-index: 10;
    }

    mark {
      background-color: #a5b4fc;
      color: #1e293b;
      font-weight: 700;
      border-radius: 3px;
      padding: 0 2px;
      box-shadow: none;
      animation: none;
      transition: background-color 0.3s ease;
    }

    mark:hover {
      background-color: #c7d2fe;
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

      nav[aria-label="Оглавление"] {
        margin-bottom: 1.8em;
      }

      nav ul.toc-list li a {
        padding: 10px 20px;
        font-size: 1em;
      }

      #search-input {
        max-width: 100%;
        font-size: 1em;
        padding-right: 36px;
      }

      #clear-button {
        right: 10px;
      }
    }

    /* === Частицы === */
    #particles-container {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      pointer-events: none;
      z-index: 20; /* Поверх текста и волн */
      overflow: visible;
      will-change: transform;
      background: transparent;
    }

    .particle {
      position: absolute;
      will-change: transform, left, top, opacity;
      user-select: none;
      pointer-events: none;
      background-size: contain;
      background-repeat: no-repeat;
      filter:
        drop-shadow(0 2px 6px rgba(0, 0, 0, 0.3));
      transition: opacity 0.3s ease;
      backface-visibility: hidden;
      transform-style: preserve-3d;
      opacity: 0.6;
      mix-blend-mode: screen;
      border-radius: 50%; /* для столкновений проще считать круги */
      /* чуть больше иконки */
      width: 36px !important;
      height: 36px !important;
    }

    /* Twitch иконка */
    .twitch {
      background-image: url('data:image/svg+xml;utf8,<svg fill="%237c3aed" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M2 2v20l4-4h6l6 4V2H2zm14 12h-2v-4h2v4zm4-8H6v10H4v-12h16v10z"/></svg>');
      filter:
        drop-shadow(0 2px 6px rgba(124, 58, 237, 0.6))
        drop-shadow(0 0 10px rgba(124, 58, 237, 0.4));
    }

    /* YouTube иконка */
    .youtube {
      background-image: url('data:image/svg+xml;utf8,<svg fill="%23ff0000" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M10 15l5.19-3L10 9v6zM21.8 7.2c-.2-.8-.8-1.4-1.6-1.6C18.4 5 12 5 12 5s-6.4 0-8.2.6c-.8.2-1.4.8-1.6 1.6C2 9 2 12 2 12s0 3 .2 4.8c.2.8.8 1.4 1.6 1.6C5.6 19 12 19 12 19s6.4 0 8.2-.6c.8-.2 1.4-.8 1.6-1.6.2-1.8.2-4.8.2-4.8s0-3-.2-4.8z"/></svg>');
      filter:
        drop-shadow(0 2px 6px rgba(255, 0, 0, 0.6))
        drop-shadow(0 0 10px rgba(255, 0, 0, 0.4));
    }

    /* Heart (сердце) */
    .heart {
      filter:
        drop-shadow(0 2px 6px rgba(224, 36, 94, 0.6))
        drop-shadow(0 0 10px rgba(224, 36, 94, 0.4));
      width: 34px !important;
      height: 34px !important;
    }

    /* Like (палец вверх) */
    .like {
      filter:
        drop-shadow(0 2px 6px rgba(34, 197, 94, 0.6))
        drop-shadow(0 0 10px rgba(34, 197, 94, 0.4));
      width: 34px !important;
      height: 34px !important;
    }

    /* Dislike (палец вниз) */
    .dislike {
      filter:
        drop-shadow(0 2px 6px rgba(239, 68, 68, 0.6))
        drop-shadow(0 0 10px rgba(239, 68, 68, 0.4));
      width: 34px !important;
      height: 34px !important;
    }

    /* Размеры частиц адаптивно */
    @media (max-width: 768px) {
      .particle {
        width: 28px !important;
        height: 28px !important;
      }

      .twitch,
      .youtube {
        width: 30px !important;
        height: 30px !important;
      }

      .heart,
      .like,
      .dislike {
        width: 26px !important;
        height: 26px !important;
      }
    }

    @media (max-width: 400px) {
      .particle {
        width: 22px !important;
        height: 22px !important;
      }

      .twitch,
      .youtube {
        width: 24px !important;
        height: 24px !important;
      }

      .heart,
      .like,
      .dislike {
        width: 20px !important;
        height: 20px !important;
      }
    }
  </style>
</head>

<body>
  <div id="search-container">
    <input type="search" id="search-input" aria-label="Поиск по правилам" placeholder="Поиск по правилам..."
      autocomplete="off" spellcheck="false" />
    <button id="clear-button" aria-label="Очистить поиск" title="Очистить поиск">&times;</button>
  </div>

  <main id="main-content" tabindex="-1">
    <h1>Правила чата</h1>

    <p>Каждый вошедший пользователь добровольно принимает правила нашего чата и обязуется их соблюдать.</p>

    <nav aria-label="Оглавление">
      <div class="toc-header" role="button" tabindex="0" aria-expanded="true" aria-controls="toc-list" id="toc-toggle">
        <svg class="toc-icon" viewBox="0 0 24 24" aria-hidden="true" focusable="false" width="28" height="28"
          fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <line x1="3" y1="6" x2="21" y2="6"></line>
          <line x1="3" y1="12" x2="21" y2="12"></line>
          <line x1="3" y1="18" x2="21" y2="18"></line>
        </svg>
        Содержание
      </div>
      <ul id="toc-list" tabindex="-1" class="toc-list">
        <li><a href="#ne-zhelatelno">Не желательно</a></li>
        <li><a href="#zapreshchaetsya">Запрещается</a></li>
        <li><a href="#dopolneniya-po-moderatoram">Важные дополнения по работе модераторов и контролю качества их
            действий</a></li>
        <li><a href="#nakazaniya">Наказания</a></li>
        <li><a href="#politika">Политика модераторов</a></li>
      </ul>
    </nav>

    <section id="samoe-vazhnoe">
      <h2>Самое важное</h2>
      <p><strong>Каждый участник чата обязан уважать других, соблюдать правила и поддерживать дружелюбную атмосферу.</strong>
      </p>
      <p>Нарушение этого принципа ведёт к предупреждениям и, при повторении — к более строгим мерам вплоть до бана.</p>
    </section>

    <section id="ne-zhelatelno">
      <h2>Не желательно</h2>

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

      <h3>4. Публикация треш-контента (стикеры/видео/гиф с расчлененкой и тому подобное) <button class="copy-btn"
          title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Бан</p>
      <p><strong>Пояснение:</strong> Шокирующие материалы могут травмировать участников.</p>
      <p><strong>Пример:</strong> видео с насилием или жестокостью.</p>

      <h3>5. Поднятие тем, нарушающих законы РФ (экстремизм, терроризм, пропаганда наркотиков, оскорбление чувств верующих
        и др.) <button class="copy-btn" title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Бан</p>
      <p><strong>Пояснение:</strong> Такие темы запрещены законом и чатом.</p>
      <p><strong>Пример:</strong> призывы к насилию, обсуждение запрещённых веществ.</p>

      <h3>6. Спам / флуд (часто повторяющиеся сообщения, сообщения без смысла) <button class="copy-btn"
          title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Мут</p>
      <p><strong>Пояснение:</strong> Чтобы чат был удобен для всех, не стоит засорять его бессмысленными сообщениями.</p>
      <p><strong>Пример:</strong> повторять одну и ту же фразу много раз подряд.</p>

      <h3>7. Публичное осуждение действий администрации / провокация администрации типа «ну давай бань меня» <button
          class="copy-btn" title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Предупреждение или мут</p>
      <p><strong>Пояснение:</strong> Если есть вопросы к администрации — лучше написать в личку, а не провоцировать конфликт
        в общем чате.</p>

      <h3>8. Любая дискриминация по расовому/национальному/половому/религиозному признаку <button class="copy-btn"
          title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Бан</p>
      <p><strong>Пояснение:</strong> Мы за равенство и уважение ко всем.</p>
      <p><strong>Пример:</strong> оскорбления по национальному признаку недопустимы.</p>

      <h3>9. Просьбы перейти по ссылкам/зарегистрироваться на вредоносном сайте <button class="copy-btn"
          title="Скопировать правило">📋</button></h3>
      <p><strong>Наказание:</strong> Бан</p>
      <p><strong>Пояснение:</strong> Безопасность участников — наш приоритет.</p>
      <p><strong>Пример:</strong> ссылки на мошеннические сайты.</p>
    </section>

    <section id="dopolneniya-po-moderatoram">
      <h2>Важные дополнения по работе модераторов и контролю качества их действий</h2>

      <h3>10. Модераторы обязаны действовать в соответствии с правилами чата и не использовать свои полномочия в личных
        интересах <button class="copy-btn" title="Скопировать правило">📋</button></h3>
      <p><strong>Пояснение:</strong> Если заметили нарушение или злоупотребление полномочиями (например, необоснованно мутит
        или банит, игнорирует правила), обратитесь к высшим администраторам или создателю чата (@lia_os). Жалобы
        рассматриваются, и мы защищаем от несправедливого обращения.</p>

      <h3>11. Перед применением наказания модератор должен дать словесное предупреждение участнику <button class="copy-btn"
          title="Скопировать правило">📋</button></h3>
      <p><strong>Пояснение:</strong> Если поведение начинает нарушать правила или мешать комфорту, модератор предупреждает:
        «Пожалуйста, прекратите, иначе последуют меры». Если предупреждение игнорируется — применяется наказание (мут, бан
        и т.п.). Это помогает избежать конфликтов и даёт шанс исправиться.</p>
    </section>

    <section id="nakazaniya">
      <h2>Наказания</h2>
      <ul>
        <li><strong>Предупреждение</strong> — первое и мягкое наказание. Сообщаем, что поведение не соответствует правилам с
          объяснением.</li>
        <li><strong>Мут</strong> — временное ограничение возможности писать (несколько минут или часов). Используется при
          повторных нарушениях или серьёзных проступках. Перед мутом обязательно словесное предупреждение.</li>
        <li><strong>Бан</strong> — удаление из чата с запретом на повторный вход. За серьёзные или неоднократные нарушения.
        </li>
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

    <section id="signature" aria-label="Подпись автора">
      <p>by Везунчик</p>
    </section>

    <footer>
      <p>Если у вас есть вопросы или нужна помощь — обращайтесь к администрации (<strong>@lia_os</strong>).</p>
    </footer>
  </main>

  <!-- Контейнер для частиц поверх всего -->
  <div id="particles-container" aria-hidden="true"></div>

  <script>
    // === Оглавление: раскрытие/скрытие ===
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

    // === Появление элементов с анимацией при скролле ===
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

    // === Поиск по тексту с подсветкой ===
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

    // === Кнопки копирования правил ===
    document.addEventListener('DOMContentLoaded', () => {
      document.querySelectorAll('.copy-btn').forEach(btn => {
        btn.addEventListener('click', () => {
          const h3 = btn.parentElement;
          if (!h3) return;
          const text = Array.from(h3.childNodes)
            .filter(n => n.nodeType === 3)
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

    // === Подсветка активного пункта меню при скролле ===
    document.addEventListener('DOMContentLoaded', () => {
      const sections = document.querySelectorAll('section[id]');
      const tocLinks = document.querySelectorAll('nav ul.toc-list li a');

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

    // === Плавный скролл по меню ===
    document.addEventListener('DOMContentLoaded', () => {
      document.querySelectorAll('nav ul.toc-list li a').forEach(anchor => {
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

    // === Улучшенный скрипт частиц с столкновениями и высокой скоростью ===
    document.addEventListener('DOMContentLoaded', () => {
      const container = document.getElementById('particles-container');
      const types = ['twitch', 'youtube', 'heart', 'like', 'dislike'];

      const maxParticles = 40; // для производительности

      function random(min, max) {
        return Math.random() * (max - min) + min;
      }

      // Конвертация px в vw/vh
      function pxToVw(px) {
        return (px / window.innerWidth) * 100;
      }

      function pxToVh(px) {
        return (px / window.innerHeight) * 100;
      }

      // Класс частицы
      class Particle {
        constructor(type, index, total) {
          this.el = document.createElement('div');
          this.el.classList.add('particle', type);

          const colCount = Math.ceil(Math.sqrt(total));
          const rowCount = Math.ceil(total / colCount);

          const col = index % colCount;
          const row = Math.floor(index / colCount);

          const cellWidth = 100 / colCount;
          const cellHeight = 100 / rowCount;

          this.baseX = cellWidth * col + random(5, cellWidth - 5);
          this.baseY = cellHeight * row + random(5, cellHeight - 5);

          this.posX = this.baseX;
          this.posY = this.baseY;

          // Размеры частицы в px
          let baseSize = 36;
          if (window.innerWidth <= 400) baseSize = 22;
          else if (window.innerWidth <= 768) baseSize = 28;
          if (type === 'twitch' || type === 'youtube') baseSize += 4;
          if (['heart', 'like', 'dislike'].includes(type)) baseSize -= 2;

          this.sizePx = random(baseSize * 0.85, baseSize * 1.15);
          this.radiusVw = pxToVw(this.sizePx) / 2;

          this.el.style.width = `${this.sizePx}px`;
          this.el.style.height = `${this.sizePx}px`;
          this.el.style.opacity = (0.4 + Math.random() * 0.3).toFixed(2);

          // Начальная скорость (vw/vh в кадр)
          this.velocityX = random(-0.18, 0.18); // увеличена скорость в 2 раза
          this.velocityY = random(-0.15, 0.15);

          this.swayPhase = Math.random() * Math.PI * 2;
          this.opacityPhase = Math.random() * Math.PI * 2;
          this.rotation = random(0, 360);
          this.rotationSpeed = random(-4, 4); // ускорено вращение

          this.maxOffset = 14; // увеличено смещение (vw)

          container.appendChild(this.el);
        }

        update() {
          // Возврат к базовой позиции с небольшой силой
          const dxBase = this.baseX - this.posX;
          const dyBase = this.baseY - this.posY;
          this.velocityX += dxBase * 0.008;
          this.velocityY += dyBase * 0.008;

          // Ограничение скорости
          this.velocityX = Math.max(Math.min(this.velocityX, 0.2), -0.2);
          this.velocityY = Math.max(Math.min(this.velocityY, 0.18), -0.18);

          this.posX += this.velocityX;
          this.posY += this.velocityY;

          // Ограничение смещения с отскоком
          const offsetX = this.posX - this.baseX;
          const offsetY = this.posY - this.baseY;

          if (offsetX > this.maxOffset) {
            this.posX = this.baseX + this.maxOffset;
            this.velocityX *= -0.7;
          } else if (offsetX < -this.maxOffset) {
            this.posX = this.baseX - this.maxOffset;
            this.velocityX *= -0.7;
          }

          if (offsetY > this.maxOffset) {
            this.posY = this.baseY + this.maxOffset;
            this.velocityY *= -0.7;
          } else if (offsetY < -this.maxOffset) {
            this.posY = this.baseY - this.maxOffset;
            this.velocityY *= -0.7;
          }

          // Колебания для живости (усилены)
          this.swayPhase += 0.1;
          const swayX = Math.sin(this.swayPhase) * 3;
          const swayY = Math.cos(this.swayPhase * 1.7) * 2;

          // Пульсация прозрачности (ускорена)
          this.opacityPhase += 0.07;
          const opacityT = (Math.sin(this.opacityPhase) + 1) / 2;
          const opacity = 0.4 + opacityT * 0.4;

          // Вращение (ускорено)
          this.rotation += this.rotationSpeed;

          // Обновление стилей
          this.el.style.left = `${this.posX + swayX}vw`;
          this.el.style.top = `${this.posY + swayY}vh`;
          this.el.style.opacity = opacity.toFixed(2);
          this.el.style.transform = `rotate(${this.rotation.toFixed(1)}deg)`;
        }
      }

      // Создаём частицы
      let particles = [];

      function createParticles() {
        // Очистка старых
        particles.forEach(p => {
          if (p.el.parentNode) p.el.parentNode.removeChild(p.el);
        });
        particles = [];

        for (let i = 0; i < maxParticles; i++) {
          const type = types[Math.floor(Math.random() * types.length)];
          particles.push(new Particle(type, i, maxParticles));
        }
      }

      // Столкновение двух частиц (отталкивание)
      function handleCollision(p1, p2) {
        const dx = p2.posX - p1.posX;
        const dy = p2.posY - p1.posY;
        const dist = Math.sqrt(dx * dx + dy * dy);
        const minDist = p1.radiusVw + p2.radiusVw;

        if (dist < minDist && dist > 0) {
          // Нормализуем вектор столкновения
          const nx = dx / dist;
          const ny = dy / dist;

          // Проекция скоростей на нормаль
          const p1v = p1.velocityX * nx + p1.velocityY * ny;
          const p2v = p2.velocityX * nx + p2.velocityY * ny;

          // Обмен скоростями по нормали (упругое столкновение)
          const m1 = 1; // массы одинаковые
          const m2 = 1;

          const optimizedP = (2 * (p1v - p2v)) / (m1 + m2);

          p1.velocityX -= optimizedP * m2 * nx;
          p1.velocityY -= optimizedP * m2 * ny;

          p2.velocityX += optimizedP * m1 * nx;
          p2.velocityY += optimizedP * m1 * ny;

          // Коррекция позиций, чтобы частицы не слипались
          const overlap = minDist - dist;
          const correctionX = nx * overlap / 2;
          const correctionY = ny * overlap / 2;

          p1.posX -= correctionX;
          p1.posY -= correctionY;
          p2.posX += correctionX;
          p2.posY += correctionY;
        }
      }

      // Анимация
      function animate() {
        // Обновляем движения
        particles.forEach(p => p.update());

        // Обрабатываем столкновения (парами)
        for (let i = 0; i < particles.length; i++) {
          for (let j = i + 1; j < particles.length; j++) {
            handleCollision(particles[i], particles[j]);
          }
        }

        requestAnimationFrame(animate);
      }

      createParticles();
      animate();

      // Оптимизация ресайза с задержкой
      let resizeTimeout;
      window.addEventListener('resize', () => {
        clearTimeout(resizeTimeout);
        resizeTimeout = setTimeout(() => {
          createParticles();
        }, 300);
      });
    });
  </script>
</body>

</html>
