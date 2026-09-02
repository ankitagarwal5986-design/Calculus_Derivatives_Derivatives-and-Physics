<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Brain and Mind Academy | Honors Precalculus & Physics: Derivatives & Motion (14.1 WS #2)</title>
  
  <!-- MathJax Configuration for Crisp Mathematical Equation Typesetting -->
  <script>
    window.MathJax = {
      tex: {
        inlineMath: [['\\(', '\\)'], ['$', '$']],
        displayMath: [['\\[', '\\]'], ['$$', '$$']],
        processEscapes: true
      },
      options: {
        skipHtmlTags: ['script', 'noscript', 'style', 'textarea', 'pre', 'code']
      },
      startup: {
        pageReady: () => {
          return MathJax.startup.defaultPageReady();
        }
      }
    };
  </script>
  <script type="text/javascript" id="MathJax-script" async
    src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
  </script>

  <style>
    :root {
      --primary-green: #15803d;
      --primary-dark: #064e3b;
      --accent-green: #16a34a;
      --accent-mint: #22c55e;
      --light-green-bg: #f0fdf4;
      --mint-border: #86efac;
      --mint-border-soft: #bbf7d0;
      --card-white: #ffffff;
      --correct-green: #059669;
      --correct-green-light: #d1fae5;
      --incorrect-red: #dc2626;
      --incorrect-red-light: #fee2e2;
      --accent-gold: #d97706;
      --accent-gold-light: #fef3c7;
      --skipped-amber: #f59e0b;
      --skipped-amber-light: #fffbeb;
      --unvisited-gray: #94a3b8;
      --unvisited-light: #f8fafc;
      --text-main: #0f172a;
      --text-muted: #475569;
      --radius-sm: 8px;
      --radius-md: 14px;
      --radius-lg: 20px;
      --shadow-sm: 0 1px 3px rgba(22, 163, 74, 0.08);
      --shadow-md: 0 4px 8px -1px rgba(22, 163, 74, 0.12), 0 2px 4px -2px rgba(22, 163, 74, 0.06);
      --shadow-lg: 0 12px 24px -4px rgba(21, 128, 61, 0.15), 0 4px 8px -2px rgba(21, 128, 61, 0.06);
    }

    * { box-sizing: border-box; margin: 0; padding: 0; }
    body {
      font-family: 'Segoe UI', -apple-system, BlinkMacSystemFont, Roboto, sans-serif;
      background: linear-gradient(180deg, #f0fdf4 0%, #ffffff 320px, #f0fdf4 100%);
      color: var(--text-main);
      line-height: 1.6;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }

    /* Header */
    header {
      background: linear-gradient(135deg, var(--primary-dark) 0%, var(--primary-green) 60%, var(--accent-green) 100%);
      color: #ffffff; padding: 1.1rem 1.75rem; box-shadow: var(--shadow-md); position: sticky; top: 0; z-index: 100;
    }
    .header-container {
      max-width: 1440px; margin: 0 auto; display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 1rem;
    }
    .brand-group { display: flex; align-items: center; gap: 14px; }
    .brand-logo {
      width: 44px; height: 44px; background: #ffffff;
      border-radius: 12px; display: flex; align-items: center; justify-content: center; font-weight: 800; color: var(--primary-green); font-size: 1.45rem; box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
    }
    .brand-title h1 { font-size: 1.25rem; font-weight: 700; letter-spacing: -0.02em; }
    .brand-title p { font-size: 0.82rem; color: #bbf7d0; }
    .user-actions { display: flex; align-items: center; gap: 10px; flex-wrap: wrap; }
    .user-badge {
      background: rgba(255, 255, 255, 0.18); border: 1px solid rgba(255, 255, 255, 0.3);
      padding: 6px 14px; border-radius: 20px; font-size: 0.85rem; color: #f1f5f9; display: flex; align-items: center; gap: 6px;
    }
    .btn-icon {
      background: rgba(255, 255, 255, 0.22); border: none; color: #ffffff; padding: 8px 14px; border-radius: var(--radius-sm); cursor: pointer; font-size: 0.85rem; font-weight: 600; transition: all 0.2s;
    }
    .btn-icon:hover { background: rgba(255, 255, 255, 0.35); transform: translateY(-1px); }

    main { max-width: 1440px; width: 100%; margin: 1.5rem auto; padding: 0 1rem; flex: 1; }
    .view-section { display: none; }
    .view-section.active { display: block; animation: fadeIn 0.25s ease-in-out; }
    @keyframes fadeIn { from { opacity: 0; transform: translateY(6px); } to { opacity: 1; transform: translateY(0); } }

    /* Portal Card */
    .card-center { max-width: 620px; margin: 3.5rem auto; background: var(--card-white); border-radius: var(--radius-lg); padding: 2.75rem; box-shadow: var(--shadow-lg); border: 2px solid var(--mint-border-soft); text-align: center; }
    .login-icon { width: 72px; height: 72px; background: #f0fdf4; color: var(--primary-green); border-radius: 50%; display: flex; align-items: center; justify-content: center; margin: 0 auto 1.25rem auto; font-size: 2.2rem; box-shadow: 0 4px 12px rgba(22, 163, 74, 0.2); border: 2px solid var(--mint-border); }
    .form-group { text-align: left; margin-bottom: 1.25rem; }
    .form-group label { display: block; font-size: 0.88rem; font-weight: 600; margin-bottom: 6px; color: var(--primary-dark); }
    .form-control { width: 100%; padding: 13px; border: 1.5px solid var(--mint-border-soft); border-radius: var(--radius-sm); font-size: 1rem; outline: none; transition: border-color 0.2s; background: #fafdfb; }
    .form-control:focus { border-color: var(--primary-green); box-shadow: 0 0 0 3px rgba(22, 163, 74, 0.2); background: #ffffff; }
    .btn-primary { width: 100%; background: linear-gradient(135deg, var(--primary-green), var(--accent-green)); color: #ffffff; border: none; padding: 14px; font-weight: 700; font-size: 1.02rem; border-radius: var(--radius-sm); cursor: pointer; box-shadow: 0 4px 10px rgba(22, 163, 74, 0.35); transition: all 0.2s ease; }
    .btn-primary:hover { box-shadow: 0 6px 14px rgba(22, 163, 74, 0.45); transform: translateY(-1px); }

    /* Theory Review Card */
    .notes-card { max-width: 1080px; margin: 1.5rem auto; background: var(--card-white); border-radius: var(--radius-lg); padding: 2.75rem; border: 2px solid var(--mint-border-soft); box-shadow: var(--shadow-lg); }
    .notes-header { border-bottom: 2px solid var(--mint-border-soft); padding-bottom: 1.25rem; margin-bottom: 1.5rem; }
    .notes-header h2 { color: var(--primary-dark); font-size: 1.7rem; }
    .notes-body h3 { color: var(--primary-green); margin: 1.8rem 0 0.6rem 0; font-size: 1.25rem; border-bottom: 1.5px solid var(--mint-border-soft); padding-bottom: 5px; }
    .notes-body p, .notes-body ul { color: var(--text-main); font-size: 1.02rem; line-height: 1.8; margin-bottom: 1rem; }
    .notes-body ul { padding-left: 1.6rem; }
    .formula-callout { background: #f0fdf4; border: 1px solid var(--mint-border-soft); border-left: 4px solid var(--primary-green); padding: 14px 18px; border-radius: var(--radius-sm); margin: 14px 0; font-size: 1.05rem; }
    .notes-confirm-box { background: #f0fdf4; border: 2px solid var(--mint-border); border-radius: var(--radius-md); padding: 1.5rem; display: flex; align-items: center; justify-content: space-between; flex-wrap: wrap; gap: 1rem; margin-top: 2rem; }

    /* Learning Workspace Grid */
    .learning-grid-layout { display: grid; grid-template-columns: 1fr 380px; gap: 1.5rem; align-items: start; }
    @media (max-width: 1080px) { .learning-grid-layout { grid-template-columns: 1fr; } }
    
    .problem-card { background: var(--card-white); border-radius: var(--radius-lg); padding: 2rem; box-shadow: var(--shadow-md); border: 2px solid var(--mint-border-soft); }
    .problem-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 1.25rem; padding-bottom: 0.75rem; border-bottom: 1.5px solid var(--mint-border-soft); }
    .p-tag { font-size: 1.15rem; font-weight: 800; color: var(--primary-green); }
    .category-badge { background: #dcfce7; color: var(--primary-dark); font-weight: 700; font-size: 0.8rem; padding: 3px 10px; border-radius: 6px; border: 1px solid var(--mint-border); margin-left: 8px; }
    .parts-badge { background: var(--accent-gold-light); color: var(--accent-gold); font-weight: 700; font-size: 0.8rem; padding: 3px 9px; border-radius: 6px; border: 1px solid #fde68a; margin-left: 6px; }
    .status-badge { font-size: 0.8rem; font-weight: 700; padding: 4px 10px; border-radius: 12px; text-transform: uppercase; }
    .badge-unvisited { background: var(--unvisited-light); color: var(--unvisited-gray); border: 1px solid #cbd5e1; }
    .badge-progress { background: #dbeafe; color: #1e40af; }
    .badge-complete { background: var(--correct-green-light); color: var(--correct-green); }
    .badge-skipped { background: var(--skipped-amber-light); color: var(--skipped-amber); }

    .problem-context { font-size: 1.15rem; font-weight: 500; margin-bottom: 1.25rem; background: #f0fdf4; border-left: 4px solid var(--accent-green); padding: 16px 20px; border-radius: var(--radius-sm); line-height: 2.2; border: 1px solid var(--mint-border-soft); border-left-width: 4px; }

    /* Progressive Multi-Step Cards */
    .steps-container { display: flex; flex-direction: column; gap: 1.25rem; }
    .step-card { border: 2px solid var(--mint-border-soft); border-radius: var(--radius-md); padding: 1.25rem 1.5rem; background: #ffffff; transition: all 0.25s ease-in-out; animation: slideDown 0.3s ease-out; }
    @keyframes slideDown {
      from { opacity: 0; transform: translateY(-8px); }
      to { opacity: 1; transform: translateY(0); }
    }
    .step-card.active { border-color: var(--accent-green); box-shadow: 0 4px 12px rgba(22, 163, 74, 0.15); }
    .step-card.completed { border-color: var(--correct-green); background: #fcfdfc; }
    
    .step-header-bar { display: flex; justify-content: space-between; align-items: center; margin-bottom: 0.75rem; }
    .step-title-text { font-weight: 700; font-size: 1rem; color: var(--primary-dark); }
    .step-status-indicator { font-size: 0.8rem; font-weight: 700; padding: 2px 8px; border-radius: 6px; }
    .step-card.completed .step-status-indicator { background: var(--correct-green-light); color: var(--correct-green); }
    .step-card.active .step-status-indicator { background: #dcfce7; color: var(--primary-dark); }

    .step-prompt { font-size: 1.05rem; font-weight: 500; margin-bottom: 1rem; color: var(--text-main); line-height: 2.4; }

    /* Step Inputs */
    .step-input {
      display: inline-block; width: 170px; padding: 6px 10px; font-size: 1.05rem; font-weight: 700; font-family: 'Segoe UI', monospace;
      text-align: center; color: var(--primary-green); background: #ffffff; border: 2px solid #86efac; border-radius: var(--radius-sm); outline: none; margin: 0 4px; vertical-align: middle;
    }
    .step-input:focus { border-color: var(--primary-green); box-shadow: 0 0 0 3px rgba(22, 163, 74, 0.2); }
    .step-input.input-correct { border-color: var(--correct-green) !important; background: var(--correct-green-light) !important; color: #065f46 !important; }
    .step-input.input-incorrect { border-color: var(--incorrect-red) !important; background: var(--incorrect-red-light) !important; color: #991b1b !important; }

    .step-controls { display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 10px; margin-top: 0.75rem; padding-top: 0.75rem; border-top: 1px dashed var(--mint-border-soft); }
    .step-feedback-msg { font-size: 0.88rem; font-weight: 600; }
    .step-feedback-msg.correct { color: #166534; }
    .step-feedback-msg.incorrect { color: #b91c1c; }

    /* Tools Panel */
    .tools-panel {
      background: #f0fdf4; border: 1.5px solid var(--mint-border); border-radius: var(--radius-md); padding: 1rem; margin-bottom: 1.25rem;
    }
    .tool-tab-header {
      display: flex; gap: 8px; border-bottom: 1.5px solid var(--mint-border-soft); padding-bottom: 8px; margin-bottom: 12px;
    }
    .tool-tab-btn {
      background: none; border: none; font-size: 0.85rem; font-weight: 700; color: var(--text-muted); cursor: pointer; padding: 4px 8px; border-radius: 4px;
    }
    .tool-tab-btn.active { color: var(--primary-green); background: #dcfce7; }
    .math-pad-grid { display: grid; grid-template-columns: repeat(7, 1fr); gap: 6px; }
    .math-pad-btn {
      background: #ffffff; border: 1px solid var(--mint-border); padding: 8px 4px; border-radius: var(--radius-sm); font-weight: 700; font-size: 0.95rem; cursor: pointer; text-align: center; color: var(--primary-dark);
    }
    .math-pad-btn:hover { background: var(--primary-green); color: #ffffff; }

    /* Calculator View */
    .calc-box { background: #ffffff; border: 1.5px solid var(--mint-border); border-radius: var(--radius-sm); padding: 10px; }
    .calc-screen { width: 100%; background: #064e3b; color: #86efac; font-family: monospace; font-size: 1.1rem; padding: 10px; border-radius: 4px; text-align: right; margin-bottom: 8px; overflow-x: auto; }
    .calc-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 6px; }
    .calc-btn { background: #f0fdf4; border: 1px solid var(--mint-border-soft); padding: 8px; border-radius: 4px; font-weight: 700; font-size: 0.9rem; cursor: pointer; text-align: center; color: var(--primary-dark); }
    .calc-btn:hover { background: #dcfce7; }
    .calc-btn.op { background: #bbf7d0; color: #064e3b; }
    .calc-btn.eq { background: var(--primary-green); color: #fff; }

    /* Palette Sidebar */
    .palette-card { background: var(--card-white); border-radius: var(--radius-lg); padding: 1.25rem; border: 2px solid var(--mint-border-soft); position: sticky; top: 90px; box-shadow: var(--shadow-md); }
    .palette-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 6px; margin: 1rem 0; max-height: 320px; overflow-y: auto; padding-right: 4px; }
    .palette-btn { aspect-ratio: 1; border-radius: var(--radius-sm); border: 1.5px solid var(--mint-border-soft); background: var(--unvisited-light); color: var(--text-muted); font-weight: 700; cursor: pointer; display: flex; align-items: center; justify-content: center; font-size: 0.85rem; }
    .palette-btn.active { border: 2.5px solid var(--primary-green) !important; background: #dcfce7 !important; color: var(--primary-green) !important; }
    .palette-btn.completed { background: var(--correct-green) !important; color: #ffffff !important; border-color: var(--correct-green) !important; }
    .palette-btn.progress { background: #93c5fd !important; border-color: #3b82f6 !important; color: #0f172a !important; }
    .palette-btn.skipped { background: var(--skipped-amber) !important; color: #ffffff !important; border-color: var(--skipped-amber) !important; }
    .palette-legend { border-top: 1.5px solid var(--mint-border-soft); padding-top: 0.75rem; display: grid; grid-template-columns: 1fr 1fr; gap: 6px; font-size: 0.75rem; }
    .legend-item { display: flex; align-items: center; gap: 4px; color: var(--text-muted); }
    .legend-color { width: 10px; height: 10px; border-radius: 2px; }

    .problem-action-bar { display: flex; justify-content: space-between; align-items: center; padding-top: 1.25rem; border-top: 1.5px solid var(--mint-border-soft); margin-top: 1.5rem; flex-wrap: wrap; gap: 10px; }
    .btn { padding: 9px 16px; border-radius: var(--radius-sm); font-weight: 700; font-size: 0.92rem; cursor: pointer; border: none; display: inline-flex; align-items: center; gap: 6px; transition: all 0.2s ease; }
    .btn-step-check { background: var(--primary-green); color: #ffffff; }
    .btn-step-back { background: #f0fdf4; color: var(--primary-dark); border: 1px solid var(--mint-border); }
    .btn-secondary { background: #e2e8f0; color: var(--text-main); }
    .btn-skip { background: #ffffff; color: var(--skipped-amber); border: 1.5px solid var(--skipped-amber); }

    .score-hero-card { background: linear-gradient(135deg, var(--primary-dark) 0%, var(--primary-green) 60%, var(--accent-green) 100%); color: #ffffff; border-radius: var(--radius-lg); padding: 2.5rem 2rem; text-align: center; margin-bottom: 2rem; box-shadow: var(--shadow-lg); }
    .score-circle { width: 115px; height: 115px; border-radius: 50%; background: rgba(255,255,255,0.15); border: 4px solid #86efac; display: flex; flex-direction: column; align-items: center; justify-content: center; margin: 0 auto 1rem auto; }
    .stats-row { display: grid; grid-template-columns: repeat(auto-fit, minmax(120px, 1fr)); gap: 1rem; max-width: 600px; margin: 1.5rem auto 0 auto; }
    .stat-pill { background: rgba(255,255,255,0.12); padding: 10px; border-radius: var(--radius-md); }
    .review-card { background: #ffffff; border: 2px solid var(--mint-border-soft); border-radius: var(--radius-md); padding: 1.5rem; margin-bottom: 1rem; box-shadow: var(--shadow-sm); line-height: 2.2; }

    .modal-overlay { display: none; position: fixed; inset: 0; background: rgba(6, 78, 59, 0.65); backdrop-filter: blur(3px); z-index: 999; align-items: center; justify-content: center; padding: 1rem; }
    .modal-overlay.active { display: flex; }
    .modal-box { background: #ffffff; max-width: 480px; width: 100%; border-radius: var(--radius-lg); padding: 2rem; text-align: center; border: 2px solid var(--mint-border); }
  </style>
</head>
<body>

  <!-- Header -->
  <header>
    <div class="header-container">
      <div class="brand-group">
        <div class="brand-logo">d/dx</div>
        <div class="brand-title">
          <h1>Brain and Mind Academy</h1>
          <p>Honors Precalc • 14.1 Worksheet #2: Derivatives and Physics</p>
        </div>
      </div>
      <div class="user-actions" id="headerActions" style="display: none;">
        <button class="btn-icon" id="revisitNotesBtn">📖 Theory Notes</button>
        <button class="btn-icon" id="jumpToSheetBtn" style="background: rgba(255, 255, 255, 0.28); color: #fff;">✍️ Practice Questions</button>
        <div class="user-badge"><span id="userEmailSpan">Student</span></div>
        <button class="btn-icon" id="soundToggleBtn"><span id="soundIcon">🔊</span></button>
        <button class="btn-icon" id="switchUserBtn">Logout</button>
      </div>
    </div>
  </header>

  <main>
    
    <!-- 1. Authentication Portal -->
    <section id="loginView" class="view-section active">
      <div class="card-center">
        <div class="login-icon">📐</div>
        <h2>14.1 Worksheet #2: Derivatives and Physics</h2>
        <p style="color: var(--text-muted); margin-bottom: 1.5rem;">Interactive step-by-step master learning sheet covering algebraic & trigonometric differentiation, tangent line equations, horizontal tangents, average vs. instantaneous rates of change, and vertical projectile kinematics.</p>
        <form id="loginForm">
          <div class="form-group">
            <label for="studentEmail">Student Name or Verification ID</label>
            <input type="text" id="studentEmail" class="form-control" placeholder="Enter your name or ID (e.g., Alex)" required autocomplete="name" />
          </div>
          <div style="display: flex; flex-direction: column; gap: 10px;">
            <button type="submit" class="btn-primary" id="startWithTheoryBtn">Review Core Theory & Formulas →</button>
            <button type="button" class="btn" id="startDirectQuizBtn" style="background: #f0fdf4; color: var(--primary-green); border: 2px solid var(--mint-border); font-weight: 700; padding: 12px; border-radius: var(--radius-sm); cursor: pointer;">
              ⚡ Jump Directly to Practice Questions (12 Questions)
            </button>
          </div>
        </form>
      </div>
    </section>

    <!-- 2. Theory & Formulas View -->
    <section id="notesView" class="view-section">
      <div class="notes-card">
        <div class="notes-header">
          <span style="display:inline-block; padding: 4px 10px; background: var(--accent-gold-light); color: var(--accent-gold); font-weight: 700; font-size: 0.75rem; border-radius: 12px; text-transform: uppercase; margin-bottom: 6px;">
            Honors Precalculus Reference
          </span>
          <h2>14.1 Derivatives and Physics — Core Review Notes</h2>
          <p style="color: var(--text-muted); font-size: 0.95rem;">Review the fundamental algebraic power rules, trigonometric derivative laws, rates of change definitions, and vertical projectile motion models.</p>
        </div>

        <div class="notes-body">
          <h3>1. Basic Differentiation Rules</h3>
          <p>Algebraic functions can often be rewritten as power terms before differentiating:</p>
          <div class="formula-callout">
            \[ \frac{d}{dx}[c] = 0, \qquad \frac{d}{dx}[x^n] = n x^{n-1}, \qquad \frac{d}{dx}[c \cdot f(x)] = c f'(x) \]
            \[ \frac{d}{dx}[\sin x] = \cos x, \qquad \frac{d}{dx}[\cos x] = -\sin x \]
          </div>

          <h3>2. Tangent Lines and Horizontal Tangents</h3>
          <ul>
            <li><strong>Slope of Tangent Line:</strong> The slope of the tangent line to \( y = f(x) \) at \( x = a \) is \( m = f'(a) \).</li>
            <li><strong>Point-Slope Form:</strong> \( y - f(a) = m(x - a) \).</li>
            <li><strong>Horizontal Tangent Condition:</strong> A curve has a horizontal tangent where its instantaneous slope is zero: \( f'(x) = 0 \).</li>
          </ul>

          <h3>3. Average vs. Instantaneous Rate of Change</h3>
          <ul>
            <li><strong>Average Rate of Change (AROC):</strong> Over an interval \( [a, b] \), the secant line slope is:
              \[ \text{AROC} = \frac{f(b) - f(a)}{b - a} \]
            </li>
            <li><strong>Instantaneous Rate of Change (IROC):</strong> At an exact instant \( t = a \), the rate is the derivative value:
              \[ \text{IROC} = f'(a) \]
            </li>
          </ul>

          <h3>4. Physics: Vertical Projectile Motion</h3>
          <p>For an object thrown vertically upward from height \( s_0 \) with initial velocity \( v_0 \) under gravity (\( g = 32\text{ ft/s}^2 \)):</p>
          <div class="formula-callout">
            \[ \text{Position Function: } s(t) = -16t^2 + v_0 t + s_0 \]
            \[ \text{Velocity Function: } v(t) = s'(t) = -32t + v_0 \]
            \[ \text{Ground Impact: } s(t) = 0 \implies \text{solve for } t \ge 0 \]
          </div>
        </div>

        <div class="notes-confirm-box">
          <div>
            <strong>Ready to practice the 12 worksheet problems step-by-step?</strong>
            <p style="font-size: 0.9rem; color: #166534; margin-top:2px;">Work through each algebraic, trigonometric, tangent, and kinematic step with interactive validation.</p>
          </div>
          <button class="btn btn-primary" id="confirmNotesReadBtn" style="width: auto; padding: 12px 24px;">
            Start 12-Question Interactive Worksheet →
          </button>
        </div>
      </div>
    </section>

    <!-- 3. Interactive Practice Workspace -->
    <section id="sheetView" class="view-section">
      <div class="learning-grid-layout">
        
        <!-- Left Side: Active Problem & Step Sequence -->
        <div class="problem-card">
          <div class="problem-header">
            <div>
              <span class="p-tag" id="pNumberDisplay">Question 1</span>
              <span class="category-badge" id="pCategoryBadge">Derivatives</span>
              <span class="parts-badge" id="pPartsBadge">2 Steps</span>
            </div>
            <div class="status-badge badge-unvisited" id="pStatusBadge">Unvisited</div>
          </div>
          
          <div class="problem-context" id="pContextDisplay"></div>

          <!-- On-Screen Mathematical Keypad & Scientific Calculator -->
          <div class="tools-panel">
            <div class="tool-tab-header">
              <button class="tool-tab-btn active" id="tabPadBtn" onclick="switchToolTab('pad')">⌨️ Mathematical Keypad</button>
              <button class="tool-tab-btn" id="tabCalcBtn" onclick="switchToolTab('calc')">🧮 Scientific Calculator</button>
            </div>
            
            <div id="mathPadView">
              <div class="math-pad-grid">
                <button class="math-pad-btn" onclick="insertSymbol('x')">x</button>
                <button class="math-pad-btn" onclick="insertSymbol('t')">t</button>
                <button class="math-pad-btn" onclick="insertSymbol('π')">π</button>
                <button class="math-pad-btn" onclick="insertSymbol('√')">√</button>
                <button class="math-pad-btn" onclick="insertSymbol('/')">/</button>
                <button class="math-pad-btn" onclick="insertSymbol('-')">-</button>
                <button class="math-pad-btn" onclick="insertSymbol('+')">+</button>
                <button class="math-pad-btn" onclick="insertSymbol('(')">(</button>
                <button class="math-pad-btn" onclick="insertSymbol(')')">)</button>
                <button class="math-pad-btn" onclick="insertSymbol('.')">.</button>
                <button class="math-pad-btn" onclick="insertSymbol('^2')">x²</button>
                <button class="math-pad-btn" onclick="insertSymbol('^3')">x³</button>
                <button class="math-pad-btn" onclick="insertSymbol('sin')">sin</button>
                <button class="math-pad-btn" onclick="insertSymbol('cos')">cos</button>
                <button class="math-pad-btn" onclick="insertSymbol('None')">None</button>
                <button class="math-pad-btn" style="background:#fef2f2; color:#dc2626;" onclick="clearActiveField()">Clear</button>
              </div>
            </div>

            <div id="calcView" style="display:none;">
              <div class="calc-box">
                <div class="calc-screen" id="calcScreen">0</div>
                <div class="calc-grid">
                  <button class="calc-btn" onclick="calcAppend('(')">(</button>
                  <button class="calc-btn" onclick="calcAppend(')')">)</button>
                  <button class="calc-btn" onclick="calcClear()">C</button>
                  <button class="calc-btn op" onclick="calcAppend('/')">/</button>
                  <button class="calc-btn" onclick="calcAppend('7')">7</button>
                  <button class="calc-btn" onclick="calcAppend('8')">8</button>
                  <button class="calc-btn" onclick="calcAppend('9')">9</button>
                  <button class="calc-btn op" onclick="calcAppend('*')">*</button>
                  <button class="calc-btn" onclick="calcAppend('4')">4</button>
                  <button class="calc-btn" onclick="calcAppend('5')">5</button>
                  <button class="calc-btn" onclick="calcAppend('6')">6</button>
                  <button class="calc-btn op" onclick="calcAppend('-')">-</button>
                  <button class="calc-btn" onclick="calcAppend('1')">1</button>
                  <button class="calc-btn" onclick="calcAppend('2')">2</button>
                  <button class="calc-btn" onclick="calcAppend('3')">3</button>
                  <button class="calc-btn op" onclick="calcAppend('+')">+</button>
                  <button class="calc-btn" onclick="calcAppend('0')">0</button>
                  <button class="calc-btn" onclick="calcAppend('.')">.</button>
                  <button class="calc-btn op" onclick="calcSqrt()">√</button>
                  <button class="calc-btn eq" onclick="calcEval()">=</button>
                </div>
                <div style="margin-top:6px; display:flex; justify-content:flex-end;">
                  <button class="btn btn-secondary" style="font-size:0.8rem; padding:4px 8px;" onclick="calcInsertToField()">↳ Insert Result into Input</button>
                </div>
              </div>
            </div>
          </div>

          <div class="steps-container" id="stepsListContainer"></div>

          <div class="problem-action-bar">
            <div style="display: flex; gap: 8px;">
              <button class="btn btn-secondary" id="prevProblemBtn">← Prev Question</button>
              <button class="btn btn-secondary" id="nextProblemBtn">Next Question →</button>
            </div>
            <button class="btn btn-skip" id="skipProblemBtn">Skip Question</button>
          </div>
        </div>

        <!-- Right Side: Sidebar Navigation Palette -->
        <aside class="palette-card">
          <div style="display:flex; justify-content:space-between; align-items:center;">
            <strong style="color:var(--primary-dark); font-size:1.02rem;">12-Question Index</strong>
            <span style="font-size:0.85rem; color:var(--primary-green); font-weight:700;" id="completionRateText">0/12 Solved</span>
          </div>
          <div class="palette-grid" id="paletteGridContainer"></div>
          <div class="palette-legend">
            <div class="legend-item"><div class="legend-color" style="background: var(--correct-green);"></div> Completed</div>
            <div class="legend-item"><div class="legend-color" style="background: #93c5fd;"></div> Working</div>
            <div class="legend-item"><div class="legend-color" style="background: var(--skipped-amber);"></div> Skipped</div>
            <div class="legend-item"><div class="legend-color" style="background: var(--unvisited-light); border:1px solid #cbd5e1;"></div> Empty</div>
          </div>
          <button class="btn btn-primary" id="finishAssessmentBtn" style="margin-top: 1.25rem; width: 100%;">Finish & View All Solutions</button>
        </aside>

      </div>
    </section>

    <!-- 4. Final Review & Score Dashboard -->
    <section id="reviewView" class="view-section">
      <div class="score-hero-card">
        <span class="topic-pill" style="background:rgba(255,255,255,0.2); color:#dcfce7; padding:4px 10px; border-radius:12px; font-weight:700;">Assessment Report</span>
        <h2 style="margin: 0.5rem 0; font-size: 1.7rem;">Derivatives & Physics Worksheet 2 Report</h2>
        <div class="score-circle">
          <div id="finalScoreVal" style="font-size:2rem; font-weight:800;">0</div>
          <div style="font-size:0.8rem; color:#bbf7d0;">out of 12</div>
        </div>
        <p id="performanceFeedbackDesc" style="color: #dcfce7; font-size:0.95rem; max-width:540px; margin:0 auto;"></p>
        <div class="stats-row">
          <div class="stat-pill"><div style="font-size:0.75rem; color:#dcfce7;">Accuracy</div><div id="accuracyStat" style="font-size:1.2rem; font-weight:700;">0%</div></div>
          <div class="stat-pill"><div style="font-size:0.75rem; color:#dcfce7;">Solved</div><div id="correctCountStat" style="font-size:1.2rem; font-weight:700; color:#86efac;">0</div></div>
          <div class="stat-pill"><div style="font-size:0.75rem; color:#dcfce7;">Skipped</div><div id="skippedCountStat" style="font-size:1.2rem; font-weight:700; color:#fde047;">0</div></div>
        </div>
        <div style="margin-top: 1.5rem; display:flex; justify-content:center; gap:10px;">
          <button class="btn" style="background: rgba(255,255,255,0.25); color:#fff;" id="retakeQuizBtn">↺ Retake Learning Sheet</button>
          <button class="btn" style="background:#fff; color:var(--primary-dark);" onclick="window.print()">🖨️ Print Solutions</button>
        </div>
      </div>
      <h3 style="color: var(--primary-dark); margin-bottom:1rem;">Complete Step-by-Step Mathematical Solutions</h3>
      <div id="reviewListContainer"></div>
    </section>

  </main>

  <!-- Submit Modal -->
  <div class="modal-overlay" id="confirmModal">
    <div class="modal-box">
      <h3 style="color:var(--primary-dark); margin-bottom:0.5rem;">Submit Worksheet?</h3>
      <p style="color:var(--text-muted); font-size:0.92rem; margin-bottom:1.25rem;">Are you ready to submit your answers and see the comprehensive step-by-step solutions report?</p>
      <div style="display:flex; justify-content:center; gap:10px;">
        <button class="btn btn-secondary" id="cancelModalBtn">Continue Solving</button>
        <button class="btn btn-primary" id="confirmSubmitModalBtn" style="width:auto;">Submit Now</button>
      </div>
    </div>
  </div>

  <script>
    /* ==========================================================================
       COMPLETE 12-PROBLEM DATASET (HONORS PRECALC 14.1 WS #2)
       ========================================================================== */
    const PROBLEMS_DATA = [
      // Q1: Constant Derivative
      {
        id: 1,
        title: "Question 1",
        category: "Derivatives",
        partsInfo: "1 Step Required",
        context: "Find the derivative of \\( y = 2\\pi \\) with respect to \\( x \\)[cite: 7].",
        steps: [
          {
            title: "Step 1 of 1: Constant Rule Differentiation",
            prompt: "Since \\( 2\\pi \\approx 6.283 \\) is a real constant containing no variable \\( x \\)[cite: 7], what is \\( \\frac{dy}{dx} \\)? <input class='step-input' style='width:60px;' data-ans='0'>",
            explanation: "The derivative of any constant value with respect to \\( x \\) is 0: \\( \\frac{d}{dx}[2\\pi] = 0 \\)[cite: 7]."
          }
        ]
      },
      // Q2: Rational Function Derivative
      {
        id: 2,
        title: "Question 2",
        category: "Derivatives",
        partsInfo: "2 Steps Required",
        context: "Find the derivative of \\( f(x) = \\frac{3x - 4}{x} \\)[cite: 7].",
        steps: [
          {
            title: "Step 1 of 2: Rewrite as Separate Powers",
            prompt: "Divide each term in the numerator by \\( x \\): \\( f(x) = 3 - 4x^k \\) where exponent \\( k = \\) <input class='step-input' style='width:50px;' data-ans='-1'>",
            explanation: "\\( f(x) = \\frac{3x}{x} - \\frac{4}{x} = 3 - 4x^{-1} \\)[cite: 7]."
          },
          {
            title: "Step 2 of 2: Apply the Power Rule",
            prompt: "\\( f'(x) = 0 - 4(-1x^{-2}) = \\frac{k}{x^2} \\) where numerator constant \\( k = \\) <input class='step-input' style='width:50px;' data-ans='4'>",
            explanation: "\\( f'(x) = 4x^{-2} = \\frac{4}{x^2} \\)[cite: 7]."
          }
        ]
      },
      // Q3: Polynomial Rational Derivative
      {
        id: 3,
        title: "Question 3",
        category: "Derivatives",
        partsInfo: "2 Steps Required",
        context: "Find the derivative of \\( g(x) = \\frac{3x^5 + 7x^2 - x}{x^3} \\)[cite: 7].",
        steps: [
          {
            title: "Step 1 of 2: Simplify Term-by-Term",
            prompt: "Divide each term by \\( x^3 \\): \\( g(x) = 3x^2 + 7x^{-1} - x^k \\) where exponent \\( k = \\) <input class='step-input' style='width:50px;' data-ans='-2'>",
            explanation: "\\( g(x) = 3x^{5-3} + 7x^{2-3} - x^{1-3} = 3x^2 + 7x^{-1} - x^{-2} \\)[cite: 7]."
          },
          {
            title: "Step 2 of 2: Differentiate Term-by-Term",
            prompt: "\\( g'(x) = 6x - 7x^{-2} + k x^{-3} \\) where coefficient \\( k = \\) <input class='step-input' style='width:50px;' data-ans='2'>",
            explanation: "\\( g'(x) = 6x - \\frac{7}{x^2} + \\frac{2}{x^3} \\)[cite: 7]."
          }
        ]
      },
      // Q4: Product / Expanded Power Derivative
      {
        id: 4,
        title: "Question 4",
        category: "Derivatives",
        partsInfo: "2 Steps Required",
        context: "Find the derivative of \\( s(x) = 6x(2x + 3)^2 \\)[cite: 7].",
        steps: [
          {
            title: "Step 1 of 2: Expand the Polynomial",
            prompt: "Expanding: \\( (2x + 3)^2 = 4x^2 + 12x + 9 \\). Multiplying by \\( 6x \\) yields \\( s(x) = 24x^3 + 72x^2 + k x \\) where \\( k = \\) <input class='step-input' style='width:60px;' data-ans='54'>",
            explanation: "\\( s(x) = 6x(4x^2 + 12x + 9) = 24x^3 + 72x^2 + 54x \\)[cite: 7]."
          },
          {
            title: "Step 2 of 2: Differentiate Using Power Rule",
            prompt: "Find \\( s'(x) = a x^2 + b x + 54 \\). Enter leading coefficient \\( a = \\) <input class='step-input' style='width:60px;' data-ans='72'>",
            explanation: "\\( s'(x) = 72x^2 + 144x + 54 = 18(4x^2 + 8x + 3) \\)[cite: 7]."
          }
        ]
      },
      // Q5: Trigonometric Derivative
      {
        id: 5,
        title: "Question 5",
        category: "Derivatives",
        partsInfo: "1 Step Required",
        context: "Find the derivative of \\( y = 2\\sin x - 3\\cos x \\)[cite: 7].",
        steps: [
          {
            title: "Step 1 of 1: Apply Trigonometric Rules",
            prompt: "Since \\( (\\sin x)' = \\cos x \\) and \\( (\\cos x)' = -\\sin x \\)[cite: 7], what is the coefficient of \\( \\sin x \\) in \\( y' = 2\\cos x + k\\sin x \\)? <input class='step-input' style='width:50px;' data-ans='3'>",
            explanation: "\\( y' = 2\\cos x - 3(-\\sin x) = 2\\cos x + 3\\sin x \\)[cite: 7]."
          }
        ]
      },
      // Q6: Rational Exponents
      {
        id: 6,
        title: "Question 6",
        category: "Derivatives",
        partsInfo: "2 Steps Required",
        context: "Find the derivative of \\( f(t) = t^{1/3} + 5t^{3/5} \\)[cite: 7].",
        steps: [
          {
            title: "Step 1 of 2: Power Rule on First Term",
            prompt: "Differentiate \\( t^{1/3} \\): \\( \\frac{1}{3}t^k \\) where exponent \\( k = \\) <input class='step-input' style='width:60px;' data-ans='-2/3'>",
            explanation: "\\( \\frac{d}{dt}[t^{1/3}] = \\frac{1}{3}t^{1/3 - 1} = \\frac{1}{3}t^{-2/3} \\)[cite: 7]."
          },
          {
            title: "Step 2 of 2: Differentiate Second Term",
            prompt: "For \\( 5t^{3/5} \\), \\( 5 \\cdot \\frac{3}{5}t^{3/5 - 1} = k t^{-2/5} \\) where coefficient \\( k = \\) <input class='step-input' style='width:50px;' data-ans='3'>",
            explanation: "\\( f'(t) = \\frac{1}{3}t^{-2/3} + 3t^{-2/5} = \\frac{1}{3t^{2/3}} + \\frac{3}{t^{2/5}} \\)[cite: 7]."
          }
        ]
      },
      // Q7: Tangent Line Equation
      {
        id: 7,
        title: "Question 7",
        category: "Tangent Lines",
        partsInfo: "3 Steps Required",
        context: "Find the equation of the tangent line to \\( f(x) = \\frac{1}{x^2} \\) at \\( x = -2 \\)[cite: 7].",
        steps: [
          {
            title: "Step 1 of 3: Find the Point of Tangency",
            prompt: "Evaluate \\( f(-2) = \\frac{1}{(-2)^2} = \\) <input class='step-input' style='width:60px;' data-ans='1/4' data-alt='0.25'>",
            explanation: "Point is \\( (-2, 1/4) \\) or \\( (-2, 0.25) \\)[cite: 7]."
          },
          {
            title: "Step 2 of 3: Calculate Derivative Slope m",
            prompt: "\\( f(x) = x^{-2} \\implies f'(x) = -2x^{-3} = -\\frac{2}{x^3} \\). Evaluate \\( f'(-2) = -\\frac{2}{(-2)^3} = \\) <input class='step-input' style='width:60px;' data-ans='1/4' data-alt='0.25'>",
            explanation: "Slope \\( m = -\\frac{2}{-8} = \\frac{1}{4} = 0.25 \\)[cite: 7]."
          },
          {
            title: "Step 3 of 3: Form the Tangent Line Equation",
            prompt: "In slope-intercept form \\( y = \\frac{1}{4}x + b \\), find the y-intercept \\( b \\): <input class='step-input' style='width:60px;' data-ans='3/4' data-alt='0.75'>",
            explanation: "\\( y - 1/4 = 1/4(x + 2) \\implies y = 1/4x + 3/4 \\)[cite: 7]."
          }
        ]
      },
      // Q8: Tangent Line at Origin
      {
        id: 8,
        title: "Question 8",
        category: "Tangent Lines",
        partsInfo: "2 Steps Required",
        context: "Find the equation of the tangent line to \\( f(x) = \\sqrt{3}x + \\sin x \\) at \\( (0, 0) \\)[cite: 7].",
        steps: [
          {
            title: "Step 1 of 2: Evaluate Slope at x = 0",
            prompt: "\\( f'(x) = \\sqrt{3} + \\cos x \\). What is \\( f'(0) = \\sqrt{3} + \\cos(0) = \\sqrt{3} + \\) <input class='step-input' style='width:50px;' data-ans='1'>",
            explanation: "\\( f'(0) = \\sqrt{3} + 1 \\approx 2.732 \\)[cite: 7]."
          },
          {
            title: "Step 2 of 2: Write Tangent Line Equation",
            prompt: "Since the line passes through the origin \\( (0,0) \\), \\( y = m x \\). Enter the slope factor \\( m \\) in radical form (e.g., √3+1): <input class='step-input' style='width:90px;' data-ans='√3+1' data-alt='sqrt(3)+1'>",
            explanation: "Equation is \\( y = (\\sqrt{3} + 1)x \\)[cite: 7]."
          }
        ]
      },
      // Q9: Horizontal Tangents
      {
        id: 9,
        title: "Question 9",
        category: "Tangent Lines",
        partsInfo: "2 Steps Required",
        context: "Where does \\( f(x) = 2x - \\cos x \\) have horizontal tangents on \\( 0 \\le x < 2\\pi \\)[cite: 7]?",
        steps: [
          {
            title: "Step 1 of 2: Set Derivative Equal to Zero",
            prompt: "Horizontal tangents require \\( f'(x) = 0 \\). Compute \\( f'(x) = 2 - (-\\sin x) = 2 + \\sin x \\). Setting \\( 2 + \\sin x = 0 \\implies \\sin x = \\) <input class='step-input' style='width:50px;' data-ans='-2'>",
            explanation: "\\( 2 + \\sin x = 0 \\implies \\sin x = -2 \\)[cite: 7]."
          },
          {
            title: "Step 2 of 2: Analyze Range of Sine Function",
            prompt: "Since the range of \\( \\sin x \\) is \\( [-1, 1] \\), \\( \\sin x = -2 \\) has no real solutions. How many horizontal tangents exist? <input class='step-input' style='width:60px;' data-ans='0' data-alt='None'>",
            explanation: "No horizontal tangents exist on \\( [0, 2\\pi) \\) (0 solutions)[cite: 7]."
          }
        ]
      },
      // Q10: AROC & IROC on Quadratic Function
      {
        id: 10,
        title: "Question 10",
        category: "Rates of Change",
        partsInfo: "3 Steps Required",
        context: "For \\( f(t) = 4t^2 + 1 \\) (where \\( t \\) is in seconds)[cite: 7]:<br>a. Find average rate of change on \\( [1, 4] \\)[cite: 7].<br>b. Find instantaneous rate of change at \\( t = 1 \\) and \\( t = 4 \\)[cite: 7].",
        steps: [
          {
            title: "Step 1 of 3: Compute Average Rate of Change on [1, 4]",
            prompt: "\\( f(1) = 5 \\) and \\( f(4) = 4(16) + 1 = 65 \\).<br>\\( \\text{AROC} = \\frac{65 - 5}{4 - 1} = \\frac{60}{3} = \\) <input class='step-input' style='width:60px;' data-ans='20'>",
            explanation: "\\( \\text{AROC} = \\frac{65 - 5}{3} = 20 \\)[cite: 7]."
          },
          {
            title: "Step 2 of 3: Instantaneous Rate of Change at t = 1",
            prompt: "\\( f'(t) = 8t \\). Evaluate at \\( t = 1 \\): \\( f'(1) = \\) <input class='step-input' style='width:50px;' data-ans='8'>",
            explanation: "\\( f'(1) = 8(1) = 8 \\)[cite: 7]."
          },
          {
            title: "Step 3 of 3: Instantaneous Rate of Change at t = 4",
            prompt: "Evaluate at \\( t = 4 \\): \\( f'(4) = 8(4) = \\) <input class='step-input' style='width:50px;' data-ans='32'>",
            explanation: "\\( f'(4) = 8(4) = 32 \\)[cite: 7]."
          }
        ]
      },
      // Q11: AROC & IROC on Trigonometric Function
      {
        id: 11,
        title: "Question 11",
        category: "Rates of Change",
        partsInfo: "2 Steps Required",
        context: "For \\( f(x) = 2\\sin x \\)[cite: 7]:<br>a. Find average rate of change on \\( [0, \\pi/6] \\)[cite: 7].<br>b. Find instantaneous rate of change at \\( x = \\pi/6 \\)[cite: 7].",
        steps: [
          {
            title: "Step 1 of 2: Average Rate of Change on [0, π/6]",
            prompt: "\\( f(0) = 0 \\) and \\( f(\\pi/6) = 2\\sin(\\pi/6) = 1 \\).<br>\\( \\text{AROC} = \\frac{1 - 0}{\\pi/6 - 0} = \\frac{k}{\\pi} \\) where numerator constant \\( k = \\) <input class='step-input' style='width:50px;' data-ans='6'>",
            explanation: "\\( \\text{AROC} = \\frac{1}{\\pi/6} = \\frac{6}{\\pi} \\approx 1.910 \\)[cite: 7]."
          },
          {
            title: "Step 2 of 2: Instantaneous Rate of Change at x = π/6",
            prompt: "\\( f'(x) = 2\\cos x \\). What is \\( f'(\\pi/6) = 2\\cos(\\pi/6) = 2\\left(\\frac{\\sqrt{3}}{2}\\right) = \\) <input class='step-input' style='width:70px;' data-ans='√3' data-alt='sqrt(3)'>",
            explanation: "\\( f'(\\pi/6) = \\sqrt{3} \\approx 1.732 \\)[cite: 7]."
          }
        ]
      },
      // Q12: Physics Projectile Motion
      {
        id: 12,
        title: "Question 12",
        category: "Physics Kinematics",
        partsInfo: "6 Steps Required",
        context: "A ball is thrown upward with an initial velocity of \\( 30\\text{ ft/s} \\) from the top of a building \\( 120\\text{ ft} \\) tall[cite: 7].",
        steps: [
          {
            title: "Step 1 of 6: Position Function s(t)",
            prompt: "Using \\( s(t) = -16t^2 + v_0 t + s_0 \\)[cite: 7], find constant term \\( s_0 = \\) <input class='step-input' style='width:60px;' data-ans='120'> ft[cite: 7]",
            explanation: "Position function is \\( s(t) = -16t^2 + 30t + 120 \\)[cite: 7]."
          },
          {
            title: "Step 2 of 6: Velocity Function v(t)",
            prompt: "Differentiate \\( s(t) \\): \\( v(t) = s'(t) = a t + 30 \\). Enter coefficient \\( a = \\) <input class='step-input' style='width:60px;' data-ans='-32'>",
            explanation: "\\( v(t) = -32t + 30 \\)[cite: 7]."
          },
          {
            title: "Step 3 of 6: Average Velocity on [1, 3] Seconds",
            prompt: "Since \\( s(1) = 134\\text{ ft} \\) and \\( s(3) = 66\\text{ ft} \\)[cite: 7]:<br>\\( v_{\\text{avg}} = \\frac{66 - 134}{3 - 1} = \\frac{-68}{2} = \\) <input class='step-input' style='width:60px;' data-ans='-34'> ft/s[cite: 7]",
            explanation: "Average velocity is \\( -34\\text{ ft/s} \\)[cite: 7]."
          },
          {
            title: "Step 4 of 6: Instantaneous Velocity at t = 1s and t = 3s",
            prompt: "• \\( v(1) = -32(1) + 30 = \\) <input class='step-input' style='width:50px;' data-ans='-2'> ft/s[cite: 7].<br>• \\( v(3) = -32(3) + 30 = -66\\text{ ft/s} \\)[cite: 7].",
            explanation: "\\( v(1) = -2\\text{ ft/s} \\) and \\( v(3) = -66\\text{ ft/s} \\)[cite: 7]."
          },
          {
            title: "Step 5 of 6: Time Ball Hits the Ground",
            prompt: "Set \\( s(t) = -16t^2 + 30t + 120 = 0 \\implies 8t^2 - 15t - 60 = 0 \\)[cite: 7].<br>Using quadratic formula for \\( t > 0 \\): \\( t = \\frac{15 + \\sqrt{2145}}{16} \\approx \\) <input class='step-input' style='width:60px;' data-ans='3.83' data-alt='3.832'> s[cite: 7]",
            explanation: "\\( t = \\frac{15 + \\sqrt{2145}}{16} \\approx 3.832\\text{ s} \\)[cite: 7]."
          },
          {
            title: "Step 6 of 6: Impact Velocity",
            prompt: "Evaluate \\( v(3.832) = -32(3.832) + 30 \\approx \\) <input class='step-input' style='width:70px;' data-ans='-92.6' data-alt='-92.63'> ft/s[cite: 7]",
            explanation: "Impact velocity is \\( -2\\sqrt{2145} \\approx -92.63\\text{ ft/s} \\) (downward)[cite: 7]."
          }
        ]
      }
    ];

    /* ==========================================================================
       SAFE STATE & MEMORY STORAGE
       ========================================================================== */
    const STORAGE_KEY = "bma_precalc_ws14_1_review";
    window._memStore = window._memStore || {};

    const SafeStorage = {
      isAvailable: () => {
        try {
          const test = '__storage_test__';
          window.localStorage.setItem(test, test);
          window.localStorage.removeItem(test);
          return true;
        } catch (e) {
          return false;
        }
      },
      getItem: (key) => {
        try {
          if (SafeStorage.isAvailable()) {
            return window.localStorage.getItem(key);
          }
        } catch (e) {}
        return window._memStore[key] || null;
      },
      setItem: (key, val) => {
        try {
          if (SafeStorage.isAvailable()) {
            window.localStorage.setItem(key, val);
            return;
          }
        } catch (e) {}
        window._memStore[key] = String(val);
      }
    };

    let activeInputElement = null;

    let state = {
      currentEmail: null,
      notesRead: false,
      currentProblemIdx: 0,
      isCompleted: false,
      problems: {}
    };

    function saveState() {
      if (!state.currentEmail) return;
      SafeStorage.setItem(`${STORAGE_KEY}_${state.currentEmail.trim().toLowerCase()}`, JSON.stringify(state));
      SafeStorage.setItem(`${STORAGE_KEY}_last_active`, state.currentEmail);
    }

    function loadState(email) {
      const data = SafeStorage.getItem(`${STORAGE_KEY}_${email.trim().toLowerCase()}`);
      if (data) {
        try { 
          state = { ...state, ...JSON.parse(data), currentEmail: email }; 
        } catch (e) {
          state = { currentEmail: email, notesRead: false, currentProblemIdx: 0, isCompleted: false, problems: {} };
        }
      } else {
        state = { currentEmail: email, notesRead: false, currentProblemIdx: 0, isCompleted: false, problems: {} };
      }
    }

    function getProblemState(idx) {
      if (!state.problems[idx]) {
        state.problems[idx] = { completedSteps: [], inputs: {}, isSolved: false, isSkipped: false };
      }
      if (!Array.isArray(state.problems[idx].completedSteps)) {
        state.problems[idx].completedSteps = [];
      }
      if (!state.problems[idx].inputs || typeof state.problems[idx].inputs !== 'object') {
        state.problems[idx].inputs = {};
      }
      return state.problems[idx];
    }

    function cleanString(s) {
      return (s || "").toString().trim().toLowerCase()
        .replace(/\s+/g, '')
        .replace(/−/g, '-')
        .replace(/[ft/sec]/g, '');
    }

    function testInputMatching(userStr, targetStr, altStr) {
      const u = cleanString(userStr);
      const t = cleanString(targetStr);
      const a = cleanString(altStr);
      if (!u) return false;
      if (u === t || (altStr && u === a)) return true;
      if (u.includes('/') || t.includes('/')) {
        const d = (f) => f.split('/').length === 2 ? parseFloat(f.split('/')[0]) / parseFloat(f.split('/')[1]) : parseFloat(f);
        return Math.abs(d(u) - d(t)) < 0.05;
      }
      const isNumU = !isNaN(Number(u));
      const isNumT = !isNaN(Number(t));
      if (isNumU && isNumT) {
        return Math.abs(Number(u) - Number(t)) < 0.1;
      }
      return false;
    }

    function triggerMathTypeset() {
      if (window.MathJax && window.MathJax.typesetPromise) {
        window.MathJax.typesetPromise().catch((err) => console.warn('MathJax error:', err));
      }
    }

    /* ==========================================================================
       KEYPAD & CALCULATOR HELPERS
       ========================================================================== */
    window.trackActiveField = function(element) { activeInputElement = element; };
    window.insertSymbol = function(sym) {
      if (!activeInputElement) return;
      const start = activeInputElement.selectionStart || 0;
      const end = activeInputElement.selectionEnd || 0;
      const val = activeInputElement.value;
      activeInputElement.value = val.substring(0, start) + sym + val.substring(end);
      activeInputElement.focus();
      activeInputElement.dispatchEvent(new Event('input', { bubbles: true }));
    };
    window.clearActiveField = function() {
      if (!activeInputElement) return;
      activeInputElement.value = '';
      activeInputElement.dispatchEvent(new Event('input', { bubbles: true }));
      activeInputElement.focus();
    };

    window.switchToolTab = function(tab) {
      document.getElementById('tabPadBtn').classList.toggle('active', tab === 'pad');
      document.getElementById('tabCalcBtn').classList.toggle('active', tab === 'calc');
      document.getElementById('mathPadView').style.display = tab === 'pad' ? 'grid' : 'none';
      document.getElementById('calcView').style.display = tab === 'calc' ? 'block' : 'none';
    };

    let calcExpression = "";
    window.calcAppend = function(val) {
      calcExpression += val;
      document.getElementById('calcScreen').textContent = calcExpression || "0";
    };
    window.calcClear = function() {
      calcExpression = "";
      document.getElementById('calcScreen').textContent = "0";
    };
    window.calcSqrt = function() {
      try {
        const res = Math.sqrt(eval(calcExpression || "0"));
        calcExpression = String(res);
        document.getElementById('calcScreen').textContent = calcExpression;
      } catch(e) { document.getElementById('calcScreen').textContent = "Error"; }
    };
    window.calcEval = function() {
      try {
        const res = eval(calcExpression || "0");
        calcExpression = String(res);
        document.getElementById('calcScreen').textContent = calcExpression;
      } catch(e) { document.getElementById('calcScreen').textContent = "Error"; }
    };
    window.calcInsertToField = function() {
      if (!activeInputElement || !calcExpression) return;
      insertSymbol(calcExpression);
    };

    /* ==========================================================================
       ROUTER & NAVIGATION CONTROLS
       ========================================================================== */
    const loginForm = document.getElementById('loginForm');
    const studentEmailInput = document.getElementById('studentEmail');

    function handleLogin(email, targetView = 'notes') {
      const cleanName = email.trim() || 'Student';
      loadState(cleanName);
      state.currentEmail = cleanName;
      saveState();
      if (targetView === 'sheet') {
        renderProblem(state.currentProblemIdx || 0);
        showView('sheet');
      } else {
        showView('notes');
        triggerMathTypeset();
      }
    }

    loginForm.addEventListener('submit', (e) => {
      e.preventDefault();
      handleLogin(studentEmailInput.value, 'notes');
    });

    document.getElementById('startDirectQuizBtn').addEventListener('click', () => {
      handleLogin(studentEmailInput.value, 'sheet');
    });

    document.getElementById('confirmNotesReadBtn').addEventListener('click', () => {
      state.notesRead = true;
      saveState();
      renderProblem(state.currentProblemIdx || 0);
      showView('sheet');
    });

    document.getElementById('revisitNotesBtn').addEventListener('click', () => {
      showView('notes');
      triggerMathTypeset();
    });

    document.getElementById('jumpToSheetBtn').addEventListener('click', () => {
      renderProblem(state.currentProblemIdx || 0);
      showView('sheet');
    });

    document.getElementById('switchUserBtn').addEventListener('click', () => {
      saveState();
      state.currentEmail = null;
      showView('login');
    });

    document.getElementById('soundToggleBtn').addEventListener('click', () => {
      soundEnabled = !soundEnabled;
      document.getElementById('soundIcon').textContent = soundEnabled ? '🔊' : '🔇';
    });

    function showView(v) {
      document.querySelectorAll('.view-section').forEach(el => el.classList.remove('active'));
      const target = document.getElementById(`${v}View`);
      if (target) target.classList.add('active');
      window.scrollTo({ top: 0, behavior: 'smooth' });
      document.getElementById('headerActions').style.display = state.currentEmail ? 'flex' : 'none';
      if (state.currentEmail) document.getElementById('userEmailSpan').textContent = state.currentEmail;
    }

    /* ==========================================================================
       PROGRESSIVE STEP-BY-STEP RENDERER
       ========================================================================== */
    function renderProblem(idx) {
      if (idx < 0 || idx >= PROBLEMS_DATA.length) return;
      state.currentProblemIdx = idx;
      const prob = PROBLEMS_DATA[idx];
      const pState = getProblemState(idx);

      document.getElementById('pNumberDisplay').textContent = `${prob.title}`;
      document.getElementById('pCategoryBadge').textContent = prob.category || 'Calculus';
      document.getElementById('pPartsBadge').textContent = prob.partsInfo;
      document.getElementById('pContextDisplay').innerHTML = prob.context;

      const badge = document.getElementById('pStatusBadge');
      if (pState.isSolved) { badge.className = 'status-badge badge-complete'; badge.textContent = 'Completed'; }
      else if (pState.isSkipped) { badge.className = 'status-badge badge-skipped'; badge.textContent = 'Skipped'; }
      else if (pState.completedSteps.length > 0) { badge.className = 'status-badge badge-progress'; badge.textContent = 'In Progress'; }
      else { badge.className = 'status-badge badge-unvisited'; badge.textContent = 'Unvisited'; }

      const container = document.getElementById('stepsListContainer');
      container.innerHTML = '';

      const completedCount = pState.completedSteps.length;
      const maxStepToRender = pState.isSolved ? prob.steps.length - 1 : Math.min(completedCount, prob.steps.length - 1);

      for (let sIdx = 0; sIdx <= maxStepToRender; sIdx++) {
        const step = prob.steps[sIdx];
        const isDone = pState.completedSteps.includes(sIdx);
        const isActive = !isDone;

        const card = document.createElement('div');
        card.id = `step-card-${idx}-${sIdx}`;
        card.className = `step-card ${isDone ? 'completed' : 'active'}`;

        card.innerHTML = `
          <div class="step-header-bar">
            <div class="step-title-text">${step.title}</div>
            <span class="step-status-indicator">${isDone ? '✓ Completed' : 'Active Step'}</span>
          </div>
          <div class="step-prompt">${step.prompt}</div>
          <div class="step-controls">
            <div>
              ${sIdx > 0 ? `<button class="btn btn-step-back" onclick="focusStepCard(${idx}, ${sIdx-1})">← Back to Step ${sIdx}</button>` : ''}
            </div>
            <div style="display:flex; align-items:center; gap:8px;">
              <span class="step-feedback-msg" id="step-msg-${idx}-${sIdx}"></span>
              ${!isDone ? `
                <button class="btn btn-step-check" id="btn-verify-${idx}-${sIdx}" onclick="verifyStepAnswers(${idx}, ${sIdx})">
                  ${sIdx === prob.steps.length - 1 ? 'Verify & Finish Question ✓' : 'Verify & Reveal Next Step →'}
                </button>
              ` : '<span style="color:var(--correct-green); font-weight:700;">✓ Step Verified</span>'}
            </div>
          </div>
        `;
        container.appendChild(card);

        card.querySelectorAll('.step-input').forEach((inp, iIdx) => {
          const inputKey = `p${idx}_s${sIdx}_i${iIdx}`;
          inp.setAttribute('onfocus', 'trackActiveField(this)');
          if (pState.inputs[inputKey] !== undefined) inp.value = pState.inputs[inputKey];
          if (isDone) {
            inp.disabled = true;
            inp.classList.add('input-correct');
          } else {
            inp.disabled = false;
            inp.addEventListener('input', (e) => {
              pState.inputs[inputKey] = e.target.value;
              saveState();
            });
            inp.addEventListener('keypress', (e) => {
              if (e.key === 'Enter') verifyStepAnswers(idx, sIdx);
            });
          }
        });
      }

      document.getElementById('prevProblemBtn').disabled = idx === 0;
      document.getElementById('nextProblemBtn').disabled = idx === PROBLEMS_DATA.length - 1;
      renderPaletteGrid();
      saveState();
      triggerMathTypeset();
    }

    window.verifyStepAnswers = function(pIdx, sIdx) {
      const prob = PROBLEMS_DATA[pIdx];
      const pState = getProblemState(pIdx);
      const card = document.getElementById(`step-card-${pIdx}-${sIdx}`);
      const inputs = card.querySelectorAll('.step-input');
      let ok = true;

      inputs.forEach((inp, iIdx) => {
        const ans = inp.getAttribute('data-ans') || '';
        const alt = inp.getAttribute('data-alt') || '';
        const inputKey = `p${pIdx}_s${sIdx}_i${iIdx}`;
        pState.inputs[inputKey] = inp.value;
        if (testInputMatching(inp.value, ans, alt)) {
          inp.classList.remove('input-incorrect');
          inp.classList.add('input-correct');
        } else {
          inp.classList.remove('input-correct');
          inp.classList.add('input-incorrect');
          ok = false;
        }
      });

      const msg = document.getElementById(`step-msg-${pIdx}-${sIdx}`);
      if (ok) {
        playSound('correct');
        if (!pState.completedSteps.includes(sIdx)) pState.completedSteps.push(sIdx);
        pState.isSkipped = false;
        msg.className = "step-feedback-msg correct";
        msg.textContent = "✓ Correct Step Verification!";

        if (pState.completedSteps.length === prob.steps.length) {
          pState.isSolved = true;
          saveState();
          setTimeout(() => {
            if (pIdx === PROBLEMS_DATA.length - 1) playSound('fanfare');
            renderProblem(pIdx);
          }, 350);
        } else {
          saveState();
          setTimeout(() => {
            renderProblem(pIdx);
            focusStepCard(pIdx, sIdx + 1);
          }, 300);
        }
      } else {
        playSound('incorrect');
        msg.className = "step-feedback-msg incorrect";
        msg.textContent = "✗ Calculation mismatch in highlighted box.";
      }
    };

    window.focusStepCard = function(pIdx, sIdx) {
      const target = document.getElementById(`step-card-${pIdx}-${sIdx}`);
      if (target) {
        target.scrollIntoView({ behavior: 'smooth', block: 'center' });
        const field = target.querySelector('.step-input');
        if (field && !field.disabled) field.focus();
      }
    };

    document.getElementById('skipProblemBtn').addEventListener('click', () => {
      playSound('click');
      const pState = getProblemState(state.currentProblemIdx);
      pState.isSkipped = true;
      saveState();
      if (state.currentProblemIdx < PROBLEMS_DATA.length - 1) renderProblem(state.currentProblemIdx + 1);
      else renderProblem(state.currentProblemIdx);
    });

    document.getElementById('prevProblemBtn').addEventListener('click', () => {
      if (state.currentProblemIdx > 0) renderProblem(state.currentProblemIdx - 1);
    });

    document.getElementById('nextProblemBtn').addEventListener('click', () => {
      if (state.currentProblemIdx < PROBLEMS_DATA.length - 1) renderProblem(state.currentProblemIdx + 1);
    });

    function renderPaletteGrid() {
      const grid = document.getElementById('paletteGridContainer');
      grid.innerHTML = '';
      let solvedCount = 0;

      PROBLEMS_DATA.forEach((p, idx) => {
        const btn = document.createElement('button');
        btn.className = 'palette-btn';
        btn.textContent = idx + 1;
        const ps = state.problems[idx];
        if (ps) {
          if (ps.isSolved) { btn.classList.add('completed'); solvedCount++; }
          else if (ps.isSkipped) btn.classList.add('skipped');
          else if (Array.isArray(ps.completedSteps) && ps.completedSteps.length > 0) btn.classList.add('progress');
        }
        if (idx === state.currentProblemIdx) btn.classList.add('active');
        btn.addEventListener('click', () => renderProblem(idx));
        grid.appendChild(btn);
      });
      document.getElementById('completionRateText').textContent = `${solvedCount}/${PROBLEMS_DATA.length} Solved`;
    }

    const confirmModal = document.getElementById('confirmModal');
    document.getElementById('finishAssessmentBtn').addEventListener('click', () => confirmModal.classList.add('active'));
    document.getElementById('cancelModalBtn').addEventListener('click', () => confirmModal.classList.remove('active'));
    document.getElementById('confirmSubmitModalBtn').addEventListener('click', () => {
      confirmModal.classList.remove('active');
      state.isCompleted = true;
      saveState();
      playSound('fanfare');
      renderReviewScreen();
      showView('review');
    });

    function renderReviewScreen() {
      let solved = 0, skipped = 0;
      PROBLEMS_DATA.forEach((p, idx) => {
        const ps = state.problems[idx];
        if (ps && ps.isSolved) solved++;
        else if (ps && ps.isSkipped) skipped++;
      });
      const total = PROBLEMS_DATA.length;
      document.getElementById('finalScoreVal').textContent = solved;
      document.getElementById('accuracyStat').textContent = `${Math.round((solved/total)*100)}%`;
      document.getElementById('correctCountStat').textContent = solved;
      document.getElementById('skippedCountStat').textContent = skipped;

      const desc = document.getElementById('performanceFeedbackDesc');
      desc.textContent = solved === total 
        ? "🌟 Outstanding mastery! You solved all 12 questions of Derivatives & Physics 14.1 Worksheet #2 flawlessly." 
        : "Review the complete step rationales below to polish your differentiation and projectile motion skills.";

      const reviewContainer = document.getElementById('reviewListContainer');
      reviewContainer.innerHTML = '';

      PROBLEMS_DATA.forEach((prob, idx) => {
        const card = document.createElement('div');
        card.className = 'review-card';
        let stepsHTML = prob.steps.map(st => `
          <div style="margin-top:10px; padding:12px; background:#f0fdf4; border-left:3px solid #16a34a; border-radius:4px; border:1px solid #bbf7d0; border-left-width:3px;">
            <strong style="color:var(--primary-green); font-size:0.95rem;">${st.title}</strong>
            <p style="margin-top:4px; font-size:0.95rem; color:#064e3b;">${st.explanation}</p>
          </div>
        `).join('');
        card.innerHTML = `
          <div style="display:flex; justify-content:space-between; align-items:center; margin-bottom:0.5rem;">
            <strong style="color:var(--primary-dark); font-size:1.1rem;">${prob.title} (${prob.partsInfo})</strong>
            <span class="status-badge ${state.problems[idx]?.isSolved ? 'badge-complete' : 'badge-skipped'}">
              ${state.problems[idx]?.isSolved ? 'Solved' : 'Skipped/Incomplete'}
            </span>
          </div>
          <div style="font-size:1.05rem; margin-bottom:0.5rem;">${prob.context}</div>
          ${stepsHTML}
        `;
        reviewContainer.appendChild(card);
      });
      triggerMathTypeset();
    }

    document.getElementById('retakeQuizBtn').addEventListener('click', () => {
      if (confirm("Reset current worksheet parameters and restart?")) {
        state.problems = {};
        state.currentProblemIdx = 0;
        state.isCompleted = false;
        saveState();
        renderProblem(0);
        showView('sheet');
      }
    });

    window.addEventListener('DOMContentLoaded', () => {
      const last = SafeStorage.getItem(`${STORAGE_KEY}_last_active`);
      if (last && studentEmailInput) studentEmailInput.value = last;
      triggerMathTypeset();
    });
  </script>
</body>
</html>
