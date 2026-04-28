<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Dave | Consultor de Datos, BI & Calidad</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #080c10;
    --bg2: #0d1117;
    --surface: #111820;
    --surface2: #162030;
    --border: #1e2d3d;
    --accent: #00d4ff;
    --accent2: #00ff9f;
    --accent3: #7b61ff;
    --text: #e8f0f7;
    --text2: #7a9ab5;
    --text3: #4a6880;
    --danger: #ff4d6d;
    --warn: #ffb347;
  }
  *{margin:0;padding:0;box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    background:var(--bg);
    color:var(--text);
    font-family:'DM Sans',sans-serif;
    font-size:16px;
    line-height:1.6;
    overflow-x:hidden;
  }

  /* ── NOISE OVERLAY ── */
  body::before{
    content:'';
    position:fixed;inset:0;
    background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events:none;
    z-index:999;
    opacity:.4;
  }

  /* ── NAV ── */
  nav{
    position:fixed;top:0;left:0;right:0;z-index:100;
    display:flex;align-items:center;justify-content:space-between;
    padding:1.2rem 5%;
    background:rgba(8,12,16,.85);
    backdrop-filter:blur(16px);
    border-bottom:1px solid var(--border);
  }
  .nav-logo{
    font-family:'Syne',sans-serif;
    font-weight:800;font-size:1.3rem;
    color:var(--accent);
    letter-spacing:-.02em;
  }
  .nav-links{display:flex;gap:2rem;list-style:none;}
  .nav-links a{
    color:var(--text2);
    text-decoration:none;
    font-size:.9rem;
    font-weight:500;
    letter-spacing:.04em;
    text-transform:uppercase;
    transition:color .2s;
  }
  .nav-links a:hover{color:var(--accent);}

  /* ── HERO ── */
  #hero{
    min-height:100vh;
    display:flex;align-items:center;
    padding:120px 5% 80px;
    position:relative;
    overflow:hidden;
  }
  .hero-grid{
    position:absolute;inset:0;
    background-image:
      linear-gradient(var(--border) 1px, transparent 1px),
      linear-gradient(90deg, var(--border) 1px, transparent 1px);
    background-size:60px 60px;
    opacity:.25;
  }
  .hero-glow{
    position:absolute;
    width:600px;height:600px;
    border-radius:50%;
    background:radial-gradient(circle, rgba(0,212,255,.08) 0%, transparent 70%);
    top:-100px;right:-100px;
    pointer-events:none;
  }
  .hero-glow2{
    position:absolute;
    width:400px;height:400px;
    border-radius:50%;
    background:radial-gradient(circle, rgba(0,255,159,.06) 0%, transparent 70%);
    bottom:0;left:20%;
    pointer-events:none;
  }
  .hero-content{position:relative;max-width:800px;}
  .hero-badge{
    display:inline-flex;align-items:center;gap:.5rem;
    background:rgba(0,212,255,.08);
    border:1px solid rgba(0,212,255,.2);
    border-radius:100px;
    padding:.35rem 1rem;
    font-size:.8rem;
    color:var(--accent);
    letter-spacing:.06em;
    text-transform:uppercase;
    margin-bottom:1.5rem;
    animation:fadeUp .6s ease both;
  }
  .hero-badge::before{
    content:'';
    width:6px;height:6px;
    border-radius:50%;
    background:var(--accent);
    animation:pulse 2s infinite;
  }
  @keyframes pulse{0%,100%{opacity:1;transform:scale(1);}50%{opacity:.4;transform:scale(.8);}}
  h1{
    font-family:'Syne',sans-serif;
    font-size:clamp(2.8rem,6vw,5rem);
    font-weight:800;
    line-height:1.05;
    letter-spacing:-.03em;
    margin-bottom:1.5rem;
    animation:fadeUp .6s .1s ease both;
  }
  h1 span{
    background:linear-gradient(135deg, var(--accent), var(--accent2));
    -webkit-background-clip:text;
    -webkit-text-fill-color:transparent;
    background-clip:text;
  }
  .hero-sub{
    font-size:1.15rem;
    color:var(--text2);
    max-width:560px;
    line-height:1.7;
    margin-bottom:2.5rem;
    animation:fadeUp .6s .2s ease both;
  }
  .hero-cta{
    display:flex;gap:1rem;flex-wrap:wrap;
    animation:fadeUp .6s .3s ease both;
  }
  .btn{
    display:inline-flex;align-items:center;gap:.5rem;
    padding:.85rem 1.8rem;
    border-radius:8px;
    font-size:.95rem;
    font-weight:500;
    cursor:pointer;
    text-decoration:none;
    transition:all .2s;
    font-family:'DM Sans',sans-serif;
  }
  .btn-primary{
    background:var(--accent);
    color:#000;
    border:none;
  }
  .btn-primary:hover{background:#00b8d9;transform:translateY(-2px);box-shadow:0 8px 24px rgba(0,212,255,.25);}
  .btn-outline{
    background:transparent;
    color:var(--text);
    border:1px solid var(--border);
  }
  .btn-outline:hover{border-color:var(--accent);color:var(--accent);transform:translateY(-2px);}
  .tech-stack{
    display:flex;flex-wrap:wrap;gap:.7rem;
    margin-top:3rem;
    animation:fadeUp .6s .4s ease both;
  }
  .tech-chip{
    display:flex;align-items:center;gap:.4rem;
    background:var(--surface);
    border:1px solid var(--border);
    border-radius:6px;
    padding:.4rem .8rem;
    font-size:.82rem;
    color:var(--text2);
    transition:all .2s;
  }
  .tech-chip:hover{border-color:var(--accent);color:var(--accent);}
  .tech-chip .dot{width:6px;height:6px;border-radius:50%;}

  @keyframes fadeUp{from{opacity:0;transform:translateY(20px);}to{opacity:1;transform:translateY(0);}}

  /* ── SECTIONS ── */
  section{padding:100px 5%;}
  .section-label{
    display:inline-block;
    font-size:.75rem;
    letter-spacing:.12em;
    text-transform:uppercase;
    color:var(--accent);
    font-weight:600;
    margin-bottom:1rem;
    position:relative;
    padding-left:1.5rem;
  }
  .section-label::before{
    content:'';
    position:absolute;left:0;top:50%;
    width:1rem;height:1px;
    background:var(--accent);
  }
  h2{
    font-family:'Syne',sans-serif;
    font-size:clamp(1.8rem,4vw,2.8rem);
    font-weight:700;
    letter-spacing:-.02em;
    margin-bottom:1rem;
    line-height:1.15;
  }
  .section-desc{color:var(--text2);max-width:540px;margin-bottom:3.5rem;line-height:1.7;}

  /* ── PROYECTOS ── */
  #proyectos{background:var(--bg2);}
  .projects-grid{
    display:grid;
    grid-template-columns:repeat(auto-fill, minmax(320px,1fr));
    gap:1.5rem;
  }
  .project-card{
    background:var(--surface);
    border:1px solid var(--border);
    border-radius:12px;
    padding:1.8rem;
    transition:all .3s;
    position:relative;
    overflow:hidden;
  }
  .project-card::before{
    content:'';
    position:absolute;top:0;left:0;right:0;
    height:2px;
    background:linear-gradient(90deg,var(--accent),var(--accent2));
    opacity:0;
    transition:opacity .3s;
  }
  .project-card:hover{border-color:rgba(0,212,255,.3);transform:translateY(-4px);box-shadow:0 16px 40px rgba(0,0,0,.4);}
  .project-card:hover::before{opacity:1;}
  .card-header{display:flex;align-items:flex-start;justify-content:space-between;margin-bottom:1.2rem;}
  .card-icon{
    width:44px;height:44px;border-radius:10px;
    display:flex;align-items:center;justify-content:center;
    font-size:1.3rem;
    background:var(--surface2);
  }
  .badge{
    font-size:.7rem;
    letter-spacing:.06em;
    text-transform:uppercase;
    padding:.25rem .7rem;
    border-radius:100px;
    font-weight:600;
  }
  .badge-real{background:rgba(0,255,159,.1);color:var(--accent2);border:1px solid rgba(0,255,159,.2);}
  .badge-demo{background:rgba(0,212,255,.1);color:var(--accent);border:1px solid rgba(0,212,255,.2);}
  .card-title{
    font-family:'Syne',sans-serif;
    font-size:1.1rem;
    font-weight:700;
    margin-bottom:.8rem;
  }
  .card-section{margin-bottom:.8rem;}
  .card-section-label{
    font-size:.72rem;
    letter-spacing:.08em;
    text-transform:uppercase;
    font-weight:600;
    margin-bottom:.3rem;
  }
  .label-problem{color:var(--danger);}
  .label-solution{color:var(--warn);}
  .label-result{color:var(--accent2);}
  .card-section p{font-size:.9rem;color:var(--text2);line-height:1.5;}
  .card-tags{display:flex;flex-wrap:wrap;gap:.4rem;margin-top:1.2rem;}
  .tag{
    font-size:.72rem;
    background:var(--surface2);
    border:1px solid var(--border);
    border-radius:4px;
    padding:.2rem .55rem;
    color:var(--text3);
  }

  /* ── SERVICIOS ── */
  .services-grid{
    display:grid;
    grid-template-columns:repeat(auto-fill,minmax(280px,1fr));
    gap:1.5rem;
  }
  .service-card{
    background:var(--surface);
    border:1px solid var(--border);
    border-radius:12px;
    padding:2rem;
    transition:all .3s;
    position:relative;
  }
  .service-card:hover{border-color:rgba(123,97,255,.4);transform:translateY(-4px);box-shadow:0 16px 40px rgba(0,0,0,.4);}
  .service-icon{font-size:2rem;margin-bottom:1rem;}
  .service-title{
    font-family:'Syne',sans-serif;
    font-size:1.2rem;font-weight:700;
    margin-bottom:.5rem;
  }
  .service-desc{font-size:.9rem;color:var(--text2);line-height:1.6;margin-bottom:1.2rem;}
  .service-items{list-style:none;margin-bottom:1.5rem;}
  .service-items li{
    font-size:.85rem;color:var(--text2);
    padding:.3rem 0;
    border-bottom:1px solid var(--border);
    display:flex;align-items:center;gap:.5rem;
  }
  .service-items li::before{content:'→';color:var(--accent);font-size:.8rem;}
  .service-price{
    font-family:'Syne',sans-serif;
    font-size:1rem;font-weight:700;
    color:var(--accent);
  }

  /* ── CERTIFICACIONES ── */
  #certificaciones{background:var(--bg2);}
  .certs-grid{
    display:grid;
    grid-template-columns:repeat(auto-fill,minmax(220px,1fr));
    gap:1rem;
  }
  .cert-card{
    background:var(--surface);
    border:1px solid var(--border);
    border-radius:10px;
    padding:1.5rem;
    display:flex;align-items:center;gap:1rem;
    transition:all .25s;
  }
  .cert-card:hover{border-color:rgba(0,212,255,.3);transform:translateX(4px);}
  .cert-num{
    font-family:'Syne',sans-serif;
    font-size:1.5rem;font-weight:800;
    color:var(--accent);
    line-height:1;
    white-space:nowrap;
  }
  .cert-info{}
  .cert-name{font-weight:600;font-size:.95rem;margin-bottom:.1rem;}
  .cert-area{font-size:.8rem;color:var(--text3);}

  /* ── CONTACTO ── */
  #contacto{
    background:linear-gradient(180deg, var(--bg) 0%, var(--bg2) 100%);
    text-align:center;
  }
  #contacto h2{margin-bottom:.8rem;}
  #contacto .section-desc{margin:0 auto 2.5rem;}
  .contact-cards{
    display:flex;flex-wrap:wrap;justify-content:center;gap:1rem;
    margin-bottom:3rem;
  }
  .contact-item{
    background:var(--surface);
    border:1px solid var(--border);
    border-radius:10px;
    padding:1rem 1.5rem;
    display:flex;align-items:center;gap:.7rem;
    font-size:.9rem;
    color:var(--text2);
    text-decoration:none;
    transition:all .2s;
  }
  .contact-item:hover{border-color:var(--accent);color:var(--accent);transform:translateY(-2px);}
  .contact-icon{font-size:1.2rem;}

  /* ── FOOTER ── */
  footer{
    background:var(--bg);
    border-top:1px solid var(--border);
    padding:2rem 5%;
    display:flex;align-items:center;justify-content:space-between;
    flex-wrap:wrap;gap:1rem;
  }
  .footer-logo{font-family:'Syne',sans-serif;font-weight:800;color:var(--accent);}
  .footer-text{font-size:.82rem;color:var(--text3);}

  /* ── RESPONSIVE ── */
  @media(max-width:768px){
    nav .nav-links{display:none;}
    #hero{padding:100px 5% 60px;}
    section{padding:70px 5%;}
    .hero-cta{flex-direction:column;}
    .btn{justify-content:center;}
  }

  /* ── SCROLL REVEAL ── */
  .reveal{opacity:0;transform:translateY(30px);transition:opacity .6s ease, transform .6s ease;}
  .reveal.visible{opacity:1;transform:none;}
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">dave.</div>
  <ul class="nav-links">
    <li><a href="#proyectos">Proyectos</a></li>
    <li><a href="#servicios">Servicios</a></li>
    <li><a href="#certificaciones">Certificaciones</a></li>
    <li><a href="#contacto">Contacto</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-grid"></div>
  <div class="hero-glow"></div>
  <div class="hero-glow2"></div>
  <div class="hero-content">
    <div class="hero-badge">Disponible para proyectos freelance</div>
    <h1>Datos, BI &<br/><span>Automatización</span><br/>que generan resultados.</h1>
    <p class="hero-sub">Consultor especializado en Power BI, SharePoint y n8n. Ayudo a empresas a tomar mejores decisiones con datos y a optimizar procesos bajo estándares ISO.</p>
    <div class="hero-cta">
      <a href="#proyectos" class="btn btn-primary">▶ Ver proyectos</a>
      <a href="https://calendly.com/TU-USUARIO" target="_blank" class="btn btn-outline">📅 Agendar llamada</a>
    </div>
    <div class="tech-stack">
      <div class="tech-chip"><span class="dot" style="background:#F2C811;"></span>Power BI</div>
      <div class="tech-chip"><span class="dot" style="background:#0078D4;"></span>SharePoint</div>
      <div class="tech-chip"><span class="dot" style="background:#EA4B71;"></span>n8n</div>
      <div class="tech-chip"><span class="dot" style="background:#00d4ff;"></span>ISO 27001</div>
      <div class="tech-chip"><span class="dot" style="background:#00ff9f;"></span>ISO 9001</div>
      <div class="tech-chip"><span class="dot" style="background:#7b61ff;"></span>ISO 20000</div>
      <div class="tech-chip"><span class="dot" style="background:#ffb347;"></span>ISO 52001</div>
    </div>
  </div>
</section>

<!-- PROYECTOS -->
<section id="proyectos">
  <div class="reveal">
    <span class="section-label">Portafolio</span>
    <h2>Proyectos destacados</h2>
    <p class="section-desc">Casos reales y demos que muestran cómo combino datos, automatización y gestión de calidad para resolver problemas concretos.</p>
  </div>
  <div class="projects-grid reveal">

    <div class="project-card">
      <div class="card-header">
        <div class="card-icon">📊</div>
        <span class="badge badge-demo">Demo</span>
      </div>
      <div class="card-title">Dashboard de Cumplimiento ISO 27001</div>
      <div class="card-section">
        <div class="card-section-label label-problem">🔴 Problema</div>
        <p>El área de seguridad no tenía visibilidad del estado de sus controles ISO 27001 en tiempo real.</p>
      </div>
      <div class="card-section">
        <div class="card-section-label label-solution">🟡 Solución</div>
        <p>Dashboard en Power BI con KPIs de cumplimiento por dominio, tendencias y alertas de controles vencidos.</p>
      </div>
      <div class="card-section">
        <div class="card-section-label label-result">🟢 Resultado</div>
        <p>Reducción del 60% en tiempo de preparación de auditorías internas.</p>
      </div>
      <div class="card-tags">
        <span class="tag">Power BI</span>
        <span class="tag">ISO 27001</span>
        <span class="tag">Excel</span>
      </div>
    </div>

    <div class="project-card">
      <div class="card-header">
        <div class="card-icon">⚡</div>
        <span class="badge badge-demo">Demo</span>
      </div>
      <div class="card-title">Automatización de Reportes con n8n</div>
      <div class="card-section">
        <div class="card-section-label label-problem">🔴 Problema</div>
        <p>El equipo generaba reportes de Power BI manualmente cada lunes, consumiendo 3 horas semanales.</p>
      </div>
      <div class="card-section">
        <div class="card-section-label label-solution">🟡 Solución</div>
        <p>Flujo n8n que extrae datos, actualiza el modelo y envía el reporte PDF por correo automáticamente.</p>
      </div>
      <div class="card-section">
        <div class="card-section-label label-result">🟢 Resultado</div>
        <p>3 horas ahorradas por semana = 150+ horas al año recuperadas para trabajo de valor.</p>
      </div>
      <div class="card-tags">
        <span class="tag">n8n</span>
        <span class="tag">Power BI</span>
        <span class="tag">Automatización</span>
      </div>
    </div>

    <div class="project-card">
      <div class="card-header">
        <div class="card-icon">📋</div>
        <span class="badge badge-real">Real</span>
      </div>
      <div class="card-title">SGC en SharePoint — ISO 9001</div>
      <div class="card-section">
        <div class="card-section-label label-problem">🔴 Problema</div>
        <p>La empresa tenía documentos del SGC dispersos en correos y carpetas locales sin control de versiones.</p>
      </div>
      <div class="card-section">
        <div class="card-section-label label-solution">🟡 Solución</div>
        <p>Sitio SharePoint estructurado por proceso, con control de versiones, flujos de aprobación y permisos por rol.</p>
      </div>
      <div class="card-section">
        <div class="card-section-label label-result">🟢 Resultado</div>
        <p>Empresa obtuvo certificación ISO 9001. Tiempo de búsqueda de documentos redujo 80%.</p>
      </div>
      <div class="card-tags">
        <span class="tag">SharePoint</span>
        <span class="tag">ISO 9001</span>
        <span class="tag">Power Automate</span>
      </div>
    </div>

    <div class="project-card">
      <div class="card-header">
        <div class="card-icon">🔔</div>
        <span class="badge badge-demo">Demo</span>
      </div>
      <div class="card-title">Alertas de No Conformidades vía n8n</div>
      <div class="card-section">
        <div class="card-section-label label-problem">🔴 Problema</div>
        <p>Las no conformidades tardaban días en llegar al responsable, retrasando acciones correctivas.</p>
      </div>
      <div class="card-section">
        <div class="card-section-label label-solution">🟡 Solución</div>
        <p>Flujo n8n conectado a formulario: detecta NC, notifica por Teams, crea tarea en Planner con fecha límite.</p>
      </div>
      <div class="card-section">
        <div class="card-section-label label-result">🟢 Resultado</div>
        <p>Tiempo de respuesta a NC bajó de 72 horas a menos de 2 horas promedio.</p>
      </div>
      <div class="card-tags">
        <span class="tag">n8n</span>
        <span class="tag">Microsoft Teams</span>
        <span class="tag">ISO 9001</span>
      </div>
    </div>

  </div>
</section>

<!-- SERVICIOS -->
<section id="servicios">
  <div class="reveal">
    <span class="section-label">Qué ofrezco</span>
    <h2>Servicios</h2>
    <p class="section-desc">Soluciones enfocadas en resultados medibles, no solo entregables.</p>
  </div>
  <div class="services-grid reveal">

    <div class="service-card">
      <div class="service-icon">📊</div>
      <div class="service-title">Business Intelligence</div>
      <p class="service-desc">Dashboards y modelos de datos que transforman información en decisiones.</p>
      <ul class="service-items">
        <li>Dashboards en Power BI</li>
        <li>Modelado de datos</li>
        <li>KPIs y métricas de negocio</li>
        <li>Integración con múltiples fuentes</li>
      </ul>
      <div class="service-price">$15,000 – $45,000 MXN</div>
    </div>

    <div class="service-card">
      <div class="service-icon">⚙️</div>
      <div class="service-title">Automatización</div>
      <p class="service-desc">Flujos inteligentes con n8n que eliminan tareas repetitivas y conectan tus sistemas.</p>
      <ul class="service-items">
        <li>Flujos n8n personalizados</li>
        <li>Integraciones entre sistemas</li>
        <li>Reportes automáticos</li>
        <li>Notificaciones y alertas</li>
      </ul>
      <div class="service-price">$8,000 – $30,000 MXN</div>
    </div>

    <div class="service-card">
      <div class="service-icon">🏆</div>
      <div class="service-title">ISO & Gestión de Calidad</div>
      <p class="service-desc">Apoyo técnico para implementación y mantenimiento de sistemas de gestión certificables.</p>
      <ul class="service-items">
        <li>ISO 27001 · 9001 · 52001 · 20000</li>
        <li>Gestión documental en SharePoint</li>
        <li>Dashboards de cumplimiento</li>
        <li>Consultoría por hora</li>
      </ul>
      <div class="service-price">$800 – $1,500 MXN / hr</div>
    </div>

  </div>
</section>

<!-- CERTIFICACIONES -->
<section id="certificaciones">
  <div class="reveal">
    <span class="section-label">Credenciales</span>
    <h2>Certificaciones</h2>
    <p class="section-desc">Conocimiento formal respaldado en estándares internacionales.</p>
  </div>
  <div class="certs-grid reveal">
    <div class="cert-card">
      <div class="cert-num">27001</div>
      <div class="cert-info">
        <div class="cert-name">ISO 27001</div>
        <div class="cert-area">Seguridad de la Información</div>
      </div>
    </div>
    <div class="cert-card">
      <div class="cert-num">9001</div>
      <div class="cert-info">
        <div class="cert-name">ISO 9001</div>
        <div class="cert-area">Gestión de Calidad</div>
      </div>
    </div>
    <div class="cert-card">
      <div class="cert-num">52001</div>
      <div class="cert-info">
        <div class="cert-name">ISO 52001</div>
        <div class="cert-area">Gestión de Energía</div>
      </div>
    </div>
    <div class="cert-card">
      <div class="cert-num">20000</div>
      <div class="cert-info">
        <div class="cert-name">ISO 20000</div>
        <div class="cert-area">Gestión de Servicios TI</div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACTO -->
<section id="contacto">
  <div class="reveal">
    <span class="section-label">Hablemos</span>
    <h2>¿Tienes un proyecto en mente?</h2>
    <p class="section-desc">Agenda una llamada de 30 minutos sin costo para explorar cómo puedo ayudarte.</p>
  </div>
  <div class="reveal">
    <a href="https://calendly.com/TU-USUARIO" target="_blank" class="btn btn-primary" style="font-size:1.05rem;padding:1rem 2.5rem;margin-bottom:2.5rem;display:inline-flex;">
      📅 Agendar llamada gratuita
    </a>
    <div class="contact-cards">
      <a href="mailto:TU@EMAIL.COM" class="contact-item">
        <span class="contact-icon">✉️</span> TU@EMAIL.COM
      </a>
      <a href="https://linkedin.com/in/TU-PERFIL" target="_blank" class="contact-item">
        <span class="contact-icon">💼</span> LinkedIn
      </a>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">dave.</div>
  <div class="footer-text">© 2026 · Consultor de Datos, BI & Calidad · México</div>
</footer>

<script>
  // Scroll reveal
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if(e.isIntersecting) { e.target.classList.add('visible'); }
    });
  }, { threshold: 0.1 });
  document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
</script>
</body>
</html>
