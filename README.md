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
    /* === 1. ГЛОБАЛЬНЫЕ СТИЛИ И ПЕРЕМЕННЫЕ === */
    :root {
      --bg-dark: #050a14;
      --card-bg: rgba(11, 26, 45, 0.85);
      --accent-purple: #7c3aed;
      --accent-light: #a78bfa;
      --text-main: #cbd5e1;
      --text-muted: #a0aec0;
      --rainbow: linear-gradient(270deg, #ff6b6b, #fbc531, #4cd137, #00a8ff, #9c88ff, #ff6b6b);
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

    /* SVG Облака прямо в CSS для объема кода и независимости от ссылок */
    .cloud1 { width: 280px; height: 150px; background-image: url("data:image/svg+xml,%3csvg width='280' height='150' viewBox='0 0 280 150' fill='none' xmlns='http://www.w3.org/2000/svg'%3e%3cellipse cx='140' cy='75' rx='120' ry='60' fill='%236b7a8c' fill-opacity='0.2'/%3e%3c/svg%3e"); }
    .cloud2 { width: 180px; height: 100px; background-image: url("data:image/svg+xml,%3csvg width='180' height='100' viewBox='0 0 180 100' fill='none' xmlns='http://www.w3.org/2000/svg'%3e%3ccircle cx='60' cy='50' r='40' fill='%236b7a8c' fill-opacity='0.15'/%3e%3ccircle cx='110' cy='50' r='50' fill='%236b7a8c' fill-opacity='0.15'/%3e%3c/svg%3e"); }
    
    @keyframes cloudMove { from { transform: translateX(-350px); } to { transform: translateX(110vw); } }

    .particle {
      position: absolute; border-radius: 50%;
      background: radial-gradient(circle, var(--accent-light), transparent);
      opacity: 0.8; animation: twinkle infinite ease-in-out;
    }
    @keyframes twinkle { 0%, 100% { opacity: 0.4; transform: scale(1); } 50% { opacity: 1; transform: scale(1.3); } }

    /* === 3. ПОИСКОВАЯ ПАНЕЛЬ === */
    #search-container {
      position: fixed; top: 0; left: 50%; transform: translateX(-50%);
      width: 100%; max-width: 900px; background: rgba(11, 26, 45, 0.96);
      backdrop-filter: blur(15px); padding: 15px 25px; z-index: 10000;
      border-bottom: 2px solid var(--accent-purple); display: flex; align-items: center;
      box-shadow: 0 4px 20px rgba(0,0,0,0.5);
    }

    #search-input {
      width: 100%; padding: 12px 45px 12px 20px; border-radius: 12px;
      border: 2px solid var(--accent-purple); background: #1e293b; color: #fff;
      font-size: 1.1em; outline: none; transition: 0.3s;
    }
    #search-input:focus { border-color: var(--accent-light); box-shadow: 0 0 15px rgba(124, 58, 237, 0.4); }

    #clear-button {
      position: absolute; right: 40px; background: none; border: none;
      color: var(--accent-light); font-size: 1.8em; cursor: pointer; display: none;
    }

    /* === 4. ОСНОВНОЙ КОНТЕНТ === */
    main {
      position: relative; z-index: 10; max-width: 900px; width: 92%;
      background: var(--card-bg); backdrop-filter: blur(20px);
      padding: 40px; border-radius: 20px; margin-bottom: 60px;
      box-shadow: 0 10px 50px rgba(124, 58, 237, 0.2);
      border: 1px solid rgba(255,255,255,0.05);
    }

    h1 {
      font-family: 'Roboto Slab', serif; text-align: center; font-size: 3em;
      background: var(--rainbow); background-size: 600%; -webkit-background-clip: text;
      color: transparent; animation: rainbowShift 12s linear infinite; margin: 0 0 20px;
    }
    @keyframes rainbowShift { 0% { background-position: 0% 50%; } 100% { background-position: 600% 50%; } }

    /* Навигация */
    nav { border: 1.5px solid rgba(167, 139, 250, 0.3); border-radius: 15px; padding: 25px; margin-bottom: 45px; text-align: center; }
    .toc-header { color: var(--accent-light); font-weight: 700; font-size: 1.4em; margin-bottom: 15px; display: flex; justify-content: center; align-items: center; gap: 10px; }
    .toc-list { list-style: none; padding: 0; display: flex; flex-wrap: wrap; justify-content: center; gap: 20px; }
    .toc-list a { color: var(--text-main); text-decoration: none; font-weight: 600; transition: 0.3s; border-bottom: 1px solid transparent; }
    .toc-list a:hover { color: var(--accent-light); border-bottom-color: var(--accent-light); transform: translateY(-2px); }

    /* Секции и правила */
    h2 { 
      text-align: center; font-size: 2em; margin-top: 70px;
      background: linear-gradient(90deg, var(--accent-purple), var(--accent-light));
      -webkit-background-clip: text; color: transparent; 
      border-bottom: 2px solid rgba(124, 58, 237, 0.2); padding-bottom: 10px;
    }
    
    section h3 {
      color: #d8b4fe; font-size: 1.4em; display: flex; align-items: center; gap: 12px;
      text-shadow: 0 0 10px rgba(168, 85, 247, 0.6); margin-top: 40px;
    }

    .rule-block { margin-bottom: 35px; padding: 25px; background: rgba(255,255,255,0.03); border-radius: 15px; border-left: 4px solid var(--accent-purple); }

    .copy-btn { background: transparent; border: none; color: var(--accent-light); cursor: pointer; font-size: 1.2em; transition: 0.3s; }
    .copy-btn:hover { transform: scale(1.3); color: #fff; text-shadow: 0 0 10px var(--accent-light); }

    mark { background: rgba(124, 58, 237, 0.7); color: #fff; border-radius: 5px; padding: 0 4px; }

    /* === 5. ТВОЯ ДВУСТОРОННЯЯ АНИМАЦИЯ (ПОЯВЛЕНИЕ/СКРЫТИЕ) === */
    .reveal {
      opacity: 0;
      transform: translateY(40px) scale(0.96);
      transition: all 0.8s cubic-bezier(0.25, 1, 0.5, 1);
      will-change: transform, opacity;
    }
    /* Когда элемент в зоне видимости */
    .visible { opacity: 1; transform: translateY(0) scale(1); }

    footer { text-align: center; padding: 50px; color: var(--text-muted); position: relative; z-index: 10; width: 100%; border-top: 1px solid rgba(255,255,255,0.05); }
    #signature p { font-family: 'Roboto Slab'; font-size: 1.8em; background: var(--rainbow); background-size: 400%; -webkit-background-clip: text; color: transparent; animation: rainbowShift 10s linear infinite; }

    @media (max-width: 650px) { h1 { font-size: 2.2em; } main { padding: 25px; } .toc-list { flex-direction: column; gap: 10px; } }
  </style>
</head>
<body>

  <div id="search-container">
    <div style="position: relative; width: 100%; max-width: 600px; margin: 0 auto;">
      <input type="search" id="search-input" placeholder="Поиск по правилам чата..." autocomplete="off">
      <button id="clear-button" title="Очистить">&times;</button>
    </div>
  </div>

  <div id="background-container">
    <div class="cloud cloud1" style="top: 10%; animation-duration: 130s;"></div>
    <div class="cloud cloud2" style="top: 30%; animation-duration: 95s; animation-delay: -20s;"></div>
    <div class="cloud cloud1" style="top: 55%; animation-duration: 110s; animation-delay: -45s;"></div>
    <div class="cloud cloud2" style="top: 80%; animation-duration: 150s; animation-delay: -10s;"></div>
  </div>

  <main id="main-content">
    <h1 class="reveal">Правила сообщества</h1>
    <p class="reveal" style="text-align: center; font-size: 1.2em; color: var(--text-muted);">Присоединяясь к нам, вы соглашаетесь соблюдать установленный порядок и уважать других участников.</p>

    <nav class="reveal">
      <div class="toc-header">🧭 Быстрая навигация</div>
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
        <p><strong>Главный принцип:</strong> Уважение. Мы создаем пространство для отдыха. Любое поведение, намеренно портящее атмосферу, будет пресекаться администрацией.</p>
      </div>
    </section>

    <section id="ne-zhelatelno">
      <h2 class="reveal">1. Не желательно</h2>
      
      <div class="rule-block reveal">
        <h3>1. Чрезмерный мат <button class="copy-btn">📋</button></h3>
        <p><strong>Наказание:</strong> Предупреждение.</p>
        <p>Пояснение: Эмоции допустимы, но если каждое второе слово — нецензурное, это мешает чтению. Без прямых оскорблений — не критично, но держите себя в руках.</p>
      </div>

      <div class="rule-block reveal">
        <h3>2. Реклама и ссылки <button class="copy-btn">📋</button></h3>
        <p><strong>Наказание:</strong> Предупреждение.</p>
        <p>Пояснение: Распространение ссылок на сторонние ресурсы без согласования с @lia_os запрещено. Хотите поделиться чем-то полезным? Спросите заранее.</p>
      </div>

      <div class="rule-block reveal">
        <h3>3. Конфликты и ссоры <button class="copy-btn">📋</button></h3>
        <p><strong>Наказание:</strong> Предупреждение/Мут.</p>
        <p>Пояснение: Спор — это нормально. Переход на личности («ты идиот») — нет. Старайтесь гасить конфликты в зачатке.</p>
      </div>

      <div class="rule-block reveal">
        <h3>4. Flash — контент <button class="copy-btn">📋</button></h3>
        <p><strong>Наказание:</strong> Мут.</p>
        <p>Пояснение: Видео с резким мерцанием или скримеры/громкие ГС вредят участникам. Уважайте чужое здоровье.</p>
      </div>

      <div class="rule-block reveal">
        <h3>5. Пересылка личных сообщений <button class="copy-btn">📋</button></h3>
        <p><strong>Наказание:</strong> Предупреждение.</p>
        <p>Пояснение: Сливать ЛС без согласия второй стороны — подло и запрещено. Приватность превыше всего.</p>
      </div>
    </section>

    <section id="zapreshchaetsya">
      <h2 class="reveal">2. Запрещается</h2>

      <div class="rule-block reveal">
        <h3>1. Обсуждение политики <button class="copy-btn">📋</button></h3>
        <p><strong>Наказание: Бан.</strong></p>
        <p>Пояснение: Мы вне политики. Любые обсуждения, споры или политические мемы ведут к немедленному бану без обсуждений.</p>
      </div>

      <div class="rule-block reveal">
        <h3>2. Оскорбления и токсичность <button class="copy-btn">📋</button></h3>
        <p><strong>Наказание:</strong> Мут/Бан.</p>
        <p>Пояснение: Целенаправленная травля или унижение достоинства участников недопустимы. Мы здесь для позитива.</p>
      </div>

      <div class="rule-block reveal">
        <h3>3. NSFW / Треш / Насилие <button class="copy-btn">📋</button></h3>
        <p><strong>Наказание: Бан.</strong></p>
        <p>Пояснение: Порнография, расчлененка, шок-контент — это билет в один конец. Правила платформы и морали прежде всего.</p>
      </div>

      <div class="rule-block reveal">
        <h3>4. Нарушение законов РФ <button class="copy-btn">📋</button></h3>
        <p><strong>Наказание: Бан.</strong></p>
        <p>Пояснение: Пропаганда запрещенных веществ, экстремизм и призывы к насилию запрещены законом и нами.</p>
      </div>

      <div class="rule-block reveal">
        <h3>5. Спам, Флуд, Капс <button class="copy-btn">📋</button></h3>
        <p><strong>Наказание:</strong> Мут.</p>
        <p>Пояснение: Не засоряйте чат бессмысленными повторами. Одно и то же сообщение более 3 раз — это флуд.</p>
      </div>

      <div class="rule-block reveal">
        <h3>6. Дискриминация <button class="copy-btn">📋</button></h3>
        <p><strong>Наказание: Бан.</strong></p>
        <p>Пояснение: Оскорбления по расе, нации, религии или полу — прямая дорога в бан.</p>
      </div>
    </section>

    <section id="moderators">
      <h2 class="reveal">Работа администрации</h2>
      <div class="rule-block reveal">
        <p>1. Модераторы — такие же люди. Они обязаны соблюдать правила.</p>
        <p>2. Перед любым наказанием (кроме тяжелых нарушений) модератор обязан дать <strong>словесное предупреждение</strong>.</p>
        <p>3. Если вы считаете действия модератора несправедливыми — пишите @lia_os.</p>
      </div>
    </section>

    <section id="nakazaniya">
      <h2 class="reveal">Система взысканий</h2>
      <ul class="reveal" style="font-size: 1.1em; line-height: 1.8;">
        <li><strong>Предупреждение:</strong> Желтая карточка. Шанс осознать и остановиться.</li>
        <li><strong>Мут:</strong> Временное лишение права голоса (от 5 мин до 24ч).</li>
        <li><strong>Бан:</strong> Постоянная блокировка за грубые или повторные нарушения.</li>
      </ul>
    </section>

    <div id="no-results" style="display: none; text-align: center; margin: 40px 0; color: var(--accent-light); font-size: 1.2em;">Ничего не найдено. Проверьте запрос.</div>

    <div id="signature" class="reveal" style="text-align: center; margin-top: 80px;">
      <p>by Везунчик</p>
    </div>
  </main>

  <footer>
    <p>Все вопросы и предложения направляйте <strong>@lia_os</strong></p>
    <div id="particles-container" style="height: 150px; position: relative; overflow: hidden; margin-top: 20px;"></div>
  </footer>

  <script>
    // --- 1. ТВОЯ ГЛАВНАЯ АНИМАЦИЯ: ПОЯВЛЕНИЕ И ИСЧЕЗНОВЕНИЕ (Reveal) ---
    // Настраиваем наблюдатель за скроллом
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          // Когда элемент входит в экран (снизу или сверху)
          entry.target.classList.add('visible');
        } else {
          // КЛЮЧЕВОЙ МОМЕНТ: Удаляем класс, когда элемент уходит
          entry.target.classList.remove('visible');
        }
      });
    }, { 
      threshold: 0.15, // Элемент должен быть виден на 15%
      rootMargin: "0px 0px -40px 0px" // Отступ, чтобы анимация срабатывала чуть раньше края
    });

    document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

    // --- 2. ПОИСК С ПОДСВЕТКОЙ (HIGHLIGHT) ---
    const searchInput = document.getElementById('search-input');
    const clearBtn = document.getElementById('clear-button');
    const content = document.getElementById('main-content');

    function removeMarks() {
      content.querySelectorAll('mark').forEach(m => {
        const p = m.parentNode; 
        p.replaceChild(document.createTextNode(m.textContent), m); 
        p.normalize();
      });
    }

    function applyHighlight(term) {
      if (!term) return;
      const regex = new RegExp(`(${term.replace(/[.*+?^${}()|[\]\\]/g, '\\$&')})`, 'gi');
      const walk = (node) => {
        if (node.nodeType === 3) {
          const match = node.data.match(regex);
          if (match) {
            const frag = document.createDocumentFragment();
            let last = 0;
            node.data.replace(regex, (m, offset) => {
              frag.appendChild(document.createTextNode(node.data.slice(last, offset)));
              const mark = document.createElement('mark'); mark.textContent = m;
              frag.appendChild(mark); last = offset + m.length;
            });
            frag.appendChild(document.createTextNode(node.data.slice(last)));
            node.parentNode.replaceChild(frag, node);
          }
        } else if (node.nodeType === 1 && !['SCRIPT','STYLE','MARK','BUTTON'].includes(node.tagName)) {
          Array.from(node.childNodes).forEach(walk);
        }
      };
      walk(content);
    }

    searchInput.addEventListener('input', () => {
      const val = searchInput.value.toLowerCase().trim();
      removeMarks();
      clearBtn.style.display = val ? 'block' : 'none';
      
      let foundAny = false;
      document.querySelectorAll('.rule-block, section, h2, h1, nav, ul').forEach(el => {
        if (el.id === 'no-results') return;
        const text = el.innerText.toLowerCase();
        const has = text.includes(val);
        
        // Показываем/скрываем элементы на основе поиска
        if (val === '') {
          el.style.display = ''; // Сброс
        } else {
          el.style.display = has ? 'block' : 'none';
        }
        
        if (has) foundAny = true;
      });

      if (val) applyHighlight(val);
      document.getElementById('no-results').style.display = (val && !foundAny) ? 'block' : 'none';
    });

    clearBtn.addEventListener('click', () => {
      searchInput.value = '';
      searchInput.dispatchEvent(new Event('input'));
      searchInput.focus();
    });

    // --- 3. КОПИРОВАНИЕ ПРАВИЛ ---
    document.addEventListener('click', e => {
      if (e.target.classList.contains('copy-btn')) {
        const header = e.target.closest('h3');
        const textToCopy = header.innerText.replace('📋', '').trim();
        navigator.clipboard.writeText(textToCopy).then(() => {
          const original = e.target.innerText;
          e.target.innerText = '✔️';
          e.target.style.color = '#4cd137';
          setTimeout(() => { 
            e.target.innerText = original; 
            e.target.style.color = ''; 
          }, 2000);
        });
      }
    });

    // --- 4. ГЕНЕРАЦИЯ ЗВЕЗД В ФУТЕРЕ ---
    const particles = document.getElementById('particles-container');
    for (let i = 0; i < 40; i++) {
      const p = document.createElement('div');
      p.className = 'particle';
      const size = 3 + Math.random() * 6;
      p.style.width = p.style.height = `${size}px`;
      p.style.left = `${Math.random() * 100}%`;
      p.style.top = `${Math.random() * 100}%`;
      p.style.animationDuration = `${2 + Math.random() * 4}s`;
      p.style.animationDelay = `${Math.random() * 5}s`;
      particles.appendChild(p);
    }
  </script>
</body>
</html>
