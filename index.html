<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Resident Detective — Who Done It?</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;1,400;1,700&family=JetBrains+Mono:wght@400;600;700&family=Crimson+Pro:wght@400;600&display=swap" rel="stylesheet"/>
<style>
  :root {
    --navy: #001a2e;
    --navy2: #002847;
    --navy3: #003860;
    --blue: #0081C6;
    --green: #49A942;
    --gold: #c9a84c;
    --gold2: #f0d080;
    --red: #c0392b;
    --cream: #f5f0e8;
    --text: #e8e0d0;
    --muted: #8a9bb0;
    --card: rgba(0,40,71,0.7);
    --border: rgba(201,168,76,0.25);
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }
  html, body { height: 100%; }

  body {
    font-family: 'Crimson Pro', Georgia, serif;
    background: var(--navy);
    color: var(--text);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* ── BACKGROUND ATMOSPHERE ── */
  .bg-layer {
    position: fixed; inset: 0; z-index: 0; pointer-events: none;
    background:
      radial-gradient(ellipse at 20% 10%, rgba(0,129,198,0.12) 0%, transparent 50%),
      radial-gradient(ellipse at 80% 90%, rgba(73,169,66,0.08) 0%, transparent 50%),
      radial-gradient(ellipse at 50% 50%, rgba(201,168,76,0.05) 0%, transparent 70%);
  }
  .bg-grid {
    position: fixed; inset: 0; z-index: 0; pointer-events: none;
    background-image:
      linear-gradient(rgba(201,168,76,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(201,168,76,0.04) 1px, transparent 1px);
    background-size: 40px 40px;
  }
  .corner-ornament {
    position: fixed; z-index: 0; pointer-events: none;
    width: 200px; height: 200px;
    opacity: 0.06;
  }
  .corner-ornament.tl { top: -20px; left: -20px; }
  .corner-ornament.br { bottom: -20px; right: -20px; transform: rotate(180deg); }

  /* ── LAYOUT ── */
  .app { position: relative; z-index: 1; min-height: 100vh; }

  /* ── VIEW TOGGLE (hidden nav for host) ── */
  .view-toggle {
    position: fixed; top: 12px; right: 12px; z-index: 100;
    display: flex; gap: 6px;
  }
  .view-btn {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px; font-weight: 700;
    letter-spacing: 0.1em;
    padding: 6px 12px;
    border-radius: 4px;
    border: 1px solid var(--border);
    background: rgba(0,24,48,0.8);
    color: var(--muted);
    cursor: pointer;
    transition: all 0.2s;
    backdrop-filter: blur(8px);
  }
  .view-btn.active {
    background: var(--gold);
    color: var(--navy);
    border-color: var(--gold);
  }

  /* ══════════════════════════════════
     VOTER PAGE
  ══════════════════════════════════ */
  #voter-view { display: block; }
  #results-view { display: none; }

  .voter-wrap {
    max-width: 480px;
    margin: 0 auto;
    padding: 32px 20px 48px;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .eyebrow {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    font-weight: 700;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 8px;
    text-align: center;
  }

  .voter-title {
    font-family: 'Playfair Display', serif;
    font-style: italic;
    font-size: clamp(2rem, 8vw, 3rem);
    text-align: center;
    color: var(--cream);
    line-height: 1.1;
    margin-bottom: 4px;
  }

  .voter-subtitle {
    font-family: 'Playfair Display', serif;
    font-size: clamp(1rem, 4vw, 1.3rem);
    text-align: center;
    color: var(--gold2);
    margin-bottom: 28px;
    font-style: italic;
  }

  .divider-ornament {
    display: flex; align-items: center; gap: 12px;
    width: 100%; margin-bottom: 28px;
  }
  .divider-ornament::before,
  .divider-ornament::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--gold), transparent);
  }
  .divider-ornament span {
    color: var(--gold);
    font-size: 14px;
  }

  /* Suspect cards */
  .suspects-grid {
    display: flex;
    flex-direction: column;
    gap: 12px;
    width: 100%;
    margin-bottom: 28px;
  }

  .suspect-card {
    position: relative;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 16px 20px;
    cursor: pointer;
    transition: all 0.25s cubic-bezier(0.4, 0, 0.2, 1);
    display: flex;
    align-items: center;
    gap: 16px;
    backdrop-filter: blur(8px);
    overflow: hidden;
  }
  .suspect-card::before {
    content: '';
    position: absolute; inset: 0;
    background: linear-gradient(135deg, rgba(201,168,76,0.08), transparent);
    opacity: 0;
    transition: opacity 0.25s;
  }
  .suspect-card:hover { border-color: rgba(201,168,76,0.5); transform: translateX(4px); }
  .suspect-card:hover::before { opacity: 1; }
  .suspect-card.selected {
    border-color: var(--gold);
    background: rgba(201,168,76,0.15);
    transform: translateX(6px);
  }
  .suspect-card.selected::before { opacity: 1; }

  .suspect-icon {
    width: 48px; height: 48px;
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-size: 22px;
    flex-shrink: 0;
    border: 2px solid var(--border);
    transition: border-color 0.25s;
  }
  .suspect-card.selected .suspect-icon { border-color: var(--gold); }

  .suspect-info { flex: 1; }
  .suspect-name {
    font-family: 'Playfair Display', serif;
    font-size: 1.15rem;
    font-weight: 700;
    color: var(--cream);
    display: block;
    margin-bottom: 2px;
  }
  .suspect-alias {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--muted);
    display: block;
  }

  .suspect-check {
    width: 24px; height: 24px;
    border-radius: 50%;
    border: 2px solid var(--border);
    flex-shrink: 0;
    display: flex; align-items: center; justify-content: center;
    transition: all 0.25s;
    color: transparent;
    font-size: 13px;
  }
  .suspect-card.selected .suspect-check {
    background: var(--gold);
    border-color: var(--gold);
    color: var(--navy);
  }

  /* Color accents per suspect */
  .scarlett .suspect-icon { background: rgba(192,57,43,0.2); }
  .mustard .suspect-icon { background: rgba(201,168,76,0.2); }
  .white .suspect-icon { background: rgba(200,200,200,0.15); }
  .green .suspect-icon { background: rgba(73,169,66,0.2); }
  .peacock .suspect-icon { background: rgba(0,129,198,0.2); }

  /* Submit button */
  .submit-btn {
    width: 100%;
    padding: 18px;
    border-radius: 10px;
    border: none;
    background: linear-gradient(135deg, var(--gold), #a07c2a);
    color: var(--navy);
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    font-weight: 700;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    cursor: pointer;
    transition: all 0.2s;
    box-shadow: 0 4px 20px rgba(201,168,76,0.3);
  }
  .submit-btn:hover:not(:disabled) {
    transform: translateY(-2px);
    box-shadow: 0 8px 28px rgba(201,168,76,0.4);
  }
  .submit-btn:disabled {
    opacity: 0.4;
    cursor: not-allowed;
    transform: none;
  }

  /* Voted state */
  .voted-state {
    display: none;
    flex-direction: column;
    align-items: center;
    gap: 16px;
    padding: 32px 20px;
    text-align: center;
  }
  .voted-icon {
    width: 80px; height: 80px;
    border-radius: 50%;
    background: linear-gradient(135deg, rgba(201,168,76,0.2), rgba(73,169,66,0.2));
    border: 2px solid var(--gold);
    display: flex; align-items: center; justify-content: center;
    font-size: 36px;
    animation: popIn 0.5s cubic-bezier(0.34, 1.56, 0.64, 1);
  }
  @keyframes popIn {
    from { transform: scale(0); opacity: 0; }
    to { transform: scale(1); opacity: 1; }
  }
  .voted-title {
    font-family: 'Playfair Display', serif;
    font-style: italic;
    font-size: 1.8rem;
    color: var(--cream);
  }
  .voted-sub {
    color: var(--muted);
    font-size: 1rem;
    line-height: 1.6;
  }

  /* ══════════════════════════════════
     RESULTS PAGE (Big Screen)
  ══════════════════════════════════ */
  .results-wrap {
    max-width: 900px;
    margin: 0 auto;
    padding: 48px 40px;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
  }

  .results-header {
    text-align: center;
    margin-bottom: 48px;
  }

  .results-title {
    font-family: 'Playfair Display', serif;
    font-style: italic;
    font-size: clamp(2.5rem, 6vw, 4rem);
    color: var(--cream);
    line-height: 1.1;
    margin-bottom: 8px;
  }

  .vote-count-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(201,168,76,0.12);
    border: 1px solid var(--border);
    border-radius: 999px;
    padding: 8px 20px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    color: var(--gold);
    margin-top: 12px;
  }
  .vote-count-badge .dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    background: var(--green);
    animation: pulse 1.5s infinite;
  }
  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.5; transform: scale(0.8); }
  }

  /* Results bars */
  .results-bars {
    display: flex;
    flex-direction: column;
    gap: 20px;
    flex: 1;
  }

  .result-row {
    display: grid;
    grid-template-columns: 220px 1fr 80px;
    align-items: center;
    gap: 20px;
  }

  .result-label {
    text-align: right;
  }
  .result-suspect {
    font-family: 'Playfair Display', serif;
    font-size: 1.2rem;
    font-weight: 700;
    color: var(--cream);
    display: block;
  }
  .result-judge {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    font-weight: 600;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--muted);
    display: block;
    margin-top: 2px;
  }

  .bar-track {
    height: 48px;
    background: rgba(255,255,255,0.04);
    border-radius: 8px;
    overflow: hidden;
    border: 1px solid rgba(255,255,255,0.06);
    position: relative;
  }
  .bar-fill {
    height: 100%;
    border-radius: 8px;
    transition: width 0.8s cubic-bezier(0.4, 0, 0.2, 1);
    position: relative;
    min-width: 4px;
    display: flex;
    align-items: center;
    padding-left: 14px;
  }
  .bar-fill.scarlett-bar { background: linear-gradient(90deg, #8b1a0e, #c0392b); }
  .bar-fill.mustard-bar { background: linear-gradient(90deg, #7a5500, var(--gold)); }
  .bar-fill.white-bar { background: linear-gradient(90deg, #4a5568, #a0aab4); }
  .bar-fill.green-bar { background: linear-gradient(90deg, #1a5e18, #49A942); }
  .bar-fill.peacock-bar { background: linear-gradient(90deg, #004a7a, #0081C6); }

  .bar-icon {
    font-size: 20px;
    filter: drop-shadow(0 1px 2px rgba(0,0,0,0.5));
  }

  .result-pct {
    font-family: 'Playfair Display', serif;
    font-size: 1.6rem;
    font-weight: 700;
    color: var(--gold2);
    text-align: right;
  }

  .leader-crown {
    display: inline;
    margin-left: 6px;
    font-size: 1.2rem;
  }

  /* Results footer */
  .results-footer {
    margin-top: 40px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-top: 24px;
    border-top: 1px solid var(--border);
  }
  .results-footer .brand {
    font-family: 'Playfair Display', serif;
    font-style: italic;
    font-size: 1.1rem;
    color: var(--gold);
  }
  .refresh-note {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 0.1em;
  }

  /* Status messages */
  .status-msg {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    text-align: center;
    padding: 10px;
    border-radius: 6px;
    margin-top: 12px;
    min-height: 36px;
    display: flex;
    align-items: center;
    justify-content: center;
    letter-spacing: 0.05em;
  }
  .status-msg.loading { color: var(--muted); }
  .status-msg.error { color: #e74c3c; background: rgba(231,76,60,0.1); }
  .status-msg.success { color: var(--green); background: rgba(73,169,66,0.1); }

  /* Spinner */
  .spinner {
    display: inline-block;
    width: 12px; height: 12px;
    border: 2px solid var(--muted);
    border-top-color: var(--gold);
    border-radius: 50%;
    animation: spin 0.8s linear infinite;
    margin-right: 8px;
    vertical-align: middle;
  }
  @keyframes spin { to { transform: rotate(360deg); } }

  /* Error state for results */
  .no-votes {
    text-align: center;
    padding: 60px 20px;
    color: var(--muted);
  }
  .no-votes .big-num {
    font-family: 'Playfair Display', serif;
    font-size: 5rem;
    color: rgba(201,168,76,0.2);
    display: block;
  }

  @media (max-width: 600px) {
    .result-row { grid-template-columns: 1fr; gap: 8px; }
    .result-label { text-align: left; }
    .result-pct { text-align: left; }
  }
</style>
</head>
<body>

<!-- Background -->
<div class="bg-layer"></div>
<div class="bg-grid"></div>

<!-- Host toggle (small, top-right) -->
<div class="view-toggle">
  <button class="view-btn active" id="btn-voter" onclick="switchView('voter')">VOTE</button>
  <button class="view-btn" id="btn-results" onclick="switchView('results')">RESULTS ⬡</button>
</div>

<div class="app">

  <!-- ═══ VOTER PAGE ═══ -->
  <div id="voter-view">
    <div class="voter-wrap">
      <div class="eyebrow">InnoTank 2026 · Resident Detective</div>
      <h1 class="voter-title">Who Done It?</h1>
      <p class="voter-subtitle">Cast your verdict, detective.</p>

      <div class="divider-ornament"><span>🕯</span></div>

      <!-- Voting form -->
      <div id="voting-form" style="width:100%">
        <div class="suspects-grid" id="suspects-grid">

          <div class="suspect-card scarlett" data-suspect="scarlett" onclick="selectSuspect(this)">
            <div class="suspect-icon">🔴</div>
            <div class="suspect-info">
              <span class="suspect-name">Miss Scarlett</span>
              <span class="suspect-alias">Katie Smith Sloan · LeadingAge CEO</span>
            </div>
            <div class="suspect-check">✓</div>
          </div>

          <div class="suspect-card mustard" data-suspect="mustard" onclick="selectSuspect(this)">
            <div class="suspect-icon">🟡</div>
            <div class="suspect-info">
              <span class="suspect-name">Colonel Mustard</span>
              <span class="suspect-alias">Chris Bird · LCS President & CEO</span>
            </div>
            <div class="suspect-check">✓</div>
          </div>

          <div class="suspect-card white" data-suspect="white" onclick="selectSuspect(this)">
            <div class="suspect-icon">⚪</div>
            <div class="suspect-info">
              <span class="suspect-name">Mrs. White</span>
              <span class="suspect-alias">Katie Schmitz · Ziegler Link•Age Funds</span>
            </div>
            <div class="suspect-check">✓</div>
          </div>

          <div class="suspect-card green" data-suspect="green" onclick="selectSuspect(this)">
            <div class="suspect-icon">🟢</div>
            <div class="suspect-info">
              <span class="suspect-name">Reverend Green</span>
              <span class="suspect-alias">John Hayes · Resident Representative</span>
            </div>
            <div class="suspect-check">✓</div>
          </div>

          <div class="suspect-card peacock" data-suspect="peacock" onclick="selectSuspect(this)">
            <div class="suspect-icon">🔵</div>
            <div class="suspect-info">
              <span class="suspect-name">Mrs. Peacock</span>
              <span class="suspect-alias">Frank Vedder · LCS CIO</span>
            </div>
            <div class="suspect-check">✓</div>
          </div>

        </div>

        <button class="submit-btn" id="submit-btn" disabled onclick="submitVote()">
          SUBMIT MY VERDICT
        </button>
        <div class="status-msg loading" id="voter-status"></div>
      </div>

      <!-- Post-vote state -->
      <div class="voted-state" id="voted-state">
        <div class="voted-icon">🔍</div>
        <h2 class="voted-title">Verdict recorded.</h2>
        <p class="voted-sub">Your accusation has been logged.<br>Watch the big screen for live results.</p>
      </div>

    </div>
  </div>

  <!-- ═══ RESULTS PAGE (Big Screen) ═══ -->
  <div id="results-view">
    <div class="results-wrap">

      <div class="results-header">
        <div class="eyebrow">Live Results · InnoTank 2026</div>
        <h2 class="results-title">The Verdict Is In</h2>
        <div class="vote-count-badge">
          <span class="dot"></span>
          <span id="total-votes-display">0 votes cast</span>
        </div>
      </div>

      <div class="results-bars" id="results-bars">
        <!-- rendered by JS -->
      </div>

      <div class="results-footer">
        <span class="brand">Resident Detective</span>
        <span class="refresh-note" id="last-refresh">Auto-refreshing every 3s</span>
      </div>

    </div>
  </div>

</div>

<script>
// ══════════════════════════════════════════════════════
//  CONFIGURATION
// ══════════════════════════════════════════════════════

// Persistent vote storage key — shared across all visitors via localStorage
// For production: replace with your Azure Function or Power Automate endpoint
const STORAGE_KEY = 'rd_innotank_votes_2026';

const SUSPECTS = [
  { id: 'scarlett', name: 'Miss Scarlett',    alias: 'Katie Smith Sloan',  role: 'LeadingAge CEO',          icon: '🔴', barClass: 'scarlett-bar' },
  { id: 'mustard',  name: 'Colonel Mustard',  alias: 'Chris Bird',         role: 'LCS President & CEO',     icon: '🟡', barClass: 'mustard-bar'  },
  { id: 'white',    name: 'Mrs. White',       alias: 'Katie Schmitz',      role: 'Ziegler Link•Age Funds',  icon: '⚪', barClass: 'white-bar'    },
  { id: 'green',    name: 'Reverend Green',   alias: 'John Hayes',         role: 'Resident Representative', icon: '🟢', barClass: 'green-bar'    },
  { id: 'peacock',  name: 'Mrs. Peacock',     alias: 'Frank Vedder',       role: 'LCS CIO',                 icon: '🔵', barClass: 'peacock-bar'  },
];

// ══════════════════════════════════════════════════════
//  STATE
// ══════════════════════════════════════════════════════

let selectedSuspect = null;
let hasVoted = false;
let resultsInterval = null;

// ══════════════════════════════════════════════════════
//  VOTE STORAGE (localStorage — works across tabs/devices on same origin)
//  For multi-device real production use, swap getVotes/saveVote 
//  to call your Power Automate HTTP endpoint or Azure Function
// ══════════════════════════════════════════════════════

function getVotes() {
  try {
    const raw = localStorage.getItem(STORAGE_KEY);
    if (!raw) return { scarlett:0, mustard:0, white:0, green:0, peacock:0 };
    return JSON.parse(raw);
  } catch(e) {
    return { scarlett:0, mustard:0, white:0, green:0, peacock:0 };
  }
}

function saveVote(suspectId) {
  const votes = getVotes();
  votes[suspectId] = (votes[suspectId] || 0) + 1;
  localStorage.setItem(STORAGE_KEY, JSON.stringify(votes));
  // Broadcast to other tabs
  window.dispatchEvent(new StorageEvent('storage', {
    key: STORAGE_KEY,
    newValue: JSON.stringify(votes)
  }));
  return votes;
}

function resetVotes() {
  const fresh = { scarlett:0, mustard:0, white:0, green:0, peacock:0 };
  localStorage.setItem(STORAGE_KEY, JSON.stringify(fresh));
  return fresh;
}

// ══════════════════════════════════════════════════════
//  VOTER LOGIC
// ══════════════════════════════════════════════════════

function selectSuspect(card) {
  if (hasVoted) return;
  document.querySelectorAll('.suspect-card').forEach(c => c.classList.remove('selected'));
  card.classList.add('selected');
  selectedSuspect = card.dataset.suspect;
  document.getElementById('submit-btn').disabled = false;
}

async function submitVote() {
  if (!selectedSuspect || hasVoted) return;

  const btn = document.getElementById('submit-btn');
  const status = document.getElementById('voter-status');

  btn.disabled = true;
  btn.textContent = 'RECORDING...';
  status.className = 'status-msg loading';
  status.innerHTML = '<span class="spinner"></span>Submitting your verdict...';

  try {
    saveVote(selectedSuspect);
    hasVoted = true;
    // Small delay for drama
    await new Promise(r => setTimeout(r, 800));

    document.getElementById('voting-form').style.display = 'none';
    const vs = document.getElementById('voted-state');
    vs.style.display = 'flex';

  } catch(err) {
    status.className = 'status-msg error';
    status.textContent = 'Error submitting vote. Please try again.';
    btn.disabled = false;
    btn.textContent = 'SUBMIT MY VERDICT';
  }
}

// ══════════════════════════════════════════════════════
//  RESULTS LOGIC
// ══════════════════════════════════════════════════════

function renderResults() {
  const votes = getVotes();
  const total = Object.values(votes).reduce((a, b) => a + b, 0);

  document.getElementById('total-votes-display').textContent =
    total === 1 ? '1 vote cast' : `${total.toLocaleString()} votes cast`;

  const container = document.getElementById('results-bars');

  // Sort by votes descending
  const sorted = [...SUSPECTS].sort((a, b) => (votes[b.id] || 0) - (votes[a.id] || 0));
  const maxVotes = Math.max(...sorted.map(s => votes[s.id] || 0), 1);
  const isLeader = sorted[0].id;

  container.innerHTML = sorted.map(s => {
    const count = votes[s.id] || 0;
    const pct = total > 0 ? Math.round((count / total) * 100) : 0;
    const barWidth = total > 0 ? Math.max(2, (count / maxVotes) * 100) : 2;
    const crown = (s.id === isLeader && total > 0) ? '<span class="leader-crown">👑</span>' : '';

    return `
      <div class="result-row">
        <div class="result-label">
          <span class="result-suspect">${s.name}${crown}</span>
          <span class="result-judge">${s.alias}</span>
        </div>
        <div class="bar-track">
          <div class="bar-fill ${s.barClass}" style="width:${barWidth}%">
            <span class="bar-icon">${s.icon}</span>
          </div>
        </div>
        <div class="result-pct">${pct}%</div>
      </div>
    `;
  }).join('');

  const now = new Date();
  document.getElementById('last-refresh').textContent =
    `Last updated ${now.toLocaleTimeString([], {hour:'2-digit',minute:'2-digit',second:'2-digit'})}`;
}

// Listen for storage events (other tabs voting)
window.addEventListener('storage', (e) => {
  if (e.key === STORAGE_KEY) renderResults();
});

// ══════════════════════════════════════════════════════
//  VIEW SWITCHING
// ══════════════════════════════════════════════════════

function switchView(view) {
  document.getElementById('voter-view').style.display = view === 'voter' ? 'block' : 'none';
  document.getElementById('results-view').style.display = view === 'results' ? 'block' : 'none';
  document.getElementById('btn-voter').className = 'view-btn' + (view === 'voter' ? ' active' : '');
  document.getElementById('btn-results').className = 'view-btn' + (view === 'results' ? ' active' : '');

  if (view === 'results') {
    renderResults();
    if (!resultsInterval) {
      resultsInterval = setInterval(renderResults, 3000);
    }
  } else {
    if (resultsInterval) {
      clearInterval(resultsInterval);
      resultsInterval = null;
    }
  }
}

// ══════════════════════════════════════════════════════
//  HOST CONTROLS (keyboard shortcuts)
//  R = toggle results view
//  Shift+X = reset all votes (confirm prompt)
// ══════════════════════════════════════════════════════

document.addEventListener('keydown', (e) => {
  if (e.key === 'r' || e.key === 'R') {
    const isResults = document.getElementById('results-view').style.display === 'block';
    switchView(isResults ? 'voter' : 'results');
  }
  if (e.key === 'X' && e.shiftKey) {
    if (confirm('Reset ALL votes? This cannot be undone.')) {
      resetVotes();
      renderResults();
      alert('Votes reset.');
    }
  }
});

// Init
renderResults();
</script>
</body>
</html>
