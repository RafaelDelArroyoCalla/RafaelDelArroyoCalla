<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Rafael Del Arroyo | Full Stack & Diseño Web</title>
<meta name="description" content="Portafolio de Rafael Del Arroyo: desarrollador Full Stack y diseñador web independiente. Estudiante de décimo semestre de Ingeniería de Sistemas en la UCSM.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#0b0d12; --bg2:#11141b; --card:#141823; --line:#232a3a;
    --text:#e8ecf4; --muted:#8b95a9;
    --a1:#7c5cff; --a2:#22d3ee; --ok:#34d399;
    --radius:16px;
  }
  :root[data-theme="light"]{
    --bg:#f6f7fb; --bg2:#eceef6; --card:#ffffff; --line:#dde1ee;
    --text:#151824; --muted:#5b6479;
  }
  *{box-sizing:border-box;margin:0;padding:0}
  html{scroll-behavior:smooth}
  body{font-family:'Space Grotesk',system-ui,sans-serif;background:var(--bg);color:var(--text);line-height:1.6;overflow-x:hidden}
  .mono{font-family:'JetBrains Mono',monospace}
  a{color:inherit;text-decoration:none}
  .wrap{max-width:1100px;margin:0 auto;padding:0 20px}
  section{padding:84px 0}
  h2{font-size:clamp(1.6rem,3vw,2.2rem);margin-bottom:8px}
  .eyebrow{color:var(--a2);font-size:.85rem;letter-spacing:.12em;text-transform:uppercase;margin-bottom:10px}
  .sub{color:var(--muted);max-width:620px;margin-bottom:36px}
  .grad{background:linear-gradient(90deg,var(--a1),var(--a2));-webkit-background-clip:text;background-clip:text;color:transparent}

  /* fondo animado */
  .glow{position:fixed;inset:0;z-index:-1;pointer-events:none;
    background:
      radial-gradient(600px circle at var(--mx,20%) var(--my,10%),rgba(124,92,255,.16),transparent 60%),
      radial-gradient(500px circle at 85% 80%,rgba(34,211,238,.10),transparent 60%);}

  /* nav */
  nav{position:sticky;top:0;z-index:50;backdrop-filter:blur(12px);background:color-mix(in srgb,var(--bg) 78%,transparent);border-bottom:1px solid var(--line)}
  nav .wrap{display:flex;align-items:center;justify-content:space-between;height:62px}
  .logo{font-weight:700}
  .logo span{color:var(--a2)}
  .links{display:flex;gap:22px;align-items:center;font-size:.95rem}
  .links a{color:var(--muted);transition:color .2s}
  .links a:hover{color:var(--text)}
  .icon-btn{background:var(--card);border:1px solid var(--line);color:var(--text);width:38px;height:38px;border-radius:10px;cursor:pointer;font-size:1rem}
  @media(max-width:700px){.links a:not(.keep){display:none}}

  /* hero */
  .hero{padding:96px 0 70px;display:grid;grid-template-columns:1.25fr .75fr;gap:40px;align-items:center}
  @media(max-width:860px){.hero{grid-template-columns:1fr}}
  .badge{display:inline-flex;gap:8px;align-items:center;border:1px solid var(--line);background:var(--card);padding:6px 12px;border-radius:999px;font-size:.82rem;color:var(--muted);margin-bottom:22px}
  .dot{width:8px;height:8px;border-radius:50%;background:var(--ok);box-shadow:0 0 0 0 rgba(52,211,153,.6);animation:pulse 2s infinite}
  @keyframes pulse{70%{box-shadow:0 0 0 9px rgba(52,211,153,0)}100%{box-shadow:0 0 0 0 rgba(52,211,153,0)}}
  h1{font-size:clamp(2.2rem,5.5vw,3.8rem);line-height:1.08;letter-spacing:-.02em}
  .typed{min-height:2em;margin:18px 0 8px;font-size:1.15rem;color:var(--a2)}
  .caret{display:inline-block;width:2px;height:1.1em;background:var(--a2);margin-left:3px;vertical-align:-3px;animation:blink 1s steps(1) infinite}
  @keyframes blink{50%{opacity:0}}
  .lead{color:var(--muted);max-width:560px;margin-bottom:28px}
  .cta{display:flex;gap:12px;flex-wrap:wrap}
  .btn{padding:12px 20px;border-radius:12px;font-weight:500;border:1px solid var(--line);background:var(--card);transition:transform .2s,border-color .2s}
  .btn:hover{transform:translateY(-2px);border-color:var(--a1)}
  .btn.primary{background:linear-gradient(90deg,var(--a1),var(--a2));border:0;color:#fff}

  /* terminal */
  .term{background:#0a0c10;border:1px solid var(--line);border-radius:var(--radius);overflow:hidden;box-shadow:0 20px 60px rgba(0,0,0,.35)}
  .term-bar{display:flex;gap:6px;padding:10px 14px;background:#12151c;border-bottom:1px solid #1d2230}
  .term-bar i{width:10px;height:10px;border-radius:50%;display:block}
  .term-bar i:nth-child(1){background:#ff5f57}.term-bar i:nth-child(2){background:#febc2e}.term-bar i:nth-child(3){background:#28c840}
  .term pre{padding:18px;font-size:.82rem;line-height:1.7;color:#c9d3e6;white-space:pre-wrap}
  .k{color:#c4a7ff}.s{color:#7ee7a8}.c{color:#6b7690}.n{color:#67e8f9}

  /* stats github */
  .stats{display:grid;grid-template-columns:repeat(4,1fr);gap:14px;margin-top:10px}
  @media(max-width:700px){.stats{grid-template-columns:repeat(2,1fr)}}
  .stat{background:var(--card);border:1px solid var(--line);border-radius:var(--radius);padding:18px}
  .stat b{display:block;font-size:1.8rem}
  .stat span{color:var(--muted);font-size:.85rem}

  /* sobre mi */
  .about{display:grid;grid-template-columns:1fr 1fr;gap:28px}
  @media(max-width:800px){.about{grid-template-columns:1fr}}
  .panel{background:var(--card);border:1px solid var(--line);border-radius:var(--radius);padding:24px}
  .panel h3{margin-bottom:10px}
  .panel p{color:var(--muted)}
  .timeline{list-style:none;border-left:2px solid var(--line);padding-left:18px;margin-top:6px}
  .timeline li{margin-bottom:14px;position:relative}
  .timeline li::before{content:"";position:absolute;left:-25px;top:8px;width:10px;height:10px;border-radius:50%;background:var(--a1)}
  .timeline small{color:var(--muted);display:block}

  /* skills */
  .grid3{display:grid;grid-template-columns:repeat(3,1fr);gap:16px}
  @media(max-width:900px){.grid3{grid-template-columns:1fr 1fr}}
  @media(max-width:600px){.grid3{grid-template-columns:1fr}}
  .skill{background:var(--card);border:1px solid var(--line);border-radius:var(--radius);padding:22px;transition:transform .25s,border-color .25s}
  .skill:hover{transform:translateY(-4px);border-color:var(--a1)}
  .skill .ico{font-size:1.6rem;margin-bottom:8px}
  .chips{display:flex;flex-wrap:wrap;gap:8px;margin-top:12px}
  .chip{font-size:.78rem;padding:4px 10px;border-radius:999px;background:var(--bg2);border:1px solid var(--line);color:var(--muted)}

  /* repos */
  .toolbar{display:flex;gap:10px;flex-wrap:wrap;margin-bottom:20px}
  .toolbar input,.toolbar select{background:var(--card);border:1px solid var(--line);color:var(--text);padding:10px 14px;border-radius:10px;font:inherit;min-width:180px}
  .repo{background:var(--card);border:1px solid var(--line);border-radius:var(--radius);padding:20px;display:flex;flex-direction:column;gap:10px;transition:transform .25s,border-color .25s}
  .repo:hover{transform:translateY(-4px);border-color:var(--a2)}
  .repo h3{font-size:1.05rem;word-break:break-word}
  .repo p{color:var(--muted);font-size:.9rem;flex:1}
  .meta{display:flex;gap:14px;font-size:.8rem;color:var(--muted);flex-wrap:wrap}
  .lang-dot{display:inline-block;width:10px;height:10px;border-radius:50%;margin-right:5px}
  .state{color:var(--muted);padding:30px;text-align:center;border:1px dashed var(--line);border-radius:var(--radius);grid-column:1/-1}

  /* proyectos destacados */
  .proj{background:var(--card);border:1px solid var(--line);border-radius:var(--radius);overflow:hidden}
  .proj .shot{height:140px;background:linear-gradient(135deg,var(--a1),var(--a2));display:grid;place-items:center;font-size:2.2rem}
  .proj .body{padding:20px}
  .proj .body p{color:var(--muted);font-size:.92rem;margin:6px 0 10px}

  /* contacto */
  .contact{text-align:center}
  .contact .panel{padding:44px 24px}
  .socials{display:flex;gap:12px;justify-content:center;flex-wrap:wrap;margin-top:20px}
  footer{border-top:1px solid var(--line);padding:26px 0;color:var(--muted);font-size:.85rem;text-align:center}

  /* reveal */
  .reveal{opacity:0;transform:translateY(22px);transition:opacity .7s,transform .7s}
  .reveal.in{opacity:1;transform:none}
  @media(prefers-reduced-motion:reduce){
    *{animation:none!important;transition:none!important}
    .reveal{opacity:1;transform:none}
    html{scroll-behavior:auto}
  }
</style>
</head>
<body>
<div class="glow" id="glow"></div>

<nav>
  <div class="wrap">
    <a href="#inicio" class="logo mono">&lt;rafael<span>/</span>&gt;</a>
    <div class="links">
      <a href="#sobre-mi">Sobre mí</a>
      <a href="#skills">Skills</a>
      <a href="#proyectos">Proyectos</a>
      <a href="#repos">GitHub</a>
      <a href="#contacto" class="keep">Contacto</a>
      <button class="icon-btn" id="theme" aria-label="Cambiar tema">🌙</button>
    </div>
  </div>
</nav>

<main class="wrap">

  <!-- HERO -->
  <header class="hero" id="inicio">
    <div>
      <div class="badge mono"><span class="dot"></span> Disponible para proyectos freelance</div>
      <h1>Hola, soy <span class="grad" id="nombre">Rafael Del Arroyo</span></h1>
      <div class="typed mono"><span id="typed"></span><span class="caret"></span></div>
      <p class="lead">
        Desarrollo y diseño sitios web de principio a fin: desde la interfaz hasta la base de datos.
        Estudiante de décimo semestre de Ingeniería de Sistemas en la Universidad Católica de Santa María (Arequipa, Perú),
        construyendo mi camino como desarrollador independiente.
      </p>
      <div class="cta">
        <a class="btn primary" href="#proyectos">Ver proyectos</a>
        <a class="btn" id="btnGithub" href="#" target="_blank" rel="noopener">Mi GitHub ↗</a>
        <a class="btn" href="#contacto">Contáctame</a>
      </div>
    </div>

    <div class="term reveal">
      <div class="term-bar"><i></i><i></i><i></i></div>
<pre class="mono"><span class="c">// perfil.js</span>
<span class="k">const</span> <span class="n">dev</span> = {
  nombre: <span class="s">"Rafael Del Arroyo"</span>,
  rol: <span class="s">"Full Stack & Web Designer"</span>,
  estudia: <span class="s">"Ing. de Sistemas — UCSM"</span>,
  semestre: <span class="s">"10mo"</span>,
  modalidad: <span class="s">"Independiente"</span>,
  stack: [<span class="s">"HTML"</span>,<span class="s">"CSS"</span>,<span class="s">"JS"</span>,<span class="s">"Node"</span>,<span class="s">"SQL"</span>],
  aprendiendo: <span class="s">"siempre"</span>
};</pre>
    </div>
  </header>

  <!-- STATS EN VIVO -->
  <section style="padding-top:0">
    <div class="stats reveal">
      <div class="stat"><b id="stRepos">–</b><span>Repositorios públicos</span></div>
      <div class="stat"><b id="stStars">–</b><span>Estrellas recibidas</span></div>
      <div class="stat"><b id="stFollowers">–</b><span>Seguidores</span></div>
      <div class="stat"><b id="stLangs">–</b><span>Lenguajes usados</span></div>
    </div>
  </section>

  <!-- SOBRE MI -->
  <section id="sobre-mi">
    <div class="eyebrow mono">// sobre mí</div>
    <h2>Del aula al código real</h2>
    <p class="sub">Combino lo que aprendo en la universidad con proyectos prácticos para clientes y para mi propio portafolio.</p>
    <div class="about">
      <div class="panel reveal">
        <h3>Mi enfoque</h3>
        <p>
          Me gusta que un sitio se vea bien, cargue rápido y funcione sin sorpresas. Diseño la interfaz pensando en el
          usuario y la respaldo con un backend ordenado: rutas, base de datos y autenticación cuando hace falta.
          Trabajo de forma independiente, así que me encargo de todo el ciclo: idea, diseño, desarrollo y publicación.
        </p>
      </div>
      <div class="panel reveal">
        <h3>Trayectoria</h3>
        <ul class="timeline">
          <li><b>Ingeniería de Sistemas</b><small>Universidad Católica de Santa María · 10.º semestre</small></li>
          <li><b>Desarrollador Full Stack independiente</b><small>Sitios web, sistemas y diseño UI</small></li>
          <li><b>Siguiente paso</b><small>Roles técnicos y proyectos con impacto real</small></li>
        </ul>
      </div>
    </div>
  </section>

  <!-- SKILLS -->
  <section id="skills">
    <div class="eyebrow mono">// habilidades</div>
    <h2>Lo que hago</h2>
    <p class="sub">Del diseño al despliegue.</p>
    <div class="grid3">
      <article class="skill reveal">
        <div class="ico">🎨</div><h3>Diseño web / UI</h3>
        <p style="color:var(--muted)">Interfaces limpias, responsivas y accesibles.</p>
        <div class="chips"><span class="chip">Figma</span><span class="chip">CSS moderno</span><span class="chip">Responsive</span><span class="chip">UX</span></div>
      </article>
      <article class="skill reveal">
        <div class="ico">🧩</div><h3>Frontend</h3>
        <p style="color:var(--muted)">Páginas dinámicas e interactivas.</p>
        <div class="chips"><span class="chip">HTML5</span><span class="chip">CSS3</span><span class="chip">JavaScript</span><span class="chip">React</span></div>
      </article>
      <article class="skill reveal">
        <div class="ico">⚙️</div><h3>Backend</h3>
        <p style="color:var(--muted)">APIs, lógica de negocio y autenticación.</p>
        <div class="chips"><span class="chip">Node.js</span><span class="chip">Express</span><span class="chip">PHP</span><span class="chip">REST</span></div>
      </article>
      <article class="skill reveal">
        <div class="ico">🗄️</div><h3>Bases de datos</h3>
        <p style="color:var(--muted)">Modelado y consultas eficientes.</p>
        <div class="chips"><span class="chip">MySQL</span><span class="chip">PostgreSQL</span><span class="chip">MongoDB</span></div>
      </article>
      <article class="skill reveal">
        <div class="ico">🚀</div><h3>Despliegue</h3>
        <p style="color:var(--muted)">Publicar y mantener tus proyectos en línea.</p>
        <div class="chips"><span class="chip">Git</span><span class="chip">GitHub Pages</span><span class="chip">Vercel</span><span class="chip">Hosting</span></div>
      </article>
      <article class="skill reveal">
        <div class="ico">🔒</div><h3>Buenas prácticas</h3>
        <p style="color:var(--muted)">Código limpio y conciencia de seguridad.</p>
        <div class="chips"><span class="chip">Validación</span><span class="chip">HTTPS</span><span class="chip">SEO básico</span></div>
      </article>
    </div>
  </section>

  <!-- PROYECTOS DESTACADOS (edítalos) -->
  <section id="proyectos">
    <div class="eyebrow mono">// proyectos destacados</div>
    <h2>Trabajo seleccionado</h2>
    <p class="sub">Reemplaza estos ejemplos por tus proyectos reales: título, descripción, tecnologías y enlaces.</p>
    <div class="grid3" id="featured"></div>
  </section>

  <!-- REPOS EN VIVO -->
  <section id="repos">
    <div class="eyebrow mono">// github en vivo</div>
    <h2>Mis repositorios</h2>
    <p class="sub">Esta lista se actualiza sola desde la API de GitHub cada vez que alguien abre la página.</p>
    <div class="toolbar">
      <input id="q" type="search" placeholder="Buscar repositorio…" aria-label="Buscar repositorio">
      <select id="sort" aria-label="Ordenar">
        <option value="updated">Más recientes</option>
        <option value="stars">Más estrellas</option>
        <option value="name">Nombre A–Z</option>
      </select>
    </div>
    <div class="grid3" id="repoGrid"><div class="state">Cargando repositorios…</div></div>
  </section>

  <!-- CONTACTO -->
  <section id="contacto" class="contact">
    <div class="panel reveal">
      <div class="eyebrow mono">// contacto</div>
      <h2>¿Tienes una idea o un proyecto?</h2>
      <p class="sub" style="margin:8px auto 0">Cuéntame qué necesitas y lo convertimos en un sitio web funcional.</p>
      <div class="socials">
        <a class="btn primary" id="mail" href="#">✉️ Escríbeme</a>
        <a class="btn" id="gh2" href="#" target="_blank" rel="noopener">GitHub</a>
        <a class="btn" id="li" href="#" target="_blank" rel="noopener">LinkedIn</a>
        <a class="btn" id="wa" href="#" target="_blank" rel="noopener">WhatsApp</a>
      </div>
    </div>
  </section>
</main>

<footer>
  © <span id="year"></span> Rafael Del Arroyo · Hecho con HTML, CSS y JavaScript · Arequipa, Perú
</footer>

<script>
/* ============ CONFIGURACIÓN: EDITA SOLO ESTO ============ */
const CONFIG = {
  githubUser: "TU_USUARIO_GITHUB",          // <- tu usuario de GitHub
  email: "tucorreo@ejemplo.com",             // <- tu correo
  linkedin: "https://www.linkedin.com/in/tu-perfil",
  whatsapp: "https://wa.me/51999999999",     // <- tu número con código de país
  roles: [
    "Desarrollador Full Stack",
    "Diseñador de páginas web",
    "Estudiante de Ingeniería de Sistemas",
    "Freelancer en crecimiento"
  ],
  featured: [
    { icon:"🛒", title:"Sistema de ventas",      desc:"Aplicación web con facturación, inventario y panel de control.", tags:["Node.js","MySQL","JS"], link:"#", repo:"#" },
    { icon:"🍽️", title:"Página de restaurante",  desc:"Sitio responsivo con carta digital y reservas.",               tags:["HTML","CSS","JS"],      link:"#", repo:"#" },
    { icon:"📱", title:"Landing page de negocio", desc:"Diseño enfocado en conversión y velocidad de carga.",          tags:["Figma","CSS"],          link:"#", repo:"#" }
  ]
};
/* ======================================================== */

const $ = s => document.querySelector(s);
const esc = t => String(t ?? "").replace(/[&<>"']/g, c => ({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));

/* Enlaces */
const ghUrl = `https://github.com/${CONFIG.githubUser}`;
$("#btnGithub").href = ghUrl; $("#gh2").href = ghUrl;
$("#mail").href = `mailto:${CONFIG.email}`;
$("#li").href = CONFIG.linkedin; $("#wa").href = CONFIG.whatsapp;
$("#year").textContent = new Date().getFullYear();

/* Tema claro/oscuro */
const root = document.documentElement, themeBtn = $("#theme");
function setTheme(t){ root.dataset.theme = t; themeBtn.textContent = t === "light" ? "☀️" : "🌙"; try{localStorage.setItem("theme",t)}catch(e){} }
let saved = null; try{ saved = localStorage.getItem("theme") }catch(e){}
setTheme(saved || (matchMedia("(prefers-color-scheme: light)").matches ? "light" : "dark"));
themeBtn.onclick = () => setTheme(root.dataset.theme === "light" ? "dark" : "light");

/* Efecto de escritura */
(function typing(){
  const el = $("#typed"); let r = 0, i = 0, del = false;
  const reduce = matchMedia("(prefers-reduced-motion: reduce)").matches;
  if (reduce){ el.textContent = CONFIG.roles[0]; return; }
  (function tick(){
    const word = CONFIG.roles[r];
    el.textContent = word.slice(0, i);
    if (!del && i === word.length){ del = true; return setTimeout(tick, 1400); }
    if (del && i === 0){ del = false; r = (r+1) % CONFIG.roles.length; }
    i += del ? -1 : 1;
    setTimeout(tick, del ? 35 : 70);
  })();
})();

/* Luz que sigue al cursor */
addEventListener("pointermove", e => {
  const g = $("#glow");
  g.style.setProperty("--mx", e.clientX + "px");
  g.style.setProperty("--my", e.clientY + "px");
});

/* Proyectos destacados */
$("#featured").innerHTML = CONFIG.featured.map(p => `
  <article class="proj reveal">
    <div class="shot">${esc(p.icon)}</div>
    <div class="body">
      <h3>${esc(p.title)}</h3>
      <p>${esc(p.desc)}</p>
      <div class="chips">${p.tags.map(t=>`<span class="chip">${esc(t)}</span>`).join("")}</div>
      <div class="chips" style="margin-top:14px">
        <a class="chip" href="${esc(p.link)}" target="_blank" rel="noopener">Demo ↗</a>
        <a class="chip" href="${esc(p.repo)}" target="_blank" rel="noopener">Código ↗</a>
      </div>
    </div>
  </article>`).join("");

/* GitHub en vivo */
const LANG_COLORS = {JavaScript:"#f1e05a",TypeScript:"#3178c6",HTML:"#e34c26",CSS:"#563d7c",Python:"#3572A5",PHP:"#4F5D95",Java:"#b07219","C#":"#178600","C++":"#f34b7d",Vue:"#41b883",SCSS:"#c6538c",Shell:"#89e051",Kotlin:"#A97BFF",Dart:"#00B4AB"};
let REPOS = [];

function renderRepos(){
  const q = $("#q").value.trim().toLowerCase(), sort = $("#sort").value;
  let list = REPOS.filter(r => (r.name + " " + (r.description||"")).toLowerCase().includes(q));
  list.sort((a,b) => sort==="stars" ? b.stargazers_count - a.stargazers_count
                    : sort==="name"  ? a.name.localeCompare(b.name)
                    : new Date(b.pushed_at) - new Date(a.pushed_at));
  $("#repoGrid").innerHTML = list.length ? list.map(r => `
    <article class="repo reveal in">
      <h3><a href="${esc(r.html_url)}" target="_blank" rel="noopener">📁 ${esc(r.name)}</a></h3>
      <p>${esc(r.description || "Sin descripción todavía.")}</p>
      <div class="meta">
        ${r.language ? `<span><i class="lang-dot" style="background:${LANG_COLORS[r.language]||'#8b95a9'}"></i>${esc(r.language)}</span>` : ""}
        <span>⭐ ${r.stargazers_count}</span>
        <span>🍴 ${r.forks_count}</span>
        <span>🕒 ${new Date(r.pushed_at).toLocaleDateString("es-PE",{day:"2-digit",month:"short",year:"numeric"})}</span>
      </div>
      ${r.homepage ? `<a class="chip" style="align-self:flex-start" href="${esc(r.homepage)}" target="_blank" rel="noopener">Ver demo ↗</a>` : ""}
    </article>`).join("") : `<div class="state">No se encontraron repositorios.</div>`;
}

async function loadGithub(){
  if (CONFIG.githubUser === "TU_USUARIO_GITHUB"){
    $("#repoGrid").innerHTML = `<div class="state">Escribe tu usuario de GitHub en <code>CONFIG.githubUser</code> para ver tus repositorios aquí.</div>`;
    return;
  }
  try{
    const [uRes, rRes] = await Promise.all([
      fetch(`https://api.github.com/users/${CONFIG.githubUser}`),
      fetch(`https://api.github.com/users/${CONFIG.githubUser}/repos?per_page=100&sort=pushed`)
    ]);
    if (!uRes.ok || !rRes.ok) throw new Error("API " + uRes.status);
    const user = await uRes.json();
    REPOS = (await rRes.json()).filter(r => !r.fork);
    $("#stRepos").textContent = user.public_repos;
    $("#stFollowers").textContent = user.followers;
    $("#stStars").textContent = REPOS.reduce((s,r)=>s+r.stargazers_count,0);
    $("#stLangs").textContent = new Set(REPOS.map(r=>r.language).filter(Boolean)).size;
    renderRepos();
  }catch(err){
    $("#repoGrid").innerHTML = `<div class="state">No pude cargar GitHub ahora (límite de la API o sin conexión). <a class="grad" href="${ghUrl}" target="_blank" rel="noopener">Míralos directamente en GitHub ↗</a></div>`;
  }
}
$("#q").addEventListener("input", renderRepos);
$("#sort").addEventListener("change", renderRepos);
loadGithub();

/* Animación al hacer scroll */
const io = new IntersectionObserver(es => es.forEach(e => { if (e.isIntersecting){ e.target.classList.add("in"); io.unobserve(e.target); } }), {threshold:.12});
document.querySelectorAll(".reveal").forEach(el => io.observe(el));
</script>
</body>
</html>
