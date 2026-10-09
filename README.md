<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>BELGER | Próximamente</title>
  <meta name="description" content="BELGER, casa de comida solo delivery en Ensenada, Berisso y La Plata. Entrega en 5 a 15 minutos. Próximamente.">
  <meta name="theme-color" content="#120906">

  <!-- Vista previa al compartir por WhatsApp, Instagram y redes.
       IMPORTANTE: sube belger-preview.png a tu hosting y reemplaza TU-DOMINIO.com por tu dominio real
       (la URL de la imagen debe ser absoluta, con https://). -->
  <meta property="og:type" content="website">
  <meta property="og:locale" content="es_AR">
  <meta property="og:site_name" content="BELGER">
  <meta property="og:title" content="BELGER | Próximamente">
  <meta property="og:description" content="Solo delivery en Ensenada, Berisso y La Plata. Entrega en 5 a 15 minutos. Descuentos y premios para los primeros.">
  <meta property="og:url" content="https://TU-DOMINIO.com/">
  <meta property="og:image" content="https://TU-DOMINIO.com/belger-preview.png">
  <meta property="og:image:width" content="1200">
  <meta property="og:image:height" content="630">
  <meta property="og:image:alt" content="BELGER, próximamente. Delivery en Ensenada, Berisso y La Plata en 5 a 15 minutos.">
  <meta name="twitter:card" content="summary_large_image">

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:opsz,wght@12..96,600;12..96,700&family=Figtree:wght@400;500;600&display=swap" rel="stylesheet">

  <style>
    :root {
      --coal: #120906;        /* fondo: carbón */
      --char: #1E0F08;        /* cortina del loading */
      --ember: #E8431A;       /* brasa */
      --flame: #FF6A1A;       /* llama */
      --amber: #FFB43A;       /* ámbar */
      --amber-deep: #C7500F;  /* sombra de botones */
      --display: "Bricolage Grotesque", system-ui, sans-serif;
      --body: "Figtree", system-ui, sans-serif;
    }
    *, *::before, *::after { box-sizing: border-box; }
    html, body { margin: 0; }
    body { background: var(--coal); color: #fff; font-family: var(--body); line-height: 1.5; -webkit-font-smoothing: antialiased; }
    body.lock { overflow: hidden; }
    :focus-visible { outline: 3px solid var(--amber); outline-offset: 3px; border-radius: 6px; }

    /* Fondo: resplandor de horno encendido */
    .bg { position: fixed; inset: 0; z-index: 0; background:
      radial-gradient(70rem 34rem at 50% 112%, rgba(255,92,20,.42), transparent 70%),
      radial-gradient(38rem 24rem at 8% 100%, rgba(200,40,20,.30), transparent 70%),
      radial-gradient(34rem 22rem at 92% 0%, rgba(255,180,58,.08), transparent 70%),
      var(--coal); }
    .bg::after { content: ""; position: absolute; inset: 0; animation: flicker 4.2s ease-in-out infinite;
      background: radial-gradient(46rem 20rem at 50% 106%, rgba(255,170,50,.30), transparent 70%); }
    @keyframes flicker { 0%, 100% { opacity: .9; } 22% { opacity: 1; } 41% { opacity: .65; } 63% { opacity: .95; } 82% { opacity: .75; } }

    /* Tira de llama reutilizable (divisores y barra de carga) */
    .wood { background: linear-gradient(90deg, #A3200F, #E8431A 28%, #FF8A1F 52%, #FFC13D 76%, #E8431A); }

    /* Logo BYG + nombre */
    .brand { display: inline-flex; align-items: center; gap: .75rem; font-family: var(--display); font-weight: 700; letter-spacing: .08em; font-size: 1.35rem; }
    .logo-mark { --s: 2.75rem; display: grid; place-items: center; width: var(--s); height: var(--s);
      border-radius: calc(var(--s) * .3); background: linear-gradient(160deg, #FFC857, #FF8A1F 62%, #E8431A); color: #2B0F06;
      font-family: var(--display); font-weight: 700; font-size: calc(var(--s) * .37); letter-spacing: .02em;
      box-shadow: inset 0 calc(var(--s) * -.08) 0 var(--amber-deep); }

    /* ========== 1. LOADING ========== */
    .loader { position: fixed; inset: 0; z-index: 100; display: grid; place-items: center; }
    .loader::before, .loader::after { content: ""; position: absolute; top: 0; bottom: 0; width: 50.5%; background: var(--char);
      transition: transform 1s cubic-bezier(.77, 0, .18, 1); }
    .loader::before { left: 0; } .loader::after { right: 0; }
    .loader.done::before { transform: translateX(-101%); }
    .loader.done::after { transform: translateX(101%); }
    .loader-inner { position: relative; z-index: 1; display: flex; flex-direction: column; align-items: center; gap: 1.1rem;
      width: min(22rem, 82vw); text-align: center; transition: opacity .4s; }
    .loader.done .loader-inner { opacity: 0; }
    .loader .logo-mark { --s: 5.5rem; animation: breathe 2.2s ease-in-out infinite; }
    .loader .brand { font-size: 2rem; letter-spacing: .28em; margin-right: -.28em; }
    .track { width: 100%; height: .85rem; border-radius: 999px; background: rgba(255,255,255,.1); overflow: hidden; margin-top: .75rem; }
    .fill { height: 100%; width: 0; border-radius: 999px; }
    .pct { font-family: var(--display); font-weight: 700; font-size: 3.5rem; line-height: 1; font-variant-numeric: tabular-nums; }
    .pct small { font-size: 1.5rem; color: var(--amber); margin-left: .15rem; }
    .status { margin: 0; min-height: 1.5rem; color: rgba(255,255,255,.65); font-size: .95rem; }
    @keyframes breathe { 50% { transform: scale(1.06); } }

    /* ========== 2. FRASES DE MISTERIO ========== */
    .intro { position: fixed; inset: 0; z-index: 50; display: grid; place-items: center; padding: 2rem; text-align: center; transition: opacity .9s; }
    .intro.off { opacity: 0; pointer-events: none; }
    .phrase { max-width: 62rem; }
    .phrase span { display: block; opacity: 0; filter: blur(14px); transform: translateY(16px);
      transition: opacity .8s ease, filter .8s ease, transform .8s ease; }
    .phrase .l1 { font-family: var(--display); font-weight: 700; line-height: 1.05; letter-spacing: -.02em; font-size: clamp(2rem, 1rem + 6vw, 5rem); }
    .phrase .l2 { margin-top: 1.1rem; color: var(--amber); font-weight: 500; font-size: clamp(1.15rem, .8rem + 1.6vw, 1.9rem); transition-delay: .35s; }
    .phrase.in span { opacity: 1; filter: none; transform: none; }
    .skip { position: fixed; left: 50%; bottom: 1.5rem; translate: -50% 0; visibility: hidden; background: none; border: 0; cursor: pointer;
      color: rgba(255,255,255,.65); font: 500 .95rem var(--body); text-decoration: underline; text-underline-offset: 4px; padding: .5rem 1rem; }
    .skip:hover { color: #fff; }
    .intro.live .skip { visibility: visible; }

    /* ========== 3. LANDING DE PRE-APERTURA ========== */
    .landing { position: relative; z-index: 1; min-height: 100svh; display: flex; flex-direction: column; align-items: center;
      justify-content: center; padding: 3.5rem 1.25rem 2rem; text-align: center; }
    .landing > * { opacity: 0; transform: translateY(20px); transition: opacity .9s ease, transform .9s ease; transition-delay: calc(var(--i, 0) * .14s); }
    body.show .landing > * { opacity: 1; transform: none; }

    h1 { margin: 2rem 0 0; font-family: var(--display); font-weight: 700; line-height: 1; letter-spacing: -.03em; font-size: clamp(2.2rem, .5rem + 8vw, 6.5rem); }
    .tagline { margin: 1.1rem 0 0; font-family: var(--display); font-weight: 600; letter-spacing: -.01em; font-size: clamp(1.3rem, 1rem + 1.8vw, 2.2rem); color: var(--amber); }
    .plank { width: 6rem; height: .5rem; border-radius: 999px; margin: 1.6rem auto 0; }
    .lead { max-width: 36rem; margin: 1.6rem 0 0; font-size: 1.15rem; line-height: 1.7; color: rgba(255,255,255,.78); }
    .zones { display: flex; flex-wrap: wrap; justify-content: center; gap: .6rem; margin: 1.75rem 0 0; padding: 0; list-style: none; }
    .zones li { display: flex; align-items: center; gap: .5rem; padding: .55rem 1.1rem; border: 1px solid rgba(255,255,255,.25); border-radius: 999px; font-weight: 600; }
    .zones li::before { content: ""; width: .5rem; height: .5rem; border-radius: 50%; background: var(--flame); box-shadow: 0 0 0 4px rgba(255,106,26,.28); }

    .countdown { display: flex; gap: .75rem; margin-top: 2.25rem; }
    .countdown[hidden] { display: none; }
    .countdown div { min-width: 4.5rem; padding: .75rem .5rem; border-radius: 1rem; background: rgba(255,255,255,.07); border: 1px solid rgba(255,255,255,.12); }
    .countdown b { display: block; font-family: var(--display); font-size: 2rem; line-height: 1; font-variant-numeric: tabular-nums; }
    .countdown span { font-size: .8rem; color: rgba(255,255,255,.6); }

    /* Tiempo de entrega */
    .speed { display: flex; flex-wrap: wrap; justify-content: center; align-items: center; gap: .6rem 1.1rem; margin-top: 2rem; padding: 1rem 1.6rem 1rem 1.2rem; border-radius: 1.25rem;
      background: rgba(255,106,26,.12); border: 1px solid rgba(255,106,26,.5); text-align: left; }
    .speed b { font-family: var(--display); font-size: clamp(2rem, 1.2rem + 3vw, 2.9rem); line-height: 1; white-space: nowrap; }
    .speed span { font-size: 1rem; line-height: 1.35; color: rgba(255,255,255,.8); max-width: 12rem; }

    /* Botones */
    .actions { display: flex; flex-wrap: wrap; justify-content: center; gap: 1rem 1.1rem; margin-top: 2.25rem; }
    .btn { display: inline-flex; align-items: center; gap: .6rem; padding: 1.05rem 2.2rem; border-radius: 999px; background: linear-gradient(180deg, #FFC54D, #FF8F1F); color: #2B0F06;
      font-size: 1.15rem; font-weight: 700; text-decoration: none; box-shadow: 0 8px 0 var(--amber-deep); transition: transform .15s, box-shadow .15s; }
    .btn:hover { transform: translateY(2px); box-shadow: 0 6px 0 var(--amber-deep); }
    .btn:active { transform: translateY(8px); box-shadow: none; }
    .btn { justify-content: center; }
    .btn-wide { max-width: 34rem; border-radius: 1.6rem; text-align: center; line-height: 1.35; }
    .btn svg { flex: none; }
    @media (max-width: 480px) { .btn { padding: 1rem 1.3rem; font-size: 1.05rem; } }
    .perk { max-width: 30rem; margin: 1.6rem 0 0; font-size: 1rem; line-height: 1.6; color: var(--amber); font-weight: 500; }

    /* Secciones internas */
    .block { width: min(44rem, 100%); margin-top: 4.5rem; }
    .block h2 { margin: 0; font-family: var(--display); font-weight: 700; letter-spacing: -.02em; line-height: 1.1; font-size: clamp(1.8rem, 1.2rem + 2.4vw, 2.6rem); }
    .block > p { margin: 1rem auto 0; max-width: 34rem; line-height: 1.7; color: rgba(255,255,255,.75); }

    /* Menú: lo que ya contamos + lo que viene */
    .secret { width: min(26rem, 100%); margin: 0 auto; padding: 1.25rem 1.5rem; border: 1px dashed rgba(255,180,58,.55); border-radius: 1.25rem; background: rgba(255,255,255,.04); text-align: left; }
    .secret-head { display: flex; align-items: center; gap: .6rem; font-family: var(--display); font-weight: 600; font-size: 1.1rem; }
    .secret-head svg { color: var(--amber); flex: none; }
    .secret-head em { margin-left: auto; font-style: normal; font-family: var(--body); font-size: .8rem; font-weight: 600; color: var(--amber); }
    .secret dl { margin: 1rem 0 0; display: grid; gap: .7rem; }
    .secret dl div { display: flex; align-items: center; gap: 1rem; }
    .secret dt { flex: none; width: 5.5rem; font-size: .9rem; color: rgba(255,255,255,.6); }
    .secret dd { margin: 0; width: calc((100% - 6.5rem) * var(--w, .7)); height: .95rem; border-radius: 4px; background: rgba(255,255,255,.88); }
    .secret p { margin: 1rem 0 0; font-size: .95rem; color: rgba(255,255,255,.75); }
    .secret p a { color: var(--amber); font-weight: 600; }

    /* Historia del nombre */
    .formula { display: flex; flex-wrap: wrap; align-items: center; justify-content: center; gap: .8rem; margin-top: 1.8rem; font-family: var(--display); font-weight: 700; }
    .formula span { padding: .6rem 1.2rem; border-radius: 1rem; background: rgba(255,255,255,.08); border: 1px solid rgba(255,255,255,.18); font-size: clamp(1.4rem, 1rem + 2vw, 2.1rem); }
    .formula i { font-style: normal; font-size: 1.6rem; color: var(--amber); }
    .formula .res { background: var(--amber); color: #2B0F06; border-color: var(--amber); }
    .byg { margin: 1.4rem auto 0; max-width: 32rem; font-size: .95rem; color: rgba(255,255,255,.65); }

    .foot { width: 100%; max-width: 64rem; margin-top: 4rem; font-size: .9rem; color: rgba(255,255,255,.65); }
    .foot .wood { height: .5rem; border-radius: 999px; margin-bottom: 1.25rem; }
    .foot p { margin: .15rem 0; }
    .foot a { color: inherit; }
    .foot a:hover { color: #fff; }

    @media (prefers-reduced-motion: reduce) {
      *, *::before, *::after { animation: none !important; transition-duration: .01ms !important; transition-delay: 0s !important; }
    }
  </style>
  <noscript><style>.loader, .intro { display: none; } .landing > * { opacity: 1; transform: none; } body.lock { overflow: auto; }</style></noscript>
</head>

<body class="lock">
  <div class="bg" aria-hidden="true"></div>

  <!-- ========== 1. LOADING ========== -->
  <div id="loader" class="loader">
    <div class="loader-inner">
      <span class="logo-mark" aria-hidden="true">BYG</span>
      <span class="brand">BELGER</span>
      <div id="bar" class="track" role="progressbar" aria-label="Cargando" aria-valuemin="0" aria-valuemax="100" aria-valuenow="0">
        <div id="fill" class="fill wood"></div>
      </div>
      <div class="pct"><span id="pct">0</span><small>%</small></div>
      <p id="status" class="status">Encendiendo la cocina</p>
    </div>
  </div>

  <!-- ========== 2. FRASES DE MISTERIO ========== -->
  <div id="intro" class="intro">
    <div id="phrase" class="phrase" aria-live="polite">
      <span id="l1" class="l1"></span>
      <span id="l2" class="l2"></span>
    </div>
    <button id="skip" class="skip" type="button">Saltar intro</button>
  </div>

  <!-- ========== 3. LANDING ========== -->
  <main id="landing" class="landing">
    <div class="brand" style="--i:0">
      <span class="logo-mark" aria-hidden="true">BYG</span>
      BELGER
    </div>

    <h1 style="--i:1">Próximamente</h1>
    <p class="tagline" style="--i:2">El horno ya está encendido.</p>
    <div class="plank wood" style="--i:2" aria-hidden="true"></div>

    <p class="lead" style="--i:3">
      La nueva casa de comida solo delivery. Sin mesas y sin salón: cocinamos y el sabor va directo hasta tu puerta.
    </p>

    <div class="speed" style="--i:4">
      <b>5 a 15 min</b>
      <span>desde que hacés tu pedido hasta que llega a tu puerta</span>
    </div>

    <ul class="zones" style="--i:5" aria-label="Zonas de entrega">
      <li>Ensenada</li>
      <li>Berisso</li>
      <li>La Plata</li>
    </ul>

    <!-- Para activar la cuenta regresiva, define OPENING_DATE en el script -->
    <div id="countdown" class="countdown" style="--i:6" hidden aria-label="Cuenta regresiva para la apertura">
      <div><b>00</b><span>días</span></div>
      <div><b>00</b><span>horas</span></div>
      <div><b>00</b><span>min</span></div>
      <div><b>00</b><span>seg</span></div>
    </div>

    <!-- Los enlaces se completan solos con los datos de WHATSAPP e INSTAGRAM del script -->
    <div class="actions" style="--i:7">
      <a data-ig href="#" class="btn btn-wide">
        <svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><rect x="3" y="3" width="18" height="18" rx="5"/><circle cx="12" cy="12" r="4"/><path d="M17.5 6.5h.01"/></svg>
        <span>Seguinos para ser uno de los primeros en enterarse de todas las novedades, promociones y la más esperada: la apertura de nuestra casa de comida</span>
      </a>
    </div>
    <p class="perk" style="--i:8">Seguinos para más detalles y sorpresas.</p>

    <!-- Menú -->
    <section class="block" style="--i:9" aria-label="Lo que viene">
      <div class="secret" aria-label="Más platos en camino, confidencial">
        <div class="secret-head">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><rect x="4" y="11" width="16" height="10" rx="2"/><path d="M8 11V8a4 4 0 0 1 8 0v3"/></svg>
          Lo que viene
          <em>Confidencial</em>
        </div>
        <dl aria-hidden="true">
          <div><dt>Nuevo</dt><dd style="--w:.72"></dd></div>
          <div><dt>Nuevo</dt><dd style="--w:.9"></dd></div>
          <div><dt>Nuevo</dt><dd style="--w:.56"></dd></div>
        </dl>
        <p>Próximamente, más información por nuestro <a data-ig href="#">Instagram</a>.</p>
      </div>
    </section>

    <!-- Historia del nombre -->
    <section class="block" style="--i:10" aria-labelledby="t-name">
      <h2 id="t-name">Por qué nos llamamos BELGER</h2>
      <div class="formula" role="img" aria-label="BEL más GER es igual a BELGER">
        <span>BEL</span><i>+</i><span>GER</span><i>=</i><span class="res">BELGER</span>
      </div>
      <p>
        Pasamos días pensando marcas y nombres, y la semana se nos fue entre ideas. Hasta que a Ger, junto a Bel, se le prendió la lamparita: ¿y si juntábamos los dos nombres en uno solo? Así nació BELGER, con las tres primeras letras del nombre de cada dueño.
      </p>
      <p class="byg">Y BYG, el logo, es la firma de los dos: B y G.</p>
    </section>

    <footer class="foot" style="--i:11">
      <div class="wood" aria-hidden="true"></div>
      <p><a data-wa href="#">WhatsApp</a> <a data-ig href="#" style="margin-left:1.2rem">Instagram</a></p>
      <p>© 2026 BELGER. Delivery en Ensenada, Berisso y La Plata.</p>
    </footer>
  </main>

  <script>
    (() => {
      const $ = s => document.querySelector(s);
      const sleep = ms => new Promise(r => setTimeout(r, ms));
      const reduce = matchMedia('(prefers-reduced-motion: reduce)').matches;

      // Pon aquí la fecha de apertura para mostrar la cuenta regresiva. Ej: '2026-11-20T20:00:00-03:00'
      const OPENING_DATE = null;

      // Tus contactos: completá estos datos y los botones se actualizan solos
      const WHATSAPP = '549221XXXXXXX';   // número con código de país, sin + ni espacios (ej: 5492215551234)
      const INSTAGRAM = 'tu_usuario';     // usuario de Instagram, sin @
      const WA_MENSAJE = 'Hola BELGER! Quiero ser de los primeros en enterarme de la apertura y del descuento.';
      document.querySelectorAll('[data-wa]').forEach(a => {
        a.href = 'https://wa.me/' + WHATSAPP + '?text=' + encodeURIComponent(WA_MENSAJE);
        a.target = '_blank'; a.rel = 'noopener';
      });
      document.querySelectorAll('[data-ig]').forEach(a => {
        a.href = 'https://instagram.com/' + INSTAGRAM;
        a.target = '_blank'; a.rel = 'noopener';
      });

      // Frases que aparecen cuando el loading llega al 100%
      const phrases = [
        ['Algo se está cocinando.', 'Y todavía no te vamos a decir qué.'],
        ['Sin mesas. Sin salón. Sin cola.', 'Solo una cocina que no para.'],
        ['Cuando abramos, no vas a venir a nosotros.', 'Vamos a ir nosotros a vos.'],
        ['Ensenada. Berisso. La Plata.', 'Tres ciudades. Una sola cocina.']
      ];
      const states = [[0, 'Encendiendo la cocina'], [30, 'Afilando los cuchillos'], [60, 'Eligiendo ingredientes'], [90, 'Casi listo']];

      const loader = $('#loader'), pct = $('#pct'), fill = $('#fill'), bar = $('#bar'), statusEl = $('#status');
      const intro = $('#intro'), phrase = $('#phrase'), l1 = $('#l1'), l2 = $('#l2'), skip = $('#skip'), landing = $('#landing');
      let ready = false, skipped = false, shown = false;

      landing.inert = true;
      Promise.all([
        document.fonts ? document.fonts.ready : null,
        new Promise(r => document.readyState === 'complete' ? r() : addEventListener('load', r))
      ]).then(() => ready = true);
      setTimeout(() => ready = true, 5000); // si la conexión es lenta, no esperamos más de 5 segundos

      // --- Loading ---
      const DUR = reduce ? 300 : 3600, t0 = performance.now();
      function setProgress(p) {
        pct.textContent = p;
        fill.style.width = p + '%';
        bar.setAttribute('aria-valuenow', p);
        statusEl.textContent = states.filter(s => p >= s[0]).pop()[1];
      }
      function tick(now) {
        const x = Math.max(0, Math.min((now - t0) / DUR, 1));
        let p = Math.floor(100 * (1 - Math.pow(1 - x, 2)));
        if (!ready) p = Math.min(p, 99);
        setProgress(p);
        p < 100 ? requestAnimationFrame(tick) : finish();
      }
      requestAnimationFrame(tick);

      async function finish() {
        await sleep(reduce ? 0 : 600);
        loader.classList.add('done');            // la cortina se abre
        await sleep(reduce ? 0 : 1000);
        loader.remove();
        reduce ? showLanding() : runIntro();
      }

      // --- Frases ---
      async function runIntro() {
        intro.classList.add('live');
        for (const [a, b] of phrases) {
          if (skipped) return;
          l1.textContent = a; l2.textContent = b;
          phrase.classList.add('in');
          await sleep(2700);
          if (skipped) return;
          phrase.classList.remove('in');
          await sleep(900);
        }
        showLanding();
      }
      skip.addEventListener('click', () => { skipped = true; showLanding(); });

      function showLanding() {
        if (shown) return;
        shown = true;
        intro.classList.add('off');
        intro.inert = true;
        landing.inert = false;
        document.body.classList.remove('lock');
        document.body.classList.add('show');
        scrollTo(0, 0);
      }

      // --- Cuenta regresiva (opcional) ---
      if (OPENING_DATE) {
        const box = $('#countdown'), target = new Date(OPENING_DATE).getTime();
        box.hidden = false;
        const update = () => {
          const s = Math.max(0, Math.floor((target - Date.now()) / 1000));
          const v = [Math.floor(s / 86400), Math.floor(s % 86400 / 3600), Math.floor(s % 3600 / 60), s % 60];
          box.querySelectorAll('b').forEach((b, i) => b.textContent = String(v[i]).padStart(2, '0'));
        };
        update(); setInterval(update, 1000);
      }
    })();
  </script>
</body>
</html>
