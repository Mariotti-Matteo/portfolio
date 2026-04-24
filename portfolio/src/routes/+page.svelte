<script>

  import { base } from "$app/paths";

  // Pre-compute paths to avoid template literal issues during prerender
  $: homePath = `${base}/`;
  $: terzoPath = `${base}/terzo`;
  $: quartoPath = `${base}/quarto`;
  $: quintoPath = `${base}/quinto`;

  const anni = [
    { href: terzoPath,  label: '3° Anno', anno: '2023–2024', desc: 'Le basi: HTML, CSS e i primi passi in informatica.' },
    { href: quartoPath, label: '4° Anno', anno: '2024–2025', desc: 'JavaScript, algoritmi e primo progetto web, reti e sistemi.' },
    { href: quintoPath,  label: '5° Anno', anno: '2025–2026', desc: 'Database, svelte-kit, sistemi e reti, API' },

  ];

  const skills = ['HTML', 'CSS', 'JavaScript', 'Python', 'SQL', 'Git', 'Linux'];
</script>

<section class="hero">
  <div class="hero-tag">Portfolio Scolastico</div>
  <h1 class="hero-title">
    Matteo<br/>
    <span class="hero-name">Mariotti</span>
  </h1>
  <p class="hero-sub">
    Studente di V Informatica presso l'istituto salesiano agnelli.
    Appassionato di Primo Soccorso e NUE/118 con interesse per programmazione in Python, sistemistica e gestione.
  </p>
  <div class="hero-cta">
    <a href={quintoPath} class="btn-primary">Vedi l'ultimo anno →</a>
    <a href="mailto:matteo.mariotti2007@gmail.com" class="btn-ghost">Contattami</a>
  </div>
  <div class="hero-deco" aria-hidden="true">
    <span>{"</>"}</span>
  </div>
</section>

<section class="anni-section">
  <div class="section-label">I miei anni</div>
  <div class="anni-grid">
    {#each anni as a, i}
      <a href={a.href} class="anno-card">
        <div class="anno-number">{String(i + 3).padStart(1, '0')}</div> 
        <div class="anno-body">
          <span class="anno-periodo">{a.anno}</span>
          <h2 class="anno-label">{a.label}</h2>
          <p class="anno-desc">{a.desc}</p>
        </div>
        <div class="anno-arrow">→</div>
      </a>
    {/each}
  </div>
</section>

<section class="skills-section">
  <div class="section-label">Tecnologie studiate</div>
  <div class="skills-row">
    {#each skills as s}
      <span class="skill-pill">{s}</span>
    {/each}
  </div>
</section>

<style>
  /* ── HERO ── */
  .hero {
    position: relative;
    padding: 6rem 2.5rem 5rem;
    max-width: 860px;
    margin: 0 auto;
    overflow: hidden;
  }

  .hero-tag {
    display: inline-block;
    font-family: 'Syne', sans-serif;
    font-size: 0.72rem;
    font-weight: 600;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: #e85d26;
    border: 1.5px solid #e85d26;
    padding: 0.25rem 0.7rem;
    border-radius: 2px;
    margin-bottom: 1.5rem;
  }

  .hero-title {
    font-family: 'Syne', sans-serif;
    font-weight: 800;
    font-size: clamp(2.6rem, 7vw, 5rem);
    line-height: 1.05;
    letter-spacing: -0.03em;
    color: #1a1714;
    margin-bottom: 1.5rem;
  }

  .hero-name {
    color: #e85d26;
    display: block;
  }

  .hero-sub {
    font-size: 1.05rem;
    font-weight: 300;
    color: #5a5450;
    line-height: 1.7;
    max-width: 500px;
    margin-bottom: 2.5rem;
  }

  .hero-cta {
    display: flex;
    gap: 1rem;
    flex-wrap: wrap;
  }

  .btn-primary {
    font-family: 'Syne', sans-serif;
    font-weight: 700;
    font-size: 0.88rem;
    letter-spacing: 0.03em;
    padding: 0.75rem 1.5rem;
    background: #1a1714;
    color: #f8f5f0;
    text-decoration: none;
    border: 2px solid #1a1714;
    border-radius: 2px;
    transition: all 0.15s ease;
  }

  .btn-primary:hover {
    background: #e85d26;
    border-color: #e85d26;
  }

  .btn-ghost {
    font-family: 'Syne', sans-serif;
    font-weight: 700;
    font-size: 0.88rem;
    letter-spacing: 0.03em;
    padding: 0.75rem 1.5rem;
    background: transparent;
    color: #1a1714;
    text-decoration: none;
    border: 2px solid #1a1714;
    border-radius: 2px;
    transition: all 0.15s ease;
  }

  .btn-ghost:hover {
    background: #1a1714;
    color: #f8f5f0;
  }

  .hero-deco {
    position: absolute;
    right: 2rem;
    top: 50%;
    transform: translateY(-50%);
    font-family: 'Syne', sans-serif;
    font-size: clamp(5rem, 12vw, 9rem);
    font-weight: 800;
    color: rgba(232, 93, 38, 0.08);
    pointer-events: none;
    user-select: none;
    letter-spacing: -0.05em;
  }

  /* ── ANNI SECTION ── */
  .anni-section {
    border-top: 2px solid #1a1714;
    padding: 4rem 2.5rem;
    max-width: 860px;
    margin: 0 auto;
  }

  .section-label {
    font-family: 'Syne', sans-serif;
    font-size: 0.72rem;
    font-weight: 600;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: #9a9490;
    margin-bottom: 2rem;
  }

  .anni-grid {
    display: flex;
    flex-direction: column;
    gap: 0;
  }

  .anno-card {
    display: flex;
    align-items: center;
    gap: 2rem;
    padding: 1.75rem 0;
    border-bottom: 1.5px solid rgba(26,23,20,0.12);
    text-decoration: none;
    color: #1a1714;
    transition: all 0.15s ease;
    position: relative;
  }

  .anno-card:hover {
    padding-left: 0.75rem;
  }

  .anno-card:hover .anno-number {
    color: #e85d26;
  }

  .anno-card:hover .anno-arrow {
    transform: translateX(4px);
    color: #e85d26;
  }

  .anno-number {
    font-family: 'Syne', sans-serif;
    font-size: 2.2rem;
    font-weight: 800;
    color: rgba(26,23,20,0.12);
    min-width: 3rem;
    transition: color 0.15s ease;
  }

  .anno-body {
    flex: 1;
  }

  .anno-periodo {
    font-size: 0.78rem;
    font-weight: 400;
    color: #9a9490;
    letter-spacing: 0.05em;
  }

  .anno-label {
    font-family: 'Syne', sans-serif;
    font-weight: 700;
    font-size: 1.3rem;
    margin: 0.15rem 0 0.3rem;
    letter-spacing: -0.01em;
  }

  .anno-desc {
    font-size: 0.9rem;
    font-weight: 300;
    color: #5a5450;
    line-height: 1.5;
  }

  .anno-arrow {
    font-size: 1.4rem;
    transition: transform 0.15s ease, color 0.15s ease;
    color: #9a9490;
  }

  /* ── SKILLS ── */
  .skills-section {
    padding: 3rem 2.5rem 5rem;
    max-width: 860px;
    margin: 0 auto;
    border-top: 2px solid #1a1714;
  }

  .skills-row {
    display: flex;
    flex-wrap: wrap;
    gap: 0.6rem;
  }

  .skill-pill {
    font-family: 'Syne', sans-serif;
    font-weight: 600;
    font-size: 0.8rem;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    padding: 0.4rem 0.9rem;
    border: 1.5px solid #1a1714;
    border-radius: 2px;
    background: transparent;
    color: #1a1714;
    transition: all 0.15s ease;
  }

  .skill-pill:nth-child(3n+1):hover { background: #1a1714; color: #f8f5f0; }
  .skill-pill:hover { background: #1a1714; color: #f8f5f0; }

  @media (max-width: 600px) {
    .hero { padding: 3.5rem 1.25rem 3rem; }
    .anni-section, .skills-section { padding-left: 1.25rem; padding-right: 1.25rem; }
    .hero-deco { display: none; }
    .anno-card { gap: 1rem; }
    .anno-number { font-size: 1.5rem; min-width: 2.2rem; }
  }
</style>
