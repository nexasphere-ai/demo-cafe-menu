<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Brew &amp; Bloom · Menu</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600&family=Fraunces:opsz,wght@9..144,500;9..144,600&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #F6F9F6;
    --surface: #FFFFFF;
    --ink: #17332D;
    --muted: #5A6F68;
    --line: #DCE6E0;
    --bloom: #E58FA3;
    --bloom-soft: #FBE3E8;
    --veg: #2C7A57;
    --nonveg: #B3382C;
    --fill: #17332D;
    --on-fill: #FFFFFF;
    --t-coffee: #E2EDE5;
    --t-cold: #E0EDF5;
    --t-snacks: #F6EACB;
    --t-dessert: #F9E0E6;
    --shadow: 0 10px 30px rgba(23, 51, 45, 0.16);
    box-sizing: border-box;
    padding-top: env(safe-area-inset-top, 0px);
    padding-bottom: env(safe-area-inset-bottom, 0px);
  }
  @media (prefers-color-scheme: dark) {
    :root:not([data-theme="light"]) {
      --bg: #0F1D1A; --surface: #172A26; --ink: #EAF3EE; --muted: #9DB3AA; --line: #29403A;
      --bloom: #EE9FB1; --bloom-soft: #3A2A30; --veg: #52C08D; --nonveg: #EE7A6C;
      --fill: #EAF3EE; --on-fill: #0F1D1A;
      --t-coffee: #21372F; --t-cold: #1F3340; --t-snacks: #3E3822; --t-dessert: #402A33;
      --shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
    }
  }
  :root[data-theme="dark"] {
    --bg: #0F1D1A; --surface: #172A26; --ink: #EAF3EE; --muted: #9DB3AA; --line: #29403A;
    --bloom: #EE9FB1; --bloom-soft: #3A2A30; --veg: #52C08D; --nonveg: #EE7A6C;
    --fill: #EAF3EE; --on-fill: #0F1D1A;
    --t-coffee: #21372F; --t-cold: #1F3340; --t-snacks: #3E3822; --t-dessert: #402A33;
    --shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
  }

  html { scroll-padding-top: env(safe-area-inset-top, 0px); }
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body {
    background: var(--bg);
    color: var(--ink);
    font-family: 'DM Sans', system-ui, -apple-system, 'Segoe UI', Roboto, sans-serif;
    -webkit-font-smoothing: antialiased;
    line-height: 1.45;
  }
  .page { max-width: 560px; margin: 0 auto; padding: 0 18px 120px; }
  button { font: inherit; color: inherit; cursor: pointer; border: 0; background: none; }
  :focus-visible { outline: 3px solid var(--bloom); outline-offset: 2px; border-radius: 8px; }

  /* Header */
  .hero { padding: 30px 0 18px; display: flex; justify-content: space-between; align-items: flex-start; gap: 12px; }
  .hero h1 {
    font-family: 'Fraunces', Georgia, 'Times New Roman', serif;
    font-weight: 600; font-size: 42px; line-height: 1.05; letter-spacing: -0.01em;
  }
  .hero p { margin-top: 10px; color: var(--muted); font-size: 16px; max-width: 30ch; }
  .bloom { flex: 0 0 auto; width: 104px; height: 104px; }
  .chips { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 16px; }
  .chip {
    font-size: 13.5px; font-weight: 500; padding: 6px 12px; border-radius: 999px;
    background: var(--surface); border: 1px solid var(--line); color: var(--ink);
  }
  .chip.table { background: var(--bloom-soft); border-color: transparent; }

  /* Tools */
  .tools { margin-top: 18px; display: flex; gap: 10px; align-items: center; }
  .search {
    flex: 1; display: flex; align-items: center; gap: 10px;
    background: var(--surface); border: 1px solid var(--line); border-radius: 14px; padding: 0 14px;
  }
  .search svg { flex: 0 0 18px; color: var(--muted); }
  .search input {
    flex: 1; min-width: 0; border: 0; background: transparent; color: var(--ink);
    font: inherit; font-size: 16px; padding: 13px 0; outline: none;
  }
  .search:focus-within { border-color: var(--bloom); box-shadow: 0 0 0 3px var(--bloom-soft); }
  .vegtoggle {
    display: flex; align-items: center; gap: 8px; padding: 11px 14px; border-radius: 14px;
    background: var(--surface); border: 1px solid var(--line); font-size: 14px; font-weight: 500; white-space: nowrap;
  }
  .vegtoggle[aria-pressed="true"] { background: var(--veg); border-color: var(--veg); color: #FFFFFF; }
  .vegtoggle[aria-pressed="true"] .vm { border-color: #FFFFFF; }
  .vegtoggle[aria-pressed="true"] .vm::after { background: #FFFFFF; }

  /* Veg marker */
  .vm { display: inline-block; width: 15px; height: 15px; border: 1.6px solid var(--veg); border-radius: 3px; position: relative; flex: 0 0 15px; }
  .vm::after { content: ''; position: absolute; inset: 3px; border-radius: 50%; background: var(--veg); }
  .vm.nv { border-color: var(--nonveg); }
  .vm.nv::after { background: var(--nonveg); }

  /* Tabs */
  .tabs {
    position: sticky; top: env(safe-area-inset-top, 0px); z-index: 20;
    margin: 16px -18px 0; padding: 10px 18px;
    background: var(--bg); border-bottom: 1px solid var(--line);
    display: flex; gap: 8px; overflow-x: auto; scrollbar-width: none;
  }
  .tabs::-webkit-scrollbar { display: none; }
  .tab {
    flex: 0 0 auto; padding: 9px 16px; border-radius: 999px; font-size: 15px; font-weight: 500;
    background: var(--surface); border: 1px solid var(--line);
  }
  .tab[aria-current="true"] { background: var(--fill); color: var(--on-fill); border-color: var(--fill); }

  /* Sections */
  section { padding-top: 26px; scroll-margin-top: 64px; }
  section h2 { font-family: 'Fraunces', Georgia, serif; font-weight: 600; font-size: 25px; letter-spacing: -0.005em; }
  section .note { color: var(--muted); font-size: 14px; margin-top: 2px; }
  .items { margin-top: 12px; display: flex; flex-direction: column; gap: 12px; }

  .item {
    display: grid; grid-template-columns: 76px 1fr; gap: 14px;
    background: var(--surface); border: 1px solid var(--line); border-radius: 20px; padding: 12px;
  }
  .tile { width: 76px; height: 76px; border-radius: 16px; display: grid; place-items: center; font-size: 36px; }
  .body { min-width: 0; display: flex; flex-direction: column; }
  .nm { display: flex; align-items: center; gap: 8px; font-weight: 600; font-size: 16.5px; }
  .ds { color: var(--muted); font-size: 14px; margin-top: 3px; }
  .best {
    display: inline-block; align-self: flex-start; margin-top: 6px; font-size: 12.5px; font-weight: 600;
    padding: 2px 9px; border-radius: 999px; background: var(--bloom-soft);
  }
  .row { display: flex; align-items: center; justify-content: space-between; margin-top: auto; padding-top: 10px; }
  .pr { font-weight: 600; font-size: 17px; }
  .add {
    padding: 8px 20px; border-radius: 999px; font-weight: 600; font-size: 14.5px;
    border: 1.5px solid var(--fill);
  }
  .step { display: flex; align-items: center; background: var(--fill); color: var(--on-fill); border-radius: 999px; }
  .step button { width: 36px; height: 34px; font-size: 20px; font-weight: 500; line-height: 1; }
  .step span { min-width: 22px; text-align: center; font-weight: 600; font-size: 15px; }
  .empty { display: none; text-align: center; color: var(--muted); padding: 44px 0 10px; }

  /* Review card + footer */
  .review {
    margin-top: 34px; border-radius: 24px; padding: 22px; background: var(--bloom-soft);
  }
  .review h3 { font-family: 'Fraunces', Georgia, serif; font-size: 22px; font-weight: 600; }
  .review p { margin-top: 4px; color: var(--muted); font-size: 15px; }
  .review .btn {
    margin-top: 14px; display: inline-block; background: var(--fill); color: var(--on-fill);
    padding: 12px 20px; border-radius: 999px; font-weight: 600; font-size: 15px;
  }
  .powered { margin-top: 30px; padding-top: 22px; border-top: 1px solid var(--line); text-align: center; color: var(--muted); font-size: 13.5px; }
  .powered img { height: 52px; width: auto; display: block; margin: 0 auto 8px; filter: none; }
  :root[data-theme="dark"] .powered img { filter: invert(1) hue-rotate(180deg); }
  @media (prefers-color-scheme: dark) { :root:not([data-theme="light"]) .powered img { filter: invert(1) hue-rotate(180deg); } }
  .powered a { color: var(--ink); font-weight: 600; text-underline-offset: 3px; }

  /* Order bar + sheet */
  .bar {
    position: fixed; left: 0; right: 0; bottom: 0; z-index: 30;
    padding: 12px 18px calc(12px + env(safe-area-inset-bottom, 0px));
    display: none; pointer-events: none;
  }
  .bar.show { display: block; }
  .bar button {
    pointer-events: auto; display: flex; justify-content: space-between; align-items: center;
    width: 100%; max-width: 524px; margin: 0 auto; padding: 16px 22px; border-radius: 999px;
    background: var(--fill); color: var(--on-fill); font-weight: 600; font-size: 16px; box-shadow: var(--shadow);
  }
  .scrim { position: fixed; inset: 0; background: rgba(10, 20, 17, 0.5); z-index: 40; }
  .sheet {
    position: fixed; left: 0; right: 0; bottom: 0; z-index: 50;
    max-width: 560px; margin: 0 auto; max-height: 86%; overflow-y: auto;
    background: var(--surface); border-radius: 26px 26px 0 0;
    padding: 22px 20px calc(22px + env(safe-area-inset-bottom, 0px));
    animation: up .22s ease-out;
  }
  @keyframes up { from { transform: translateY(24px); opacity: .4; } to { transform: none; opacity: 1; } }
  @media (prefers-reduced-motion: reduce) { .sheet { animation: none; } }
  [hidden] { display: none !important; }
  .sheet h3 { font-family: 'Fraunces', Georgia, serif; font-size: 24px; font-weight: 600; }
  .sheet .tbl { color: var(--muted); font-size: 14px; margin-top: 2px; }
  .lines { margin-top: 12px; }
  .line { display: flex; align-items: center; justify-content: space-between; gap: 10px; padding: 12px 0; border-bottom: 1px solid var(--line); }
  .line .ln { font-weight: 500; }
  .line .lp { color: var(--muted); font-size: 14px; }
  .sheet .tot { display: flex; justify-content: space-between; font-weight: 600; font-size: 18px; padding: 16px 0 6px; }
  .sheet textarea {
    width: 100%; margin-top: 8px; border: 1px solid var(--line); border-radius: 14px; padding: 12px;
    background: var(--bg); color: var(--ink); font: inherit; font-size: 15px; resize: none; min-height: 64px;
  }
  .send {
    margin-top: 14px; display: block; text-align: center; text-decoration: none;
    background: var(--fill); color: var(--on-fill); padding: 15px; border-radius: 999px; font-weight: 600; font-size: 16px;
  }
  .hint { text-align: center; color: var(--muted); font-size: 13px; margin-top: 10px; }
  .close { position: absolute; top: 16px; right: 16px; width: 36px; height: 36px; border-radius: 50%; background: var(--bg); font-size: 20px; }
  .toast {
    position: fixed; left: 50%; transform: translateX(-50%); bottom: calc(96px + env(safe-area-inset-bottom, 0px)); z-index: 60;
    background: var(--fill); color: var(--on-fill); padding: 12px 18px; border-radius: 14px; font-size: 14px; max-width: 86%; text-align: center;
    box-shadow: var(--shadow);
  }
</style>
</head>
<body>
<div class="page">

  <header class="hero">
    <div>
      <h1>Brew &amp; Bloom</h1>
      <p>Coffee, small plates and slow afternoons.</p>
      <div class="chips">
        <span class="chip">Open 8 am to 11 pm</span>
        <span class="chip table" id="tableChip" hidden></span>
        <span class="chip">Sample menu</span>
      </div>
    </div>
    <svg class="bloom" viewBox="0 0 120 120" aria-hidden="true">
      <g transform="translate(60 60)">
        <g fill="#E58FA3">
          <ellipse cx="0" cy="-32" rx="15" ry="26" />
          <ellipse cx="0" cy="-32" rx="15" ry="26" transform="rotate(72)" />
          <ellipse cx="0" cy="-32" rx="15" ry="26" transform="rotate(144)" />
          <ellipse cx="0" cy="-32" rx="15" ry="26" transform="rotate(216)" />
          <ellipse cx="0" cy="-32" rx="15" ry="26" transform="rotate(288)" />
        </g>
        <ellipse cx="0" cy="0" rx="17" ry="22" fill="#2B1A12" transform="rotate(-24)" />
        <path d="M-5 -19 C 6 -8, -6 6, 5 19" fill="none" stroke="#F6E7D8" stroke-width="3" stroke-linecap="round" transform="rotate(-24)" />
      </g>
    </svg>
  </header>

  <div class="tools">
    <label class="search">
      <svg viewBox="0 0 24 24" width="18" height="18" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><circle cx="11" cy="11" r="7"/><path d="M20 20l-3.5-3.5"/></svg>
      <input id="q" type="search" placeholder="Search the menu" autocomplete="off" aria-label="Search the menu">
    </label>
    <button class="vegtoggle" id="veg" aria-pressed="false"><span class="vm"></span>Veg</button>
  </div>

  <nav class="tabs" id="tabs" aria-label="Menu categories"></nav>

  <main id="menu"></main>
  <p class="empty" id="empty">Nothing matches that search. Try another word.</p>

  <div class="review">
    <h3>Enjoyed your visit?</h3>
    <p>A quick Google review helps a small café more than you would think.</p>
    <button class="btn" id="reviewBtn">Leave a Google review</button>
  </div>

  <div class="powered">
    <img alt="Nexa Sphere" src="nexasphere-logo.png">
    Sample menu made by <a href="https://nexasphere-digital-craft.lovable.app/" target="_blank" rel="noopener">Nexa Sphere</a>.<br>
    Brew &amp; Bloom is a fictional café.
  </div>
</div>

<div class="bar" id="bar">
  <button id="barBtn"><span id="barInfo"></span><span>View order</span></button>
</div>

<div class="scrim" id="scrim" hidden></div>
<div class="sheet" id="sheet" role="dialog" aria-modal="true" aria-labelledby="sheetTitle" hidden>
  <button class="close" id="closeSheet" aria-label="Close order">×</button>
  <h3 id="sheetTitle">Your order</h3>
  <div class="tbl" id="sheetTable"></div>
  <div class="lines" id="lines"></div>
  <div class="tot"><span>Total</span><span id="total"></span></div>
  <textarea id="note" placeholder="Anything the kitchen should know? (optional)" aria-label="Note for the kitchen"></textarea>
  <a class="send" id="send" href="#" target="_blank" rel="noopener">Send order on WhatsApp</a>
  <p class="hint">Opens WhatsApp with your order ready to send. Pay at the counter.</p>
</div>

<div class="toast" id="toast" role="status" hidden></div>

<script>
(function () {
  var MENU = [
    { id: 'coffee', name: 'Coffee', note: 'Roasted in small batches', tile: 't-coffee', items: [
      { n: 'Filter coffee', d: 'South Indian style, strong and frothy', p: 120, v: 1, e: '☕', best: 1 },
      { n: 'Cappuccino', d: 'Double shot, silky steamed milk', p: 170, v: 1, e: '☕' },
      { n: 'Flat white', d: 'Velvety, ristretto based', p: 190, v: 1, e: '☕' },
      { n: 'Cold coffee', d: 'Slow brewed, blended with vanilla ice cream', p: 190, v: 1, e: '🥤' },
      { n: 'Hazelnut latte', d: 'Toasted hazelnut, espresso, warm milk', p: 220, v: 1, e: '☕' }
    ]},
    { id: 'cold', name: 'Cold and fresh', note: 'Made to order', tile: 't-cold', items: [
      { n: 'Iced lemon tea', d: 'Black tea, fresh lemon, mint', p: 140, v: 1, e: '🍋' },
      { n: 'Blueberry cooler', d: 'Blueberry, lime and sparkling water', p: 180, v: 1, e: '🫐' },
      { n: 'Virgin mojito', d: 'Mint, lime and a little sugar', p: 170, v: 1, e: '🍃' },
      { n: 'Rose milk soda', d: 'Our signature bloom drink', p: 150, v: 1, e: '🌹', best: 1 }
    ]},
    { id: 'snacks', name: 'Small plates', note: 'Good with coffee, better with friends', tile: 't-snacks', items: [
      { n: 'Paneer tikka sandwich', d: 'Grilled paneer, mint chutney, toasted sourdough', p: 220, v: 1, e: '🥪' },
      { n: 'Chicken pesto panini', d: 'Basil pesto, mozzarella, grilled chicken', p: 260, v: 0, e: '🥖' },
      { n: 'Peri peri fries', d: 'Crisp fries with house peri peri dust', p: 160, v: 1, e: '🍟', best: 1 },
      { n: 'Cheesy garlic bread', d: 'Butter, roasted garlic, molten cheese', p: 180, v: 1, e: '🧄' },
      { n: 'Loaded veg nachos', d: 'Beans, jalapeño, cheese sauce, salsa', p: 240, v: 1, e: '🌮' },
      { n: 'Omelette toast', d: 'Masala omelette on buttered toast', p: 170, v: 0, e: '🍳' }
    ]},
    { id: 'desserts', name: 'Desserts', note: 'Baked fresh every morning', tile: 't-dessert', items: [
      { n: 'Walnut brownie', d: 'Warm, fudgy, with a scoop of vanilla', p: 190, v: 1, e: '🍫', best: 1 },
      { n: 'Blueberry cheesecake', d: 'Baked, with a biscuit base', p: 240, v: 1, e: '🍰' },
      { n: 'Tiramisu jar', d: 'Coffee soaked sponge, mascarpone cream', p: 230, v: 1, e: '🍮' },
      { n: 'Rose petal cake slice', d: 'Light sponge, rose cream, pistachio', p: 210, v: 1, e: '🌸' }
    ]}
  ];

  var cart = {};           // key -> qty
  var byKey = {};
  var q = '', vegOnly = false;

  function inr(n) { return '₹' + n.toLocaleString('en-IN'); }
  function $(id) { return document.getElementById(id); }

  // Table number from ?table=7
  var table = null;
  try {
    var t = new URLSearchParams(location.search).get('table');
    if (t && /^[A-Za-z0-9 -]{1,6}$/.test(t)) table = t;
  } catch (e) {}
  if (table) { $('tableChip').textContent = 'Table ' + table; $('tableChip').hidden = false; }

  // Build menu
  var menuEl = $('menu'), tabsEl = $('tabs');
  MENU.forEach(function (c) {
    var tab = document.createElement('button');
    tab.className = 'tab'; tab.textContent = c.name; tab.dataset.target = c.id;
    tabsEl.appendChild(tab);

    var sec = document.createElement('section');
    sec.id = c.id;
    sec.innerHTML = '<h2>' + c.name + '</h2><p class="note">' + c.note + '</p><div class="items"></div>';
    var list = sec.querySelector('.items');

    c.items.forEach(function (it, i) {
      var key = c.id + '-' + i;
      it.key = key; it.cat = c.id; byKey[key] = it;
      var el = document.createElement('article');
      el.className = 'item'; el.dataset.key = key;
      el.dataset.text = (it.n + ' ' + it.d).toLowerCase();
      el.dataset.veg = it.v ? '1' : '0';
      el.innerHTML =
        '<div class="tile" style="background:var(--' + c.tile + ')" aria-hidden="true">' + it.e + '</div>' +
        '<div class="body">' +
          '<div class="nm"><span class="vm' + (it.v ? '' : ' nv') + '" title="' + (it.v ? 'Vegetarian' : 'Non-vegetarian') + '"></span>' + it.n + '</div>' +
          '<div class="ds">' + it.d + '</div>' +
          (it.best ? '<span class="best">Bestseller</span>' : '') +
          '<div class="row"><span class="pr">' + inr(it.p) + '</span><span class="ctl"></span></div>' +
        '</div>';
      list.appendChild(el);
    });
    menuEl.appendChild(sec);
  });

  function renderCtl(key) {
    var el = menuEl.querySelector('[data-key="' + key + '"] .ctl');
    var n = cart[key] || 0;
    if (!n) {
      el.innerHTML = '<button class="add" data-act="inc" data-key="' + key + '" aria-label="Add ' + byKey[key].n + '">Add</button>';
    } else {
      el.innerHTML = '<div class="step"><button data-act="dec" data-key="' + key + '" aria-label="Remove one ' + byKey[key].n + '">−</button><span>' + n + '</span><button data-act="inc" data-key="' + key + '" aria-label="Add one more ' + byKey[key].n + '">+</button></div>';
    }
  }
  Object.keys(byKey).forEach(renderCtl);

  function totals() {
    var c = 0, s = 0;
    Object.keys(cart).forEach(function (k) { c += cart[k]; s += cart[k] * byKey[k].p; });
    return { count: c, sum: s };
  }

  function refresh() {
    var t = totals();
    $('bar').classList.toggle('show', t.count > 0);
    $('barInfo').textContent = t.count + (t.count === 1 ? ' item' : ' items') + ' · ' + inr(t.sum);
    if (!$('sheet').hidden) renderSheet();
    if (t.count === 0 && !$('sheet').hidden) closeSheet();
  }

  function change(key, delta) {
    var n = (cart[key] || 0) + delta;
    if (n <= 0) delete cart[key]; else cart[key] = Math.min(n, 20);
    renderCtl(key); refresh();
  }

  document.addEventListener('click', function (e) {
    var b = e.target.closest('[data-act]');
    if (!b) return;
    change(b.dataset.key, b.dataset.act === 'inc' ? 1 : -1);
  });

  // Sheet
  function renderSheet() {
    var html = '';
    Object.keys(cart).forEach(function (k) {
      var it = byKey[k];
      html += '<div class="line"><div><div class="ln">' + it.n + '</div><div class="lp">' + inr(it.p) + ' each</div></div>' +
        '<div class="step"><button data-act="dec" data-key="' + k + '" aria-label="Remove one ' + it.n + '">−</button><span>' + cart[k] + '</span><button data-act="inc" data-key="' + k + '" aria-label="Add one more ' + it.n + '">+</button></div></div>';
    });
    $('lines').innerHTML = html;
    $('total').textContent = inr(totals().sum);
    $('sheetTable').textContent = table ? 'Table ' + table : 'Brew & Bloom';
    updateLink();
  }
  function updateLink() {
    var lines = ['Hi Brew & Bloom, new order' + (table ? ' for Table ' + table : '') + ':', ''];
    Object.keys(cart).forEach(function (k) {
      lines.push(cart[k] + ' x ' + byKey[k].n + ' (' + inr(cart[k] * byKey[k].p) + ')');
    });
    lines.push('', 'Total: ' + inr(totals().sum));
    var note = $('note').value.trim();
    if (note) lines.push('', 'Note: ' + note);
    $('send').href = 'https://wa.me/?text=' + encodeURIComponent(lines.join('\n'));
  }
  $('note').addEventListener('input', updateLink);
  function openSheet() { $('scrim').hidden = false; $('sheet').hidden = false; renderSheet(); $('closeSheet').focus(); }
  function closeSheet() { $('scrim').hidden = true; $('sheet').hidden = true; }
  $('barBtn').addEventListener('click', openSheet);
  $('closeSheet').addEventListener('click', closeSheet);
  $('scrim').addEventListener('click', closeSheet);
  document.addEventListener('keydown', function (e) { if (e.key === 'Escape') closeSheet(); });

  // Toast for demo review button
  var toastTimer;
  $('reviewBtn').addEventListener('click', function () {
    var t = $('toast');
    t.textContent = 'On a live menu, this opens the café’s Google review page.';
    t.hidden = false; clearTimeout(toastTimer);
    toastTimer = setTimeout(function () { t.hidden = true; }, 3400);
  });

  // Filter
  function applyFilter() {
    var any = false;
    MENU.forEach(function (c) {
      var sec = $(c.id), shown = 0;
      sec.querySelectorAll('.item').forEach(function (el) {
        var ok = (!q || el.dataset.text.indexOf(q) > -1) && (!vegOnly || el.dataset.veg === '1');
        el.style.display = ok ? '' : 'none';
        if (ok) shown++;
      });
      sec.style.display = shown ? '' : 'none';
      tabsEl.querySelector('[data-target="' + c.id + '"]').style.display = shown ? '' : 'none';
      if (shown) any = true;
    });
    $('empty').style.display = any ? 'none' : 'block';
  }
  $('q').addEventListener('input', function (e) { q = e.target.value.trim().toLowerCase(); applyFilter(); });
  $('veg').addEventListener('click', function () {
    vegOnly = !vegOnly; this.setAttribute('aria-pressed', String(vegOnly)); applyFilter();
  });

  // Tabs: jump + scroll spy
  var reduce = window.matchMedia && window.matchMedia('(prefers-reduced-motion: reduce)').matches;
  tabsEl.addEventListener('click', function (e) {
    var t = e.target.closest('.tab'); if (!t) return;
    $(t.dataset.target).scrollIntoView({ behavior: reduce ? 'auto' : 'smooth', block: 'start' });
  });
  function setActive(id) {
    tabsEl.querySelectorAll('.tab').forEach(function (t) {
      var on = t.dataset.target === id;
      if (on) t.setAttribute('aria-current', 'true'); else t.removeAttribute('aria-current');
      if (on) { var l = t.offsetLeft - 18; tabsEl.scrollTo({ left: l, behavior: 'auto' }); }
    });
  }
  setActive(MENU[0].id);
  window.addEventListener('scroll', function () {
    var cur = MENU[0].id;
    MENU.forEach(function (c) {
      var s = $(c.id);
      if (s.style.display !== 'none' && s.getBoundingClientRect().top < 120) cur = c.id;
    });
    setActive(cur);
  }, { passive: true });

  refresh();
})();
</script>
</body>
</html>
