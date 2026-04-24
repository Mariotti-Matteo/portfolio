<script>
  import { page } from '$app/stores';
  import { base } from '$app/paths';
</script>

<div class="site-wrapper">
  <nav class="navbar">
    <a href="{base}/" class="logo">Matteo</a>
    <ul class="nav-links">
      <li>
        <a href="{base}/" class:active={$page.url.pathname === `${base}/`}>Home</a>
      </li>
      <li>
        <a href="{base}/terzo" class:active={$page.url.pathname === `${base}/terzo`}>3° Anno</a>
      </li>
      <li>
        <a href="{base}/quarto" class:active={$page.url.pathname === `${base}/quarto`}>4° Anno</a>
      </li>
      <li>
        <a href="{base}/quinto" class:active={$page.url.pathname === `${base}/quinto`}>5° Anno</a>
      </li>
    </ul>
  </nav>

  <main>
    <slot />
  </main>

  <footer class="footer">
    <div class="footer-inner">
      <p class="footer-name">Matteo Mariotti — Studente di Informatica</p>
      <div class="footer-links">
        <a href="https://instagram.com/not_immqtte" target="_blank" rel="noopener" class="footer-link">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <rect x="2" y="2" width="20" height="20" rx="5" ry="5"/>
            <circle cx="12" cy="12" r="4"/>
            <circle cx="17.5" cy="6.5" r="1" fill="currentColor" stroke="none"/>
          </svg>
          @not_immqtte
        </a>
        <span class="footer-sep">·</span>
        <a href="mailto:matteo.mariotti2007@gmail.com" class="footer-link">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <rect x="2" y="4" width="20" height="16" rx="2"/>
            <polyline points="2,4 12,13 22,4"/>
          </svg>
          matteo.mariotti2007@gmail.com
        </a>
      </div>
      <p class="footer-copy">© 2025 Matteo Mariotti</p>
    </div>
  </footer>
</div>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap');

  :global(*, *::before, *::after) {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  :global(html) {
    font-family: 'DM Sans', sans-serif;
    background: #f8f5f0;
    color: #1a1714;
    scroll-behavior: smooth;
  }

  :global(body) {
    min-height: 100vh;
  }

  .site-wrapper {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
  }

  /* ── NAVBAR ── */
  .navbar {
    position: sticky;
    top: 0;
    z-index: 100;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 1.1rem 2.5rem;
    background: #f8f5f0;
    border-bottom: 2px solid #1a1714;
  }

  .logo {
    font-family: 'Syne', sans-serif;
    font-weight: 800;
    font-size: 1.5rem;
    color: #1a1714;
    text-decoration: none;
    letter-spacing: -0.02em;
  }

  /* .logo span {
    color: #e85d26;
  } */

  .nav-links {
    list-style: none;
    display: flex;
    gap: 0.25rem;
  }

  .nav-links a {
    font-family: 'Syne', sans-serif;
    font-weight: 600;
    font-size: 0.85rem;
    text-decoration: none;
    color: #1a1714;
    padding: 0.4rem 0.9rem;
    border: 2px solid transparent;
    border-radius: 2px;
    transition: all 0.15s ease;
    letter-spacing: 0.04em;
    text-transform: uppercase;
  }

  .nav-links a:hover {
    border-color: #1a1714;
  }

  .nav-links a.active {
    background: #1a1714;
    color: #f8f5f0;
  }

  /* ── MAIN ── */
  main {
    flex: 1;
  }

  /* ── FOOTER ── */
  .footer {
    background: #1a1714;
    color: #f8f5f0;
    border-top: 2px solid #e85d26;
    padding: 2rem 2.5rem;
  }

  .footer-inner {
    max-width: 900px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.8rem;
    text-align: center;
  }

  .footer-name {
    font-family: 'Syne', sans-serif;
    font-weight: 700;
    font-size: 1rem;
    letter-spacing: 0.02em;
  }

  .footer-links {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    flex-wrap: wrap;
    justify-content: center;
  }

  .footer-link {
    display: flex;
    align-items: center;
    gap: 0.4rem;
    color: #f8f5f0;
    text-decoration: none;
    font-size: 0.9rem;
    font-weight: 400;
    padding: 0.35rem 0.75rem;
    border: 1.5px solid rgba(248,245,240,0.2);
    border-radius: 2px;
    transition: all 0.15s ease;
  }

  .footer-link:hover {
    border-color: #e85d26;
    color: #e85d26;
  }

  .footer-sep {
    color: rgba(248,245,240,0.3);
    font-size: 1.2rem;
  }

  .footer-copy {
    font-size: 0.78rem;
    color: rgba(248,245,240,0.4);
    font-style: italic;
    margin-top: 0.25rem;
  }

  @media (max-width: 600px) {
    .navbar {
      flex-direction: column;
      gap: 0.75rem;
      padding: 1rem 1.25rem;
    }
    .nav-links {
      flex-wrap: wrap;
      justify-content: center;
    }
    .footer-sep { display: none; }
  }
</style>
