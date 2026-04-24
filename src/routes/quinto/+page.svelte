<script>
  import { base } from "$app/paths";

  // const materie = [
  //   { nome: 'Informatica', voto: 0, nota: 'N/A' },
  //   { nome: 'Sistemi e Reti', voto: 0, nota: 'N/A' },
  //   { nome: 'Italiano', voto: 0, nota: 'N/A' },
  //   { nome: 'Inglese', voto: 0, nota: 'N/A' },
  //   { nome: 'Matematica', voto: 0, nota: 'N/A' },
  //   { nome: 'TPSI', voto: 0, nota: 'N/A' },
  // ];

  const progetti = [
    {
      titolo: '1522',
      desc: 'Database relazionale per gestire amministratori, utenti e urgenze. Schema ER, normalizzazione e query complesse in SQL.',
      tech: ['SQL', 'MySQL', 'HTML', 'CSS'],
      icona: '📚',
      highlight: false,
      stato: 'Completato',
    },
  ];

  const obiettivi = [
    { testo: 'Iscrizione Università', fatto: false },
    { testo: 'Completamento Tirocinio TSSA - CRI', fatto: false },
    { testo: 'Arruolamento nel Corpo Militare di Croce Rossa Italiana', fatto: false },
    { testo: 'Allegato Trasporto Infermi e Soccorso in Ambulanza - Croce Rossa Italiana', fatto: true },
    { testo: 'Allegato Trasporto Infermi - Croce Rossa Italiana', fatto: true },
  ];
</script>

<div class="page-wrapper">
  <header class="page-header">
    <a href="{base}/" class="back-link">← Torna alla home</a>
    <div class="year-badge">05</div>
    <div class="current-badge">Anno in corso</div>
    <h1 class="page-title">Quinto Anno</h1>
    <p class="page-period">2025 — 2026</p>
    <p class="page-intro">
      L'anno più intenso. Database, SvelteKit, Sistemi e Reti, API e tanto altro.
      Un anno di crescita, sfide e preparazione per il futuro.
    </p>
  </header>

  <!-- <section class="section">
    <h2 class="section-title">Materie & Voti</h2>
    <div class="materie-grid">
      {#each materie as m}
        <div class="materia-card">
          <div class="materia-top">
            <span class="materia-nome">{m.nome}</span>
            <span class="materia-voto" class:ottimo={m.voto >= 8} class:buono={m.voto === 7} class:sufficiente={m.voto <= 6}>
              {m.voto}
            </span>
          </div>
          <p class="materia-nota">{m.nota}</p>
          <div class="materia-bar">
            <div class="materia-bar-fill" style="width: {(m.voto / 10) * 100}%"></div>
          </div>
        </div>
      {/each}
    </div>
  </section> -->

  <section class="section">
    <h2 class="section-title">Progetti</h2>
    <div class="progetti-list">
      {#each progetti as p}
        <div class="progetto-card" class:highlight={p.highlight}>
          {#if p.highlight}
            <div class="highlight-badge">Best project</div>
          {/if}
          <div class="progetto-icona">{p.icona}</div>
          <div class="progetto-body">
            <div class="progetto-header">
              <h3 class="progetto-titolo">{p.titolo}</h3>
              <span class="stato-badge" class:in-corso={p.stato === 'In corso'}>{p.stato}</span>
            </div>
            <p class="progetto-desc">{p.desc}</p>
            <div class="progetto-tech">
              {#each p.tech as t}
                <span class="tech-tag">{t}</span>
              {/each}
            </div>
          </div>
        </div>
      {/each}
    </div>
  </section>

  <section class="section">
    <h2 class="section-title">Obiettivi dell'anno</h2>
    <div class="obiettivi-list">
      {#each obiettivi as o}
        <div class="obiettivo" class:fatto={o.fatto}>
          <span class="obiettivo-check">
            {#if o.fatto}✓{:else}○{/if}
          </span>
          <span class="obiettivo-testo">{o.testo}</span>
        </div>
      {/each}
    </div>
  </section>

  <div class="nav-anni">
    <a href="{base}/quarto" class="btn-prev">← 4° Anno</a>
    <!-- <a href="mailto:marco.rossi@email.com" class="btn-contact">Contattami →</a> -->
  </div>
</div>

<style>
  .page-wrapper {
    max-width: 860px;
    margin: 0 auto;
    padding: 3rem 2.5rem 5rem;
  }

  .back-link {
    font-family: 'Syne', sans-serif;
    font-size: 0.8rem;
    font-weight: 600;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    color: #9a9490;
    text-decoration: none;
    transition: color 0.15s;
    display: inline-block;
    margin-bottom: 2.5rem;
  }

  .back-link:hover { color: #e85d26; }

  .page-header {
    border-bottom: 2px solid #1a1714;
    padding-bottom: 2.5rem;
    margin-bottom: 3.5rem;
    position: relative;
  }

  .year-badge {
    font-family: 'Syne', sans-serif;
    font-size: 7rem;
    font-weight: 800;
    color: rgba(26,23,20,0.06);
    line-height: 1;
    position: absolute;
    right: 0;
    top: 0;
    pointer-events: none;
  }

  .current-badge {
    display: inline-block;
    font-family: 'Syne', sans-serif;
    font-size: 0.68rem;
    font-weight: 700;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    background: #e85d26;
    color: #fff;
    padding: 0.2rem 0.6rem;
    border-radius: 2px;
    margin-bottom: 0.75rem;
  }

  .page-title {
    font-family: 'Syne', sans-serif;
    font-weight: 800;
    font-size: clamp(2rem, 5vw, 3.5rem);
    letter-spacing: -0.03em;
    color: #1a1714;
    margin-bottom: 0.25rem;
  }

  .page-period {
    font-family: 'Syne', sans-serif;
    font-size: 0.85rem;
    font-weight: 600;
    color: #e85d26;
    letter-spacing: 0.1em;
    margin-bottom: 1.25rem;
  }

  .page-intro {
    font-size: 1rem;
    font-weight: 300;
    color: #5a5450;
    line-height: 1.75;
    max-width: 580px;
  }

  .page-intro em {
    font-style: italic;
    color: #1a1714;
  }

  .section {
    margin-bottom: 3.5rem;
  }

  .section-title {
    font-family: 'Syne', sans-serif;
    font-weight: 700;
    font-size: 1.1rem;
    letter-spacing: -0.01em;
    margin-bottom: 1.5rem;
    padding-bottom: 0.5rem;
    border-bottom: 1.5px solid rgba(26,23,20,0.12);
  }

  /* MATERIE */
  /* .materie-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
    gap: 1rem;
  }

  .materia-card {
    padding: 1.1rem 1.25rem;
    border: 1.5px solid rgba(26,23,20,0.15);
    border-radius: 4px;
    background: #fff;
    transition: border-color 0.15s;
  }

  .materia-card:hover { border-color: #1a1714; }

  .materia-top {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 0.4rem;
  }

  .materia-nome {
    font-family: 'Syne', sans-serif;
    font-weight: 700;
    font-size: 0.9rem;
  }

  .materia-voto {
    font-family: 'Syne', sans-serif;
    font-weight: 800;
    font-size: 1.1rem;
    width: 2rem;
    height: 2rem;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 2px;
  }

  .materia-voto.ottimo { background: #1a1714; color: #f8f5f0; }
  .materia-voto.buono { background: #e85d26; color: #fff; }
  .materia-voto.sufficiente { background: rgba(26,23,20,0.1); color: #1a1714; }

  .materia-nota {
    font-size: 0.8rem;
    font-weight: 300;
    color: #5a5450;
    line-height: 1.5;
    margin-bottom: 0.75rem;
  }

  .materia-bar {
    height: 3px;
    background: rgba(26,23,20,0.1);
    border-radius: 2px;
    overflow: hidden;
  }

  .materia-bar-fill {
    height: 100%;
    background: #e85d26;
    border-radius: 2px;
  } */

  /* PROGETTI */
  .progetti-list {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .progetto-card {
    display: flex;
    gap: 1.25rem;
    padding: 1.25rem 1.5rem;
    border: 1.5px solid rgba(26,23,20,0.15);
    border-radius: 4px;
    background: #fff;
    transition: border-color 0.15s, transform 0.15s;
    position: relative;
  }

  .progetto-card:hover {
    border-color: #1a1714;
    transform: translateX(4px);
  }

  .progetto-card.highlight {
    border-color: #e85d26;
    background: #fff9f6;
  }

  .highlight-badge {
    position: absolute;
    top: -1px;
    right: 1rem;
    font-family: 'Syne', sans-serif;
    font-size: 0.65rem;
    font-weight: 700;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    background: #e85d26;
    color: #fff;
    padding: 0.15rem 0.5rem;
    border-radius: 0 0 2px 2px;
  }

  .progetto-icona {
    font-size: 1.8rem;
    flex-shrink: 0;
    margin-top: 0.1rem;
  }

  .progetto-header {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    margin-bottom: 0.35rem;
    flex-wrap: wrap;
  }

  .progetto-titolo {
    font-family: 'Syne', sans-serif;
    font-weight: 700;
    font-size: 1rem;
  }

  .stato-badge {
    font-family: 'Syne', sans-serif;
    font-size: 0.65rem;
    font-weight: 700;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    padding: 0.15rem 0.45rem;
    border-radius: 2px;
    background: rgba(26,23,20,0.08);
    color: #5a5450;
  }

  .stato-badge.in-corso {
    background: rgba(232, 93, 38, 0.12);
    color: #e85d26;
  }

  .progetto-desc {
    font-size: 0.88rem;
    font-weight: 300;
    color: #5a5450;
    line-height: 1.6;
    margin-bottom: 0.75rem;
  }

  .progetto-tech {
    display: flex;
    gap: 0.4rem;
    flex-wrap: wrap;
  }

  .tech-tag {
    font-family: 'Syne', sans-serif;
    font-size: 0.7rem;
    font-weight: 600;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    padding: 0.2rem 0.5rem;
    border: 1px solid rgba(26,23,20,0.2);
    border-radius: 2px;
    color: #5a5450;
  }

  /* OBIETTIVI */
  .obiettivi-list {
    display: flex;
    flex-direction: column;
    gap: 0.6rem;
  }

  .obiettivo {
    display: flex;
    align-items: center;
    gap: 0.9rem;
    padding: 0.75rem 1rem;
    border: 1.5px solid rgba(26,23,20,0.12);
    border-radius: 4px;
    background: #fff;
  }

  .obiettivo.fatto {
    background: #f0fdf4;
    border-color: rgba(34, 197, 94, 0.3);
  }

  .obiettivo-check {
    font-family: 'Syne', sans-serif;
    font-weight: 800;
    font-size: 0.9rem;
    width: 1.4rem;
    height: 1.4rem;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 50%;
    flex-shrink: 0;
    color: #9a9490;
    border: 1.5px solid rgba(26,23,20,0.15);
  }

  .obiettivo.fatto .obiettivo-check {
    background: #22c55e;
    color: #fff;
    border-color: #22c55e;
  }

  .obiettivo-testo {
    font-size: 0.9rem;
    font-weight: 400;
    color: #1a1714;
  }

  .obiettivo.fatto .obiettivo-testo {
    color: #5a5450;
    text-decoration: line-through;
    text-decoration-color: #22c55e;
  }

  /* NAV */
  .nav-anni {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-top: 2rem;
    border-top: 1.5px solid rgba(26,23,20,0.12);
  }

  /* .btn-prev, .btn-contact {
    font-family: 'Syne', sans-serif;
    font-weight: 700;
    font-size: 0.88rem;
    letter-spacing: 0.03em;
    padding: 0.7rem 1.4rem;
    text-decoration: none;
    border: 2px solid #1a1714;
    border-radius: 2px;
    transition: all 0.15s ease;
    color: #1a1714;
    background: transparent;
  } */

  .btn-prev:hover { background: #1a1714; color: #f8f5f0; }
  /* .btn-contact { background: #e85d26; border-color: #e85d26; color: #fff; }
  .btn-contact:hover { background: #c94d1a; border-color: #c94d1a; } */

  @media (max-width: 600px) {
    .page-wrapper { padding: 2rem 1.25rem 4rem; }
    /* .materie-grid { grid-template-columns: 1fr; } */
    .year-badge { font-size: 4rem; }
  }
</style>
