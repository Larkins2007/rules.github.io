<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Правила чата | Hoyo Community</title>
  <meta name="description" content="Полный свод правил чата: модерация, наказания, политика." />
  <link rel="preconnect" href="https://fonts.googleapis.com" crossorigin />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&family=Roboto+Slab:wght@700&display=swap" rel="stylesheet" />
  <style>
    /* === 1. ГЛОБАЛЬНЫЕ НАСТРОЙКИ И ПЕРЕМЕННЫЕ === */
    :root {
      --bg-dark: #050a14;
      --card-bg: rgba(11, 26, 45, 0.85);
      --accent-purple: #7c3aed;
      --accent-light: #a78bfa;
      --text-main: #cbd5e1;
      --text-muted: #a0aec0;
      --rainbow: linear-gradient(270deg, #ff6b6b, #fbc531, #4cd137, #00a8ff, #9c88ff, #ff6b6b);
      --shadow-glow: 0 0 20px rgba(124, 58, 237, 0.4);
    }

    html { scroll-behavior: smooth; scroll-padding-top: 100px; }
    
    body {
      font-family: 'Inter', sans-serif;
      margin: 0;
      background: var(--bg-dark) url('https://www.transparenttextures.com/patterns/stardust.png');
      color: var(--text-main);
      min-height: 100vh;
      padding-top: 120px;
      overflow-x: hidden;
      display: flex;
      flex-direction: column;
      align-items: center;
      position: relative;
    }

    /* === 2. ФОНОВЫЕ ЭФФЕКТЫ (ОБЛАКА И ЗВЕЗДЫ) === */
    #background-container {
      position: fixed; top: 0; left: 0; width: 100vw; height: 100vh;
      pointer-events: none; z-index: 0; overflow: hidden;
    }

    .cloud {
      position: absolute; opacity: 0.25; animation: cloudMove linear infinite;
      will-change: transform; filter: drop-shadow(0 0 8px rgba(107, 122, 140, 0.4));
    }

    .cloud1 { width: 280px; height: 150px; background-image: url("data:image/svg+xml,%3csvg width='280' height='150' viewBox='0 0 280 150' fill='none' xmlns='http://www.w3.org/2000/svg'%3e%3cellipse cx='140' cy='75' rx='120' ry='60' fill='%236b7a8c' fill-opacity='0.2'/%3e%3c/svg%3e"); }
    .cloud2 { width: 180px; height: 100px; background-image: url("data:image/svg+xml,%3csvg width='180' height='100' viewBox='0 0 180 100' fill='none' xmlns='http://www.w3.org/2000/svg'%3e%3ccircle cx='60' cy='50' r='40' fill='%236b7a8c' fill-opacity='0.15'/%3e%3ccircle cx='110' cy='50' r='50' fill='%236b7a8c' fill-opacity='0.15'/%3e%3c/svg%3e"); }
    
    @keyframes cloudMove { 
      from { transform: translateX(-400px); } 
      to { transform: translateX(120vw); } 
    }

    .particle {
      position: absolute; border-radius: 50%;
      background: radial-gradient(circle, var(--accent-light), transparent);
      opacity: 0.8; animation: twinkle infinite ease-in-out;
    }
    @keyframes twinkle { 0%, 100% { opacity: 0.4; transform: scale(1); } 50% { opacity: 1; transform: scale(1.3); } }

    /* === 3. УМНЫЙ ПОИСК === */
    #search-container {
      position: fixed; top: 0; left: 50%; transform: translateX(-50%);
      width: 100%; max-width: 900px; background: rgba(11, 26, 45, 0.98);
      backdrop-filter: blur(20px); padding: 15px 25px; z-index: 10000;
      border-bottom: 2px solid var(--accent-purple); display: flex; align-items: center;
      box-shadow: 0 4px 30px rgba(0,0,0,0.6);
    }

    .search-wrapper { position: relative; width: 100%; max-width: 550px; margin: 0 auto; }
    
    #search-input {
      width: 100%; padding: 14px 50px 14px 20px; border-radius: 12px;
      border: 2px solid var(--accent-purple); background: #1e293b; color: #fff;
      font-size: 1.1em; outline: none; transition: 0.3s; box-sizing: border-box;
    }
    #search-input:focus { border-color: var(--accent-light); box-shadow: var(--shadow-glow); }
    #search-input::placeholder { color: var(--text-muted); }

    #clear-button {
      position: absolute; right: 15px; top: 50%; transform: translateY(-50%);
      background: none; border: none; color: var(--accent-light); font-size: 1.8em;
      cursor: pointer; display: none; line-height: 1; transition: 0.2s;
    }
    #clear-button:hover { color: #fff; transform: translateY(-50%) scale(1.1); }

    /* === 4. ОСНОВНОЙ КОНТЕНТ === */
    main {
      position: relative; z-index: 10; max-width: 900px; width: 92%;
      background: var(--card-bg); backdrop-filter: blur(25px);
      padding: 50px; border-radius: 24px; margin-bottom: 80px;
      box-shadow: 0 15px 60px rgba(0,0,0,0.7);
      border: 1px solid rgba(255,255,255,0.08);
      animation: fadeInMain 1s ease-out;
    }

    @keyframes fadeInMain { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }

    h1 {
      font-family: 'Roboto Slab', serif; text-align: center; font-size: clamp(2.2rem, 8vw, 3.5rem);
      background: var(--rainbow); background-size: 600%; -webkit-background-clip: text;
      color: transparent; animation: rainbowShift 10s linear infinite; margin: 0 0 20px;
    }
    @keyframes rainbowShift { 0% { background-position: 0% 50%; } 100% { background-position: 600% 50%; } }

    /* Навигация */
    nav { 
      border: 1.5px solid rgba(167, 139, 250, 0.3); border-radius: 18px; 
      padding: 30px; margin: 40px 0; text-align: center; background: rgba(0,0,0,0.2);
    }
    .toc-header { 
      color: var(--accent-light); font-weight: 700; font-size: 1.5em; 
      margin-bottom: 20px; display: flex; justify-content: center; align-items: center; gap: 12px;
      cursor: pointer; transition: 0.3s;
    }
    .toc-header:hover { text-shadow: 0 0 10px var(--accent-light); }
    .toc-list { 
      list-style: none; padding: 0; display: flex; flex-wrap: wrap; 
      justify-content: center; gap: 20px; margin: 0;
    }
    .toc-list a { 
      color: var(--text-main); text-decoration: none; font-weight: 600; 
      transition: 0.3s; border-bottom: 1px solid transparent; padding: 5px 0;
    }
    .toc-list a:hover { color: var(--accent-light); border-bottom-color: var(--accent-light); transform: translateY(-2px); }

    /* Стилизация секций */
    h2 { 
      text-align: center; font-size: 2.2em; margin-top: 80px;
      background: linear-gradient(90deg, var(--accent-purple), var(--accent-light));
      -webkit-background-clip: text; color: transparent; 
      border-bottom: 2px solid rgba(124, 58, 237, 0.2); padding-bottom: 15px;
    }
    
    section h3 {
      color: #d8b4fe; font-size: 1.45em; display: flex; align-items: center; gap: 12px;
      text-shadow: 0 0 10px rgba(168, 85, 247, 0.6); margin-top: 45px; margin-bottom: 15px;
    }

    .rule-block { 
      margin-bottom: 40px; padding: 25px; 
      background: rgba(255,255,255,0.03); border-radius: 18px; 
      border-left: 5px solid var(--accent-purple);
      transition: transform 0.3s ease, background 0.3s ease;
    }
    .rule-block:hover { background: rgba(255,255,255,0.06); transform: translateX(5px); }

    .copy-btn { 
      background: transparent; border: none; color: var(--accent-light); 
      cursor: pointer; font-size: 1.3em; transition: 0.3s; padding: 5px;
    }
    .copy-btn:hover { transform: scale(1.2); color: #fff; text-shadow: 0 0 10px var(--accent-light); }

    mark { background: rgba(124, 58, 237, 0.8); color: #fff; border-radius: 5px; padding: 0 4px; box-shadow: 0 0 5px var(--accent-purple); }

    /* === 5. ДВУСТОРОННЯЯ АНИМАЦИЯ REVEAL === */
    .reveal {
      opacity: 0;
      transform: translateY(40px) scale(0.97);
      transition: all 0.9s cubic-bezier(0.25, 1, 0.5, 1);
      will-change: transform, opacity;
    }
    /* Появление при входе в экран */
    .reveal.visible { opacity: 1; transform: translateY(0) scale(1); }

    /* Подпись и Футер */
    #signature { text-align: center; margin-top: 100px; }
    #signature p { 
      font-family: 'Roboto Slab'; font-size: 2em; 
      background: var(--rainbow); background-size: 400%; -webkit-background-clip: text; 
      color: transparent; animation: rainbowShift 8s linear infinite; 
    }

    footer { 
      text-align: center; padding: 60px; color: var(--text-muted); 
      position: relative; z-index: 10; width: 100%; 
      border-top: 1px solid rgba(255,255,255,0.06); background: rgba(0,0,0,0.3);
    }
    
    #no-results { display: none; text-align: center; margin: 50px 0; color: var(--accent-light); font-size: 1.3em; font-weight: bold; }

    @media (max-width: 700px) {
      main { padding: 30px 20px; }
      h1 { font-size: 2rem; }
      .toc-list { flex-direction: column; gap: 12px; }
    }
  </style>
</head>
<body>

  <div id="search-container">
    <div class="search-wrapper">
      <input type="search" id="search-input" placeholder="Поиск по правилам чата..." autocomplete="off">
      <button id="clear-button" title="Очистить">&times;</button>
    </div>
  </div>

  <div id="background-container">
    <div class="cloud cloud1" style="top: 10%; animation-duration: 140s;"></div>
    <div class="cloud cloud2" style="top: 35%; animation-duration: 100s; animation-delay: -30s;"></div>
    <div class="cloud cloud1" style="top: 60%; animation-duration: 120s; animation-delay: -50s;"></div>
    <div class="cloud cloud2" style="top: 85%; animation-duration: 160s; animation-delay: -15s;"></div>
  </div>

  <main id="main-content">
    <h1 class="reveal">Правила чата</h1>
    <p class="reveal" style="text-align: center; font-size: 1.25em; color: var(--text-muted); margin-bottom: 40px;">
      Добро пожаловать в наше сообщество! Пожалуйста, ознакомьтесь с правилами поведения.
    </p>

    <nav class="reveal">
      <div class="toc-header">🧭 Навигация по разделам</div>
      <ul class="toc-list">
        <li><a href="#samoe-vazhnoe">Самое важное</a></li>
        <li><a href="#ne-zhelatelno">Не желательно</a></li>
        <li><a href="#zapreshchaetsya">Запрещается</a></li>
        <li><a href="#moderators">Модерация</a></li>
        <li><a href="#nakazaniya">Наказания</a></li>
      </ul>
    </nav>

    <section id="samoe-vazhnoe">
      <h2 class="reveal">Самое важное</h2>
      <div class="rule-block reveal">
        <p style="font-size: 1.1em; line-height: 1.7;">
          <strong>Уважение превыше всего.</strong> Мы здесь для того, чтобы делиться радостью от игр и общения. Любое токсичное поведение, направленное на разрушение комфортной атмосферы, будет немедленно пресекаться.
        </p>
      </div>
    </section>

    <section id="ne-zhelatelno">
      <h2 class="reveal">1. Не желательно</h2>
      
      <div class="rule-block reveal">
        <h3>1. Избыток нецензурной лексики <button class="copy-btn" title="Скопировать">📋</button></h3>
        <p><strong>Наказание:</strong> Словесное предупреждение.</p>
        <p>Мы не запрещаем мат полностью, но просим не превращать свою речь в сплошной поток ругани. Редкое использование для эмоций допустимо.</p>
      </div>

      <div class="rule-block reveal">
        <h3>2. Самопиар и реклама <button class="copy-btn">📋</button></h3>
        <p><strong>Наказание:</strong> Предупреждение / Мут.</p>
        <p>Реклама личных каналов, групп или ботов без прямого согласия создателя чата (@lia_os) запрещена. Поделиться интересным контентом можно, но не превращайте это в спам.</p>
      </div>

      <div class="rule-block reveal">
        <h3>3. Ссоры и разборки <button class="copy-btn">📋</button></h3>
        <p><strong>Наказание:</strong> Предупреждение / Мут.</p>
        <p>Если спор заходит в тупик и превращается в личный конфликт — переходите в ЛС. Не мешайте остальным участникам наслаждаться беседой.</p>
      </div>

      <div class="rule-block reveal">
        <h3>4. Flash-контент (громкие звуки/мерцание) <button class="copy-btn">📋</button></h3>
        <p><strong>Наказание:</strong> Мут.</p>
        <p>Громкие голосовые сообщения, скримеры или видео с резкими вспышками света запрещены. Заботьтесь о здоровье и ушах сочатников.</p>
      </div>
    </section>

    <section id="zapreshchaetsya">
      <h2 class="reveal">2. Запрещается</h2>

      <div class="rule-block reveal">
        <h3>1. Политика в любом виде <button class="copy-btn">📋</button></h3>
        <p><strong>Наказание: Бан.</strong></p>
        <p>Обсуждение текущих мировых событий, политических лидеров, партий и конфликтов строго запрещено. Наш чат — территория, свободная от политики.</p>
      </div>

      <div class="rule-block reveal">
        <h3>2. Оскорбления участников <button class="copy-btn">📋</button></h3>
        <p><strong>Наказание:</strong> Мут / Бан.</p>
        <p>Прямые оскорбления, травля (буллинг) и переход на личности недопустимы. Мы ценим каждого участника.</p>
      </div>

      <div class="rule-block reveal">
        <h3>3. NSFW / Шокирующий контент <button class="copy-btn">📋</button></h3>
        <p><strong>Наказание: Бан.</strong></p>
        <p>Публикация материалов сексуального характера (18+), жестокости, насилия и прочего «треша» ведет к немедленной блокировке.</p>
      </div>

      <div class="rule-block reveal">
        <h3>4. Нарушение законов и экстремизм <button class="copy-btn">📋</button></h3>
        <p><strong>Наказание: Бан.</strong></p>
        <p>Пропаганда наркотиков, оружия, призывы к насилию и экстремистские высказывания запрещены как правилами чата, так и законом.</p>
      </div>

      <div class="rule-block reveal">
        <h3>5. Флуд и спам <button class="copy-btn">📋</button></h3>
        <p><strong>Наказание:</strong> Мут.</p>
        <p>Отправка более 5 сообщений подряд, бессмысленные наборы букв, массовые отметки участников — всё это считается флудом.</p>
      </div>

      <div class="rule-block reveal">
        <h3>6. Дискриминация <button class="copy-btn">📋</button></h3>
        <p><strong>Наказание: Бан.</strong></p>
        <p>Любые высказывания, унижающие достоинство человека по признаку расы, пола, национальности или религии, запрещены.</p>
      </div>
    </section>

    <section id="moderators">
      <h2 class="reveal">Модерация</h2>
      <div class="rule-block reveal">
        <p>• Модераторы обязаны быть вежливыми и объективными.</p>
        <p>• Перед выдачей наказания (кроме грубых нарушений типа NSFW/Политика) модератор должен дать <strong>словесное предупреждение</strong>.</p>
        <p>• Все жалобы на работу модераторов принимаются в ЛС: @lia_os.</p>
      </div>
    </section>

    <section id="nakazaniya">
      <h2 class="reveal">Наказания</h2>
      <ul class="reveal" style="font-size: 1.15em; line-height: 2;">
        <li><strong>Предупреждение</strong> — мягкое напоминание о правилах.</li>
        <li><strong>Мут</strong> — временное ограничение общения (от 10 минут до 3 суток).</li>
        <li><strong>Бан</strong> — окончательное удаление из сообщества без права возврата.</li>
      </ul>
    </section>

    <div id="no-results">Ничего не найдено по вашему запросу...</div>

    <div id="signature" class="reveal">
      <p>by Везунчик</p>
    </div>
  </main>

  <footer>
    <p>Создатель чата: <strong>@lia_os</strong></p>
    <p style="margin-top: 10px; font-size: 0.85em;">© 2026 Hoyo Community Rules. Все права защищены.</p>
    <div id="particles-container" style="height: 150px; position: relative; overflow: hidden; margin-top: 20px;"></div>
  </footer>

  <script>
    /* === 1. АНИМАЦИЯ ПОЯВЛЕНИЯ/СКРЫТИЯ (ДВУСТОРОННЯЯ) === */
    const obsOptions = { threshold: 0.15, rootMargin: "0px 0px -50px 0px" };
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
        } else {
          // Элемент уходит с экрана — скрываем его (эффект бесконечной "дышащей" страницы)
          entry.target.classList.remove('visible');
        }
      });
    }, obsOptions);

    document.querySelectorAll('.reveal').forEach(el => observer.observe(el));


    /* === 2. ПОИСК С ГЛУБОКОЙ ПОДСВЕТКОЙ (HIGHLIGHT) === */
    const sInput = document.getElementById('search-input');
    const clearBtn = document.getElementById('clear-button');
    const mainArea = document.getElementById('main-content');

    // Функция очистки маркеров поиска
    function clearSearchMarks() {
      const marks = mainArea.querySelectorAll('mark');
      marks.forEach(m => {
        const parent = m.parentNode;
        parent.replaceChild(document.createTextNode(m.textContent), m);
        parent.normalize();
      });
    }

    // Рекурсивный поиск текста в узлах
    function highlightNodes(node, term) {
      if (node.nodeType === 3) { // Текстовый узел
        const text = node.data;
        const regex = new RegExp(`(${term.replace(/[.*+?^${}()|[\]\\]/g, '\\$&')})`, 'gi');
        const match = text.match(regex);
        
        if (match) {
          const fragment = document.createDocumentFragment();
          let lastIdx = 0;
          text.replace(regex, (m, offset) => {
            fragment.appendChild(document.createTextNode(text.slice(lastIdx, offset)));
            const mark = document.createElement('mark');
            mark.textContent = m;
            fragment.appendChild(mark);
            lastIdx = offset + m.length;
          });
          fragment.appendChild(document.createTextNode(text.slice(lastIdx)));
          node.parentNode.replaceChild(fragment, node);
        }
      } else if (node.nodeType === 1 && node.childNodes && !['SCRIPT','STYLE','MARK','BUTTON'].includes(node.tagName)) {
        Array.from(node.childNodes).forEach(child => highlightNodes(child, term));
      }
    }

    sInput.addEventListener('input', () => {
      const query = sInput.value.toLowerCase().trim();
      clearSearchMarks();
      clearBtn.style.display = query ? 'block' : 'none';
      
      let foundSomething = false;
      const elementsToSearch = document.querySelectorAll('.rule-block, section, h2, nav, ul');

      elementsToSearch.forEach(el => {
        if (el.id === 'no-results') return;
        const hasMatch = el.innerText.toLowerCase().includes(query);
        
        if (query === '') {
          el.style.display = ''; 
          foundSomething = true;
        } else {
          el.style.display = hasMatch ? 'block' : 'none';
          if (hasMatch) {
            foundSomething = true;
            highlightNodes(el, query);
          }
        }
      });

      document.getElementById('no-results').style.display = (query && !foundSomething) ? 'block' : 'none';
    });

    clearBtn.addEventListener('click', () => {
      sInput.value = '';
      sInput.dispatchEvent(new Event('input'));
      sInput.focus();
    });


    /* === 3. КОПИРОВАНИЕ ПРАВИЛ === */
    document.addEventListener('click', e => {
      if (e.target.classList.contains('copy-btn')) {
        const parentH3 = e.target.closest('h3');
        // Текст заголовка без иконки
        const textToCopy = parentH3.innerText.replace('📋', '').trim();
        
        navigator.clipboard.writeText(textToCopy).then(() => {
          const originalIcon = e.target.innerText;
          e.target.innerText = '✔️';
          e.target.style.color = '#4cd137';
          setTimeout(() => { 
            e.target.innerText = originalIcon; 
            e.target.style.color = ''; 
          }, 2000);
        });
      }
    });


    /* === 4. ЧАСТИЦЫ-ЗВЕЗДЫ В ФУТЕРЕ === */
    const particlesContainer = document.getElementById('particles-container');
    const count = 45;

    for (let i = 0; i < count; i++) {
      const star = document.createElement('div');
      star.className = 'particle';
      const size = 3 + Math.random() * 6;
      star.style.width = `${size}px`;
      star.style.height = `${size}px`;
      star.style.left = `${Math.random() * 100}%`;
      star.style.top = `${Math.random() * 100}%`;
      star.style.animationDuration = `${2 + Math.random() * 4}s`;
      star.style.animationDelay = `${Math.random() * 5}s`;
      particlesContainer.appendChild(star);
    }
  </script>
</body>
</html>
