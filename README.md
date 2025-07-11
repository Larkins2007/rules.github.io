<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Правила чата</title>

  <!-- Подключение шрифтов Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com" crossorigin />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&family=Roboto+Slab:wght@700&display=swap" rel="stylesheet" />

  <style>
    /* Общие стили и фон, объединяющие оба дизайна */
    body {
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
      margin: 20px;
      line-height: 1.6;
      color: #222;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%);
      min-height: 100vh;
      padding: 20px;
      box-sizing: border-box;
      display: flex;
      justify-content: center;
      overflow-x: hidden;
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
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

    /* Заголовок h1 с декоративным шрифтом */
    h1 {
      font-family: 'Roboto Slab', serif;
      font-size: 2.4em;
      margin-bottom: 0.8em;
      display: flex;
      align-items: center;
      gap: 12px;
      color: #111827;
      letter-spacing: -0.02em;
      text-shadow: 0 1px 3px rgba(0,0,0,0.1);
    }
    h1 svg {
      width: 42px;
      height: 42px;
      fill: #4f46e5;
      flex-shrink: 0;
      filter: drop-shadow(0 1px 2px rgba(79, 70, 229, 0.5));
    }

    /* Заголовки h2 — заголовочные, жирные и крупные */
    h2 {
      font-family: 'Roboto Slab', serif;
      margin-top: 48px;
      margin-bottom: 14px;
      border-bottom: 3px solid #4f46e5;
      padding-bottom: 6px;
      color: #2c2f48;
      display: flex;
      align-items: center;
      gap: 10px;
      font-weight: 700;
      font-size: 1.5em;
      user-select: none;
      text-shadow: 0 0 1px rgba(79,70,229,0.3);
    }
    h2 svg {
      width: 28px;
      height: 28px;
      fill: #4f46e5;
      flex-shrink: 0;
      transition: transform 0.3s ease, fill 0.3s ease;
      cursor: default;
    }
    h2:hover svg {
      transform: rotate(15deg);
      fill: #3730a3;
    }

    /* Заголовки h3 — подзаголовки, полужирные */
    h3 {
      font-family: 'Inter', sans-serif;
      margin-top: 28px;
      margin-bottom: 8px;
      color: #3b4252;
      display: flex;
      align-items: center;
      gap: 8px;
      font-weight: 600;
      font-size: 1.15em;
    }
    h3 svg {
      width: 20px;
      height: 20px;
      fill: #4f46e5;
      flex-shrink: 0;
      transition: fill 0.3s ease;
      cursor: default;
    }
    h3:hover svg {
      fill: #3730a3;
    }

    /* Основной текст */
    p {
      font-family: 'Inter', sans-serif;
      margin-bottom: 1.2em;
      font-size: 1.05em;
      color: #4b5563;
      letter-spacing: 0.02em;
    }

    /* Списки */
    ul {
      font-family: 'Inter', sans-serif;
      padding-left: 1.4em;
      margin-bottom: 1.5em;
      color: #4b5563;
      font-size: 1.05em;
      letter-spacing: 0.02em;
    }
    ul li {
      margin-bottom: 0.8em;
    }

    /* Навигация */
    nav {
      background: #eef2ff;
      padding: 20px 24px;
      border-radius: 12px;
      margin-bottom: 40px;
      box-shadow: 0 4px 12px rgba(79, 70, 229, 0.1);
      font-family: 'Inter', sans-serif;
      user-select: none;
      max-width: 100%;
    }
    nav .toc-header {
      display: flex;
      align-items: center;
      gap: 12px;
      font-weight: 700;
      font-size: 1.3em;
      color: #4f46e5;
      cursor: pointer;
      padding: 8px 12px;
      border-radius: 10px;
      background: linear-gradient(135deg, #c7d2fe 0%, #a5b4fc 100%);
      box-shadow:
        inset 0 1px 0 rgba(255 255 255 / 0.6),
        0 4px 8px rgba(79, 70, 229, 0.2);
      transition:
        background 0.3s ease,
        color 0.3s ease,
        box-shadow 0.3s ease;
      user-select: none;
    }
    nav .toc-header:hover,
    nav .toc-header:focus {
      background: linear-gradient(135deg, #a5b4fc 0%, #6366f1 100%);
      color: #e0e7ff;
      outline: none;
      box-shadow:
        inset 0 1px 0 rgba(255 255 255 / 0.9),
        0 6px 15px rgba(55, 48, 163, 0.5);
    }
    nav .toc-header svg {
      width: 28px;
      height: 28px;
      fill: currentColor;
      flex-shrink: 0;
      transition: transform 0.3s ease;
      user-select: none;
      pointer-events: none;
    }
    nav .toc-header[aria-expanded="true"] svg {
      transform: rotate(90deg);
    }
    nav ul {
      padding-left: 0;
      list-style: none;
      margin-top: 12px;
      max-height: 500px; /* max height for smooth animation */
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
      gap: 10px;
      padding-left: 8px;
      border-left: 3px solid transparent;
      transition: border-color 0.3s ease;
    }
    nav ul li:hover,
    nav ul li:focus-within {
      border-left-color: #4f46e5;
      background: rgba(79, 70, 229, 0.1);
      border-radius: 6px;
    }
    nav ul li svg {
      width: 16px;
      height: 16px;
      fill: #4f46e5;
      flex-shrink: 0;
      transition: fill 0.3s ease;
    }
    nav ul li a {
      text-decoration: none;
      color: #4f46e5;
      font-weight: 600;
      font-size: 1.05em;
      transition: color 0.3s;
      flex-grow: 1;
      font-family: 'Inter', sans-serif;
    }
    nav ul li a:hover,
    nav ul li a:focus {
      color: #3730a3;
      outline: none;
      text-decoration: underline;
    }

    /* Акценты */
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

    /* Футер */
    footer {
      font-family: 'Inter', sans-serif;
      margin-top: 40px;
      font-size: 0.9em;
      color: #6b7280;
      text-align: center;
      user-select: none;
      letter-spacing: 0.02em;
    }

    /* Адаптив */
    @media (max-width: 700px) {
      body {
        margin: 10px;
        padding: 10px;
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
    }
  </style>
</head>
<body>
  <main>
    <h1>
      <!-- Иконка правил (щит с галочкой) -->
      <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Правила">
        <path d="M12 2L3 5v6c0 5.55 3.84 10.74 9 12 5.16-1.26 9-6.45 9-12V5l-9-3zM10 16l-4-4 1.41-1.41L10 13.17l6.59-6.59L18 8l-8 8z"/>
      </svg>
      Правила чата
    </h1>

    <p>Каждый вошедший пользователь добровольно принимает правила нашего чата и обязуется их соблюдать.</p>

    <nav aria-label="Оглавление">
      <div class="toc-header" role="button" tabindex="0" aria-expanded="true" aria-controls="toc-list" id="toc-toggle">
        Содержание
        <!-- Иконка списка -->
        <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Список">
          <path d="M4 10h16v2H4zm0-4h16v2H4zm0 8h10v2H4z"/>
        </svg>
      </div>
      <ul id="toc-list" tabindex="-1">
        <li>
          <!-- Иконка стрелки вправо -->
          <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Пункт">
            <path d="M10 17l5-5-5-5v10z"/>
          </svg>
          <a href="#ne-zhelatelno">Не желательно</a>
        </li>
        <li>
          <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Пункт">
            <path d="M10 17l5-5-5-5v10z"/>
          </svg>
          <a href="#zapreshchaetsya">Запрещается</a>
        </li>
        <li>
          <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Пункт">
            <path d="M10 17l5-5-5-5v10z"/>
          </svg>
          <a href="#dopolneniya-po-moderatoram">Важные дополнения по работе модераторов и контролю качества их действий</a>
        </li>
        <li>
          <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Пункт">
            <path d="M10 17l5-5-5-5v10z"/>
          </svg>
          <a href="#nakazaniya">Наказания</a>
        </li>
        <li>
          <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Пункт">
            <path d="M10 17l5-5-5-5v10z"/>
          </svg>
          <a href="#politika">Политика модераторов</a>
        </li>
      </ul>
    </nav>

    <section id="samoe-vazhnoe">
      <h2>
        Самое важное
        <!-- Иконка звезды -->
        <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Звезда">
          <path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/>
        </svg>
      </h2>
      <p><strong>Каждый участник чата обязан уважать других, соблюдать правила и поддерживать дружелюбную атмосферу.</strong></p>
      <p>Нарушение этого принципа ведёт к предупреждениям и, при повторении — к более строгим мерам вплоть до бана.</p>
    </section>

    <section id="ne-zhelatelno">
      <h2>
        Не желательно
        <!-- Иконка предупреждения -->
        <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Предупреждение">
          <path d="M1 21h22L12 2 1 21zm12-3h-2v-2h2v2zm0-4h-2v-4h2v4z"/>
        </svg>
      </h2>
      <h3>
        1. Использование большого количества ненормативной лексики
        <!-- Иконка "звук" -->
        <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Звук">
          <path d="M3 9v6h4l5 5V4L7 9H3z"/>
        </svg>
      </h3>
      <p><strong>Наказание:</strong> Предупреждение</p>
      <p><strong>Пояснение:</strong> Мы понимаем, что иногда эмоции берут верх, но старайтесь не злоупотреблять матом. Если вы используете ненормативную лексику редко и без оскорблений — это не проблема.</p>
      <p><strong>Пример:</strong> «Вот это классно!» — нормально; «Ты полный [нецензурное слово]» — повод для предупреждения.</p>

      <h3>
        2. Рекламировать другие группы/каналы
        <!-- Иконка "реклама" -->
        <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Реклама">
          <path d="M3 10h2v4H3v-4zm16-2h2v8h-2v-8zm-6 0h2v8h-2v-8zM5 7h14v2H5V7z"/>
        </svg>
      </h3>
      <p><strong>Наказание:</strong> Предупреждение</p>
      <p><strong>Пояснение:</strong> Реклама чужих ресурсов без согласия администрации мешает общению. Если хотите поделиться полезным каналом — сначала свяжитесь с администратором (@lia_os).</p>
      <p><strong>Пример:</strong> «Подпишитесь на мой канал!» — запрещено без разрешения.</p>

      <h3>
        3. Начинать ссоры, старайтесь поддерживать комфорт в чате
        <!-- Иконка "конфликт" -->
        <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Конфликт">
          <path d="M7 14l5-5 5 5H7z"/>
        </svg>
      </h3>
      <p><strong>Наказание:</strong> Предупреждение или мут (в зависимости от интенсивности)</p>
      <p><strong>Пояснение:</strong> Споры бывают, но если они переходят в оскорбления или мешают другим — сначала предупредим, а при повторе временно ограничим возможность писать (мут).</p>
      <p><strong>Пример:</strong> «Ты неправ!» — нормально, «Ты идиот!» — повод для наказания.</p>

      <h3>
        4. Flash — видео/голосовые (редкие громкие звуки, резко мерцающие видео)
        <!-- Иконка "звук мут" -->
        <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Звук мут">
          <path d="M16.5 12c0-1.77-1.02-3.29-2.5-4.03v8.06c1.48-.74 2.5-2.26 2.5-4.03zM19 12c0 2.89-2.39 5.24-5.5 5.24S8 14.89 8 12s2.39-5.24 5.5-5.24S19 9.11 19 12z"/>
        </svg>
      </h3>
      <p><strong>Наказание:</strong> Мут</p>
      <p><strong>Пояснение:</strong> Такие материалы могут раздражать или вредить здоровью участников (например, вызывать головную боль). Поэтому за их публикацию временно ограничивается возможность писать.</p>

      <h3>
        5. Оскорбление персонажей, уважайте чувства и вкусы других
        <!-- Иконка "сердце" -->
        <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Сердце">
          <path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41 1.01 4.5 2.09C13.09 4.01 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"/>
        </svg>
      </h3>
      <p><strong>Наказание:</strong> Предупреждение или мут</p>
      <p><strong>Пояснение:</strong> Критика — нормально, а личные оскорбления — нет.</p>
      <p><strong>Пример:</strong> «Мне не нравится этот персонаж» — допустимо, «Этот персонаж — дурак» — нарушение.</p>

      <h3>
        6. Пересылка личных сообщений другого человека в беседу
        <!-- Иконка "конфиденциальность" -->
        <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Конфиденциальность">
          <path d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm0 2c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"/>
        </svg>
      </h3>
      <p><strong>Наказание:</strong> Предупреждение</p>
      <p><strong>Пояснение:</strong> Личные сообщения другого участника нельзя пересылать в общий чат без согласия обеих сторон. Если оба участника переписки являются членами группы, часть переписки пересылается только с одобрения обеих сторон. Это помогает сохранять приватность и уважать личное пространство.</p>
      <p><strong>Пример:</strong> Пересылать скриншоты или сообщения из личных диалогов без разрешения — запрещено.</p>
    </section>

    <section id="zapreshchaetsya">
      <h2>
        Запрещается
        <!-- Иконка запрета -->
        <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Запрет">
          <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm5 13.59L13.59 17 12 15.41 10.41 17 7 13.59 8.59 12 7 10.41 10.41 7 12 8.59 13.59 7 17 10.41 15.41 12 17 13.59z"/>
        </svg>
      </h2>

      <h3>
        1. Обсуждение политики и публикация любого контента, связанного с политикой
        <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Политика">
          <path d="M7 10h2v4H7zM15 10h2v4h-2z"/>
        </svg>
      </h3>
      <p><strong>Наказание:</strong> Бан</p>
      <p><strong>Пояснение:</strong> Политика часто вызывает конфликты и разделение. Чтобы сохранить дружелюбную атмосферу, такие темы запрещены.</p>
      <p><strong>Пример:</strong> обсуждение выборов, политических лидеров и т.п.</p>

      <h3>
        2. Оскорбления
        <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Оскорбления">
          <path d="M12 4a8 8 0 1 0 0 16 8 8 0 0 0 0-16zm1 11h-2v-2h2v2zm0-4h-2V7h2v4z"/>
        </svg>
      </h3>
      <p><strong>Наказание:</strong> Предупреждение, при повторе — мут или бан</p>
      <p><strong>Пояснение:</strong> Шутки — хорошо, но если кому-то неприятно — защитим его.</p>
      <p><strong>Пример:</strong> «Ты такой смешной дурачок» — шутка, но если это обидело — последует предупреждение.</p>

      <h3>
        3. Публикация порнографического и околопорнографического контента
        <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Порнография">
          <path d="M12 2a10 10 0 1 0 0 20 10 10 0 0 0 0-20zm-1 14h2v2h-2v-2zm0-8h2v6h-2V8z"/>
        </svg>
      </h3>
      <p><strong>Наказание:</strong> Бан</p>
      <p><strong>Пояснение:</strong> Нарушает правила приличия и закон.</p>
      <p><strong>Пример:</strong> откровенные фото, видео или ссылки.</p>

      <h3>
        4. Публикация треш-контента (стикеры/видео/гиф с расчлененкой и тому подобное)
        <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Треш-контент">
          <path d="M4 4h16v16H4zM9 9h6v6H9z"/>
        </svg>
      </h3>
      <p><strong>Наказание:</strong> Бан</p>
      <p><strong>Пояснение:</strong> Шокирующие материалы могут травмировать участников.</p>
      <p><strong>Пример:</strong> видео с насилием или жестокостью.</p>

      <h3>
        5. Поднятие тем, нарушающих законы РФ (экстремизм, терроризм, пропаганда наркотиков, оскорбление чувств верующих и др.)
        <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Закон">
          <path d="M12 4a8 8 0 0 1 8 8c0 4.42-3.58 8-8 8s-8-3.58-8-8a8 8 0 0 1 8-8zm0 14a6 6 0 0 0 6-6 6 6 0 0 0-6-6 6 6 0 0 0-6 6 6 6 0 0 0 6 6z"/>
        </svg>
      </h3>
      <p><strong>Наказание:</strong> Бан</p>
      <p><strong>Пояснение:</strong> Такие темы запрещены законом и чатом.</p>
      <p><strong>Пример:</strong> призывы к насилию, обсуждение запрещённых веществ.</p>

      <h3>
        6. Спам / флуд (часто повторяющиеся сообщения, сообщения без смысла)
        <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Спам">
          <path d="M3 12h18M3 6h18M3 18h18"/>
        </svg>
      </h3>
      <p><strong>Наказание:</strong> Мут</p>
      <p><strong>Пояснение:</strong> Чтобы чат был удобен для всех, не стоит засорять его бессмысленными сообщениями.</p>
      <p><strong>Пример:</strong> повторять одну и ту же фразу много раз подряд.</p>

      <h3>
        7. Публичное осуждение действий администрации / провокация администрации типа «ну давай бань меня»
        <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Администрация">
          <path d="M12 2a10 10 0 1 1 0 20 10 10 0 0 1 0-20zm1 15h-2v-2h2v2zm0-4h-2V7h2v6z"/>
        </svg>
      </h3>
      <p><strong>Наказание:</strong> Предупреждение или мут</p>
      <p><strong>Пояснение:</strong> Если есть вопросы к администрации — лучше написать в личку, а не провоцировать конфликт в общем чате.</p>

      <h3>
        8. Любая дискриминация по расовому/национальному/половому/религиозному признаку
        <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Дискриминация">
          <path d="M12 2C6.48 2 2 6.48 2 12c0 4.42 3.58 8 8 8 1.85 0 3.55-.63 4.9-1.69l4.39 1.16-1.16-4.39A7.96 7.96 0 0 0 20 12c0-5.52-4.48-10-10-10z"/>
        </svg>
      </h3>
      <p><strong>Наказание:</strong> Бан</p>
      <p><strong>Пояснение:</strong> Мы за равенство и уважение ко всем.</p>
      <p><strong>Пример:</strong> оскорбления по национальному признаку недопустимы.</p>

      <h3>
        9. Просьбы перейти по ссылкам/зарегистрироваться на вредоносном сайте
        <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Ссылки">
          <path d="M10 17l5-5-5-5v10z"/>
        </svg>
      </h3>
      <p><strong>Наказание:</strong> Бан</p>
      <p><strong>Пояснение:</strong> Безопасность участников — наш приоритет.</p>
      <p><strong>Пример:</strong> ссылки на мошеннические сайты.</p>
    </section>

    <section id="dopolneniya-po-moderatoram">
      <h2>
        Важные дополнения по работе модераторов и контролю качества их действий
        <!-- Иконка щита -->
        <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Щит">
          <path d="M12 2L3 5v6c0 5.55 3.84 10.74 9 12 5.16-1.26 9-6.45 9-12V5l-9-3z"/>
        </svg>
      </h2>
      <h3>
        10. Модераторы обязаны действовать в соответствии с правилами чата и не использовать свои полномочия в личных интересах
        <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Пользователь">
          <path d="M12 12c2.21 0 4-1.79 4-4S14.21 4 12 4 8 5.79 8 8s1.79 4 4 4zM6 20v-2c0-2.21 3.58-4 6-4s6 1.79 6 4v2H6z"/>
        </svg>
      </h3>
      <p><strong>Пояснение:</strong> Если заметили нарушение или злоупотребление полномочиями (например, необоснованно мутит или банит, игнорирует правила), обратитесь к высшим администраторам или создателю чата (@lia_os). Жалобы рассматриваются, и мы защищаем от несправедливого обращения.</p>

      <h3>
        11. Перед применением наказания модератор должен дать словесное предупреждение участнику
        <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Внимание">
          <path d="M12 2a10 10 0 1 1 0 20 10 10 0 0 1 0-20zm1 15h-2v-2h2v2zm0-4h-2V7h2v6z"/>
        </svg>
      </h3>
      <p><strong>Пояснение:</strong> Если поведение начинает нарушать правила или мешать комфорту, модератор предупреждает: «Пожалуйста, прекратите, иначе последуют меры». Если предупреждение игнорируется — применяется наказание (мут, бан и т.п.). Это помогает избежать конфликтов и даёт шанс исправиться.</p>
    </section>

    <section id="nakazaniya">
      <h2>
        Наказания
        <!-- Иконка молотка -->
        <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Наказания">
          <path d="M14.7 9.3l-4.4 4.4-1.4-1.4 4.4-4.4 1.4 1.4zM3 17h18v2H3v-2z"/>
        </svg>
      </h2>
      <ul>
        <li><strong>Предупреждение</strong> — первое и мягкое наказание. Сообщаем, что поведение не соответствует правилам с объяснением.</li>
        <li><strong>Мут</strong> — временное ограничение возможности писать (несколько минут или часов). Используется при повторных нарушениях или серьёзных проступках. Перед мутом обязательно словесное предупреждение.</li>
        <li><strong>Бан</strong> — удаление из чата с запретом на повторный вход. За серьёзные или неоднократные нарушения.</li>
      </ul>
    </section>

    <section id="politika">
      <h2>
        Политика модераторов
        <!-- Иконка политика -->
        <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" role="img" aria-label="Политика">
          <path d="M12 12c2.21 0 4-1.79 4-4S14.21 4 12 4 8 5.79 8 8s1.79 4 4 4zm-6 8v-2c0-2.21 3.58-4 6-4s6 1.79 6 4v2H6z"/>
        </svg>
      </h2>
      <ul>
        <li>Всегда сначала предупреждайте участников, чтобы дать им шанс исправиться.</li>
        <li>Действуйте объективно и справедливо, руководствуясь правилами, а не личными симпатиями.</li>
        <li>При сомнениях или спорных ситуациях обращайтесь к высшему администратору для консультации.</li>
        <li>Помните, что ваша задача — поддерживать комфорт и безопасность в чате, а не «наказывать» ради наказания.</li>
      </ul>
    </section>

    <footer>
      <p>Если у вас есть вопросы или нужна помощь — обращайтесь к администрации (<strong>@lia_os</strong>).</p>
    </footer>
  </main>

  <script>
    (function(){
      const toggle = document.getElementById('toc-toggle');
      const list = document.getElementById('toc-list');

      function setCollapsed(collapsed) {
        if(collapsed){
          list.classList.add('collapsed');
          toggle.setAttribute('aria-expanded', 'false');
        } else {
          list.classList.remove('collapsed');
          toggle.setAttribute('aria-expanded', 'true');
        }
      }

      // Изначально раскрыто
      setCollapsed(false);

      toggle.addEventListener('click', () => {
        const isCollapsed = list.classList.contains('collapsed');
        setCollapsed(!isCollapsed);
      });

      // Доступность: переключение по Enter и Space
      toggle.addEventListener('keydown', (e) => {
        if(e.key === 'Enter' || e.key === ' '){
          e.preventDefault();
          toggle.click();
        }
      });
    })();
  </script>
</body>
</html>
