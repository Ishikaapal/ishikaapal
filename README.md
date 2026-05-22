<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ishika Pal // Celestial Core Portfolio</title>
  
  <!-- Premium Font Integrations -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;500;600&family=Plus+Jakarta+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">

  <style>
    /* DESIGN SYSTEM DESIGNATORS */
    :root {
      --bg-space: #030712;
      --text-main: #f8fafc;
      --text-muted: #94a3b8;
      --cyan-core: #22d3ee;
      --sky-glow: #38bdf8;
      --indigo-accent: #818cf8;
      --emerald-sys: #34d399;
      
      /* Dynamic positions initialized at screen centers */
      --mouse-x: 50%;
      --mouse-y: 50%;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html, body {
      width: 100%;
      min-height: 100vh;
      background-color: var(--bg-space);
      color: var(--text-main);
      font-family: 'Plus Jakarta Sans', sans-serif;
      -webkit-font-smoothing: antialiased;
      overflow-x: hidden;
    }

    /* GLOBAL SELECTION SYSTEEM */
    ::selection {
      background: rgba(34, 211, 238, 0.2);
      color: var(--cyan-core);
    }

    /* CELESTIAL BACKGROUND SYSTEMS */
    .cosmic-container {
      position: relative;
      width: 100%;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }

    /* Deep Space Ambient Nebula */
    .nebula-layer {
      position: absolute;
      inset: 0;
      pointer-events: none;
      opacity: 0.4;
      mix-blend-mode: screen;
      z-index: 1;
      transition: background 0.1s cubic-bezier(0.1, 0.8, 0.2, 1);
      background: radial-gradient(600px circle at var(--mouse-x) var(--mouse-y), rgba(14, 165, 233, 0.15), rgba(99, 102, 241, 0.05), transparent 80%);
    }

    /* High-Altitude Cosmic Grid */
    .grid-layer {
      position: absolute;
      inset: 0;
      pointer-events: none;
      opacity: 0.03;
      z-index: 1;
      background-image: 
        linear-gradient(to right, #64748b 1px, transparent 1px), 
        linear-gradient(to bottom, #64748b 1px, transparent 1px);
      background-size: 32px 32px;
    }

    /* Constellation Stars Backdrop */
    .starscape-layer {
      position: absolute;
      inset: 0;
      pointer-events: none;
      opacity: 0.25;
      mix-blend-mode: screen;
      z-index: 1;
      background-image: radial-gradient(#ffffff 1px, transparent 1px);
      background-size: 24px 24px;
      mask-image: radial-gradient(ellipse 50% % 50% at 50% 50%, #000 70%, transparent 100%);
      -webkit-mask-image: radial-gradient(ellipse 50% 50% at 50% 50%, #000 70%, transparent 100%);
    }

    /* UTILITY LAYOUT CONTAINERS */
    .max-width-wrapper {
      width: 100%;
      max-width: 80rem; /* 1280px */
      margin: 0 auto;
      padding-left: 1.5rem;
      padding-right: 1.5rem;
    }

    /* TOP NAVIGATION ARCHITECTURE */
    .system-header {
      position: relative;
      z-index: 20;
      border-bottom: 1px solid rgba(30, 41, 59, 0.4);
      backdrop-filter: blur(12px);
      -webkit-backdrop-filter: blur(12px);
      background-color: rgba(3, 7, 18, 0.2);
    }

    .header-inner {
      height: 4rem;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .brand-core {
      font-family: 'Fira Code', monospace;
      font-size: 0.875rem;
      font-weight: 600;
      letter-spacing: 0.05em;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .pulse-dot {
      height: 0.5rem;
      width: 0.5rem;
      border-radius: 50%;
      background-color: var(--cyan-core);
      animation: pulse-glow 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
    }

    @keyframes pulse-glow {
      0%, 100% { opacity: 1; transform: scale(1); }
      50% { opacity: .4; transform: scale(0.9); }
    }

    .nav-matrix {
      display: none;
      align-items: center;
      gap: 2rem;
    }

    @media (min-width: 768px) {
      .nav-matrix { display: flex; }
    }

    .nav-link {
      font-family: 'Fira Code', monospace;
      font-size: 0.75rem;
      letter-spacing: 0.1em;
      color: var(--text-muted);
      text-decoration: none;
      transition: color 0.2s ease;
    }

    .nav-link:hover {
      color: var(--cyan-core);
    }

    .init-button {
      font-family: 'Fira Code', monospace;
      font-size: 0.75rem;
      font-weight: 500;
      color: #cbd5e1;
      text-decoration: none;
      padding: 0.375rem 1rem;
      border-radius: 9999px;
      border: 1px solid #1e293b;
      background-color: rgba(15, 23, 42, 0.6);
      transition: all 0.2s ease;
      box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.4);
    }

    .init-button:hover {
      border-color: #334155;
      color: #ffffff;
    }

    /* MAIN HERO INTERFACE */
    .main-interface {
      position: relative;
      z-index: 10;
      flex-grow: 1;
      display: flex;
      align-items: center;
      padding-top: 5rem;
      padding-bottom: 5rem;
    }

    .grid-architecture {
      display: grid;
      grid-template-columns: 1fr;
      gap: 3rem;
      width: 100%;
    }

    @media (min-width: 1024px) {
      .grid-architecture {
        grid-template-columns: repeat(12, minmax(0, 1fr));
      }
    }

    /* LEFT SIDE: TYPOGRAPHY BLOCKS */
    .typography-block {
      display: flex;
      flex-direction: column;
      gap: 2rem;
    }

    @media (min-width: 1024px) {
      .typography-block { grid-column: span 7 / span 7; }
    }

    .ambient-tag {
      align-self: flex-start;
      display: flex;
      align-items: center;
      gap: 0.5rem;
      padding: 0.25rem 0.75rem;
      border-radius: 9999px;
      border: 1px solid rgba(6, 182, 212, 0.2);
      background-color: rgba(6, 182, 212, 0.05);
      font-family: 'Fira Code', monospace;
      font-size: 0.75rem;
      font-weight: 500;
      color: var(--cyan-core);
      letter-spacing: 0.05em;
    }

    .title-system h1 {
      font-size: 2.5rem;
      font-weight: 700;
      letter-spacing: -0.025em;
      line-height: 1.1;
      color: #ffffff;
      margin-bottom: 1rem;
    }

    @media (min-width: 768px) {
      .title-system h1 { font-size: 3.75rem; }
    }

    .gradient-text {
      background: linear-gradient(to right, #22d3ee, #38bdf8, #818cf8);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .description-text {
      max-width: 36rem;
      font-size: 1rem;
      line-height: 1.625;
      color: var(--text-muted);
    }

    @media (min-width: 768px) {
      .description-text { font-size: 1.125rem; }
    }

    .cta-cluster {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      gap: 1rem;
    }

    .btn-primary {
      position: relative;
      padding: 0.75rem 1.5rem;
      border-radius: 0.75rem;
      background: linear-gradient(to right, #06b6d4, #6366f1);
      font-size: 0.875rem;
      font-weight: 600;
      color: #ffffff;
      text-decoration: none;
      transition: all 0.2s ease;
      box-shadow: 0 20px 25px -5px rgba(6, 182, 212, 0.1);
    }

    .btn-primary:hover {
      box-shadow: 0 20px 25px -5px rgba(6, 182, 212, 0.25);
      transform: translateY(-2px);
    }

    .btn-primary .arrow {
      display: inline-block;
      margin-left: 0.5rem;
      transition: transform 0.2s ease;
    }

    .btn-primary:hover .arrow {
      transform: translateX(4px);
    }

    .btn-secondary {
      padding: 0.75rem 1.5rem;
      border-radius: 0.75rem;
      border: 1px solid #1e293b;
      background-color: rgba(15, 23, 42, 0.4);
      font-size: 0.875rem;
      font-weight: 600;
      color: #cbd5e1;
      text-decoration: none;
      backdrop-filter: blur(4px);
      -webkit-backdrop-filter: blur(4px);
      transition: all 0.2s ease;
    }

    .btn-secondary:hover {
      border-color: #334155;
      background-color: rgba(15, 23, 42, 0.6);
    }

    /* RIGHT SIDE: BENTO SYSTEM MATRIX */
    .bento-column {
      position: relative;
    }

    @media (min-width: 1024px) {
      .bento-column { grid-column: span 5 / span 5; }
    }

    .bento-card {
      position: relative;
      border-radius: 1rem;
      border: 1px solid rgba(30, 41, 59, 0.8);
      background-color: rgba(3, 7, 18, 0.4);
      padding: 1.5rem;
      backdrop-filter: blur(24px);
      -webkit-backdrop-filter: blur(24px);
      box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.8);
    }

    /* Top Linear Neon Edge Border Accent */
    .bento-card::before {
      content: '';
      position: absolute;
      top: -1px;
      left: 0;
      right: 0;
      height: 1px;
      background: linear-gradient(to right, transparent, rgba(34, 211, 238, 0.5), transparent);
    }

    .window-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      border-bottom: 1px solid #0f172a;
      padding-bottom: 1rem;
      margin-bottom: 1.5rem;
    }

    .window-dots {
      display: flex;
      gap: 0.375rem;
    }

    .dot {
      height: 0.75rem;
      width: 0.75rem;
      border-radius: 50%;
    }
    .dot-r { background-color: rgba(239, 68, 68, 0.4); }
    .dot-y { background-color: rgba(234, 179, 8, 0.4); }
    .dot-g { background-color: rgba(34, 197, 94, 0.4); }

    .window-title {
      font-family: 'Fira Code', monospace;
      font-size: 0.625rem;
      letter-spacing: 0.1em;
      color: #64748b;
    }

    .matrix-readout {
      display: flex;
      flex-direction: column;
      gap: 1rem;
      font-family: 'Fira Code', monospace;
      font-size: 0.75rem;
    }

    .matrix-row {
      display: flex;
      align-items: baseline;
      justify-content: space-between;
      border-bottom: 1px solid rgba(15, 23, 42, 0.6);
      padding-bottom: 0.5rem;
    }

    .matrix-row:last-of-type {
      border-bottom: none;
      padding-bottom: 0;
      padding-top: 0.25rem;
    }

    .label-sys { color: #64748b; }
    .val-engine { color: var(--cyan-core); }
    .val-flow { color: var(--sky-glow); }
    .val-vault { color: var(--indigo-accent); }
    .val-anim { color: var(--emerald-sys); }

    .status-badge {
      display: inline-flex;
      align-items: center;
      gap: 0.375rem;
      color: var(--emerald-sys);
      font-weight: 600;
    }

    .ping-dot {
      height: 0.375rem;
      width: 0.375rem;
      border-radius: 50%;
      background-color: var(--emerald-sys);
      position: relative;
    }

    .ping-dot::after {
      content: '';
      position: absolute;
      inset: 0;
      border-radius: 50%;
      background-color: var(--emerald-sys);
      animation: ping-wave 1s cubic-bezier(0, 0, 0.2, 1) infinite;
    }

    @keyframes ping-wave {
      75%, 100% { transform: scale(2.5); opacity: 0; }
    }

    /* FOOTER METRICS SYSTEM */
    .system-footer {
      position: relative;
      z-index: 10;
      border-top: 1px solid rgba(15, 23, 42, 0.6);
      background-color: rgba(3, 7, 18, 0.2);
      padding-top: 2rem;
      padding-bottom: 2rem;
      backdrop-filter: blur(4px);
      -webkit-backdrop-filter: blur(4px);
    }

    .footer-grid {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 1.5rem;
    }

    @media (min-width: 768px) {
      .footer-grid {
        grid-template-columns: repeat(4, minmax(0, 1fr));
      }
    }

    .stat-metric {
      font-size: 1.5rem;
      font-weight: 700;
      font-family: 'Fira Code', monospace;
      color: #ffffff;
    }

    .stat-metric.highlight-cyan { color: var(--cyan-core); }
    .stat-metric.highlight-indigo { color: var(--indigo-accent); }

    .stat-label {
      font-family: 'Fira Code', monospace;
      font-size: 0.625rem;
      text-transform: uppercase;
      letter-spacing: 0.05em;
      color: #64748b;
      margin-top: 0.25rem;
    }
  </style>
</head>
<body>

  <div class="cosmic-container" id="cosmicRoot">
    <!-- CELESTIAL BACKGROUND LAYERS -->
    <div class="nebula-layer" id="nebula"></div>
    <div class="grid-layer"></div>
    <div class="starscape-layer"></div>

    <!-- TOP NAVIGATION ARCHITECTURE -->
    <header class="system-header">
      <div class="max-width-wrapper header-inner">
        <div class="brand-core">
          <span class="pulse-dot"></span>
          ISHIKA_PAL // SYSTEM_CORE
        </div>
        <nav class="nav-matrix">
          <a href="#context" class="nav-link">01 // CONTEXT</a>
          <a href="#ecosystem" class="nav-link">02 // ECOSYSTEM</a>
          <a href="#deployments" class="nav-link">03 // DEPLOYMENTS</a>
        </nav>
        <div>
          <a href="https://github.com/YOUR_GITHUB_USERNAME" class="init-button" target="_blank">System.init()</a>
        </div>
      </div>
    </header>

    <!-- MAIN HERO INTERFACE -->
    <main class="main-interface">
      <div class="max-width-wrapper">
        <div class="grid-architecture">
          
          <!-- LEFT: CORE PHILOSOPHY & HEADLINE -->
          <section class="typography-block">
            <div class="ambient-tag">
              <span>✦</span> CURRENT ORBIT: FULL-STACK ARCHITECTURES
            </div>
            <div class="title-system">
              <h1>
                Engineering Fluid Digital <br>
                <span class="gradient-text">Ecosystems</span>
              </h1>
              <p class="description-text">
                I build high-performance web ecosystems sitting precisely at the coordinates of robust backend concurrency and pixel-perfect micro-interactions.
              </p>
            </div>
            <div class="cta-cluster">
              <a href="#deployments" class="btn-primary">
                Explore Systems <span class="arrow">→</span>
              </a>
              <a href="https://linkedin.com/in/YOUR_LINKEDIN_USERNAME" class="btn-secondary" target="_blank">
                Connect Matrix
              </a>
            </div>
          </section>

          <!-- RIGHT: BENTO TECH SPEC MATRIX -->
          <aside class="bento-column">
            <div class="bento-card">
              <div class="window-header">
                <div class="window-dots">
                  <span class="dot dot-r"></span>
                  <span class="dot dot-y"></span>
                  <span class="dot dot-g"></span>
                </div>
                <div class="window-title">KERNEL_LOG.MD</div>
              </div>
              
              <div class="matrix-readout">
                <div class="matrix-row">
                  <span class="label-sys">ENGINE:</span>
                  <span class="val-engine">React // Next.js</span>
                </div>
                <div class="matrix-row">
                  <span class="label-sys">DATA_FLOW:</span>
                  <span class="val-flow">REST // WebSockets</span>
                </div>
                <div class="matrix-row">
                  <span class="label-sys">STATE_VAULT:</span>
                  <span class="val-vault">MongoDB // Redis</span>
                </div>
                <div class="matrix-row">
                  <span class="label-sys">ANIMATION:</span>
                  <span class="val-anim">Tailwind + Framer</span>
                </div>
                <div class="matrix-row">
                  <span class="label-sys">STATUS:</span>
                  <span class="status-badge">
                    <span class="ping-dot"></span>
                    OPERATIONAL
                  </span>
                </div>
              </div>
            </div>
          </aside>

        </div>
      </div>
    </main>

    <!-- LOWER ARCHITECTURAL STATS FOOTHOLD -->
    <footer class="system-footer">
      <div class="max-width-wrapper footer-grid">
        <div>
          <div class="stat-metric">04+</div>
          <div class="stat-label">Core Platforms Dev</div>
        </div>
        <div>
          <div class="stat-metric highlight-cyan">99.9%</div>
          <div class="stat-label">State Responsiveness</div>
        </div>
        <div>
          <div class="stat-metric">0ms</div>
          <div class="stat-label">Layout Shift Goal</div>
        </div>
        <div>
          <div class="stat-metric highlight-indigo">MERN</div>
          <div class="stat-label">Architectural Anchor</div>
        </div>
      </div>
    </footer>
  </div>

  <!-- INTERACTIVE NEBULA CORE CONTROLLER -->
  <script>
    const rootContainer = document.getElementById('cosmicRoot');

    rootContainer.addEventListener('mousemove', (e) => {
      const rect = rootContainer.getBoundingClientRect();
      
      // Calculate dynamic viewport values based on current bounding bounds
      const x = e.clientX - rect.left;
      const y = e.clientY - rect.top;
      
      // Bind coordinate updates seamlessly to CSS Root properties
      rootContainer.style.setProperty('--mouse-x', `${x}px`);
      rootContainer.style.setProperty('--mouse-y', `${y}px`);
    });
  </script>
</body>
</html>
