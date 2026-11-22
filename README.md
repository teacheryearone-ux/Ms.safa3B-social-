# Ms.safa3B-social-[modern_knowledge_school_year_3_social_studies_revision_arcade_hub.html](https://github.com/user-attachments/files/35244926/modern_knowledge_school_year_3_social_studies_revision_arcade_hub.html)
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Modern Knowledge School — Year 3 Social Studies Revision &amp; Arcade</title>
  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Google Fonts: Fredoka & Inter -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@500;600;700&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
  <!-- Font Awesome -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
  <script>
    tailwind.config = {
      theme: {
        extend: {
          fontFamily: {
            sans: ['Inter', 'sans-serif'],
            display: ['Fredoka', 'sans-serif'],
          },
          colors: {
            mksNavy: '#0f294a',
            mksGold: '#f59e0b',
            mksTeal: '#0d9488',
            mksCoral: '#f43f5e',
            mksIndigo: '#4f46e5',
          }
        }
      }
    }
  </script>
  <style>
    body {
      background-color: #f0f6f8;
      color: #1e293b;
      -webkit-tap-highlight-color: transparent;
    }
    .font-display {
      font-family: 'Fredoka', sans-serif;
    }
    @keyframes popIn {
      0% { transform: scale(0.93); opacity: 0; }
      100% { transform: scale(1); opacity: 1; }
    }
    .animate-pop {
      animation: popIn 0.25s cubic-bezier(0.16, 1, 0.3, 1) forwards;
    }
    @keyframes starPulse {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.32) rotate(12deg); }
    }
    .star-pulse {
      animation: starPulse 0.45s ease-in-out;
    }
    @keyframes shakeWrong {
      0%, 100% { transform: translateX(0); }
      25% { transform: translateX(-6px); }
      75% { transform: translateX(6px); }
    }
    .shake-wrong {
      animation: shakeWrong 0.28s ease-in-out;
    }
    .no-scrollbar::-webkit-scrollbar {
      display: none;
    }
    .no-scrollbar {
      -ms-overflow-style: none;
      scrollbar-width: none;
    }
    @media print {
      .no-print { display: none !important; }
      body { background: white; }
      .print-full { max-width: 100% !important; box-shadow: none !important; }
    }
  </style>
</head>
<body class="min-h-screen flex flex-col pb-24 md:pb-10">

  <!-- Sticky Top Header -->
  <header class="sticky top-0 z-40 bg-gradient-to-r from-mksNavy via-slate-900 to-teal-950 text-white shadow-lg no-print">
    <div class="max-w-5xl mx-auto px-4 py-3 flex items-center justify-between gap-2">
      <div class="flex items-center gap-3">
        <div class="w-11 h-11 rounded-2xl bg-gradient-to-br from-amber-400 to-orange-500 flex items-center justify-center text-mksNavy font-display font-bold text-xl shadow-md shrink-0">
          MKS
        </div>
        <div>
          <h1 class="font-display font-bold text-base sm:text-xl leading-tight tracking-wide">
            Modern Knowledge School
          </h1>
          <p class="text-xs text-teal-200 font-medium">Year 3 A/B • Social Studies Term 1 Revision &amp; Arcade</p>
        </div>
      </div>

      <!-- Sound Toggle & Live Star Points -->
      <div class="flex items-center gap-2 sm:gap-3">
        <button onclick="toggleSound()" title="Toggle Sound Effects" class="w-11 h-11 rounded-xl bg-white/10 hover:bg-white/20 flex items-center justify-center text-teal-200 transition">
          <i id="soundIcon" class="fa-solid fa-volume-high"></i>
        </button>
        <div id="starBadge" class="flex items-center gap-2 bg-amber-500/20 border border-amber-400/40 px-3.5 py-2 rounded-2xl">
          <i class="fa-solid fa-star text-amber-400 text-base"></i>
          <span id="starCount" class="font-display font-bold text-amber-300 text-base sm:text-lg">0</span>
          <span class="hidden sm:inline text-xs text-amber-200 font-medium">Stars</span>
        </div>
      </div>
    </div>

    <!-- Desktop Top Navigation Bar (5 Tabs) -->
    <nav class="hidden md:block bg-black/25 border-t border-white/10">
      <div class="max-w-5xl mx-auto px-4 grid grid-cols-5 gap-2 py-2">
        <button onclick="switchTab('study')" data-tab="study" class="nav-btn py-2.5 px-3 rounded-xl font-display font-semibold text-sm flex items-center justify-center gap-2 transition">
          <i class="fa-solid fa-book-open"></i> Study Hub
        </button>
        <button onclick="switchTab('games')" data-tab="games" class="nav-btn py-2.5 px-3 rounded-xl font-display font-semibold text-sm flex items-center justify-center gap-2 transition">
          <i class="fa-solid fa-gamepad"></i> Arcade Games
        </button>
        <button onclick="switchTab('tests')" data-tab="tests" class="nav-btn py-2.5 px-3 rounded-xl font-display font-semibold text-sm flex items-center justify-center gap-2 transition">
          <i class="fa-solid fa-circle-check"></i> Self-Correcting Tests
        </button>
        <button onclick="switchTab('papers')" data-tab="papers" class="nav-btn py-2.5 px-3 rounded-xl font-display font-semibold text-sm flex items-center justify-center gap-2 transition">
          <i class="fa-solid fa-file-pen"></i> Past Papers
        </button>
        <button onclick="switchTab('cheatsheet')" data-tab="cheatsheet" class="nav-btn py-2.5 px-3 rounded-xl font-display font-semibold text-sm flex items-center justify-center gap-2 transition">
          <i class="fa-solid fa-bolt"></i> Cheat Sheet
        </button>
      </div>
    </nav>
  </header>

  <!-- Main Content Container -->
  <main id="appContainer" class="flex-1 max-w-5xl w-full mx-auto px-4 pt-5 pb-8 print-full">
    <!-- Dynamic View Injected Here -->
  </main>

  <!-- Mobile Sticky Bottom Navigation Bar (5 Touch Targets) -->
  <nav class="md:hidden fixed bottom-0 inset-x-0 z-40 bg-white border-t border-slate-200 shadow-[0_-4px_16px_rgba(15,41,74,0.1)] px-1.5 py-1.5 no-print">
    <div class="grid grid-cols-5 gap-1">
      <button onclick="switchTab('study')" data-tab="study" class="mobile-nav-btn min-h-[52px] flex flex-col items-center justify-center py-1.5 px-1 rounded-xl text-[11px] font-semibold transition">
        <i class="fa-solid fa-book-open text-base mb-0.5"></i>
        <span>Study</span>
      </button>
      <button onclick="switchTab('games')" data-tab="games" class="mobile-nav-btn min-h-[52px] flex flex-col items-center justify-center py-1.5 px-1 rounded-xl text-[11px] font-semibold transition">
        <i class="fa-solid fa-gamepad text-base mb-0.5"></i>
        <span>Games</span>
      </button>
      <button onclick="switchTab('tests')" data-tab="tests" class="mobile-nav-btn min-h-[52px] flex flex-col items-center justify-center py-1.5 px-1 rounded-xl text-[11px] font-semibold transition">
        <i class="fa-solid fa-circle-check text-base mb-0.5"></i>
        <span>Tests</span>
      </button>
      <button onclick="switchTab('papers')" data-tab="papers" class="mobile-nav-btn min-h-[52px] flex flex-col items-center justify-center py-1.5 px-1 rounded-xl text-[11px] font-semibold transition">
        <i class="fa-solid fa-file-pen text-base mb-0.5"></i>
        <span>Papers</span>
      </button>
      <button onclick="switchTab('cheatsheet')" data-tab="cheatsheet" class="mobile-nav-btn min-h-[52px] flex flex-col items-center justify-center py-1.5 px-1 rounded-xl text-[11px] font-semibold transition">
        <i class="fa-solid fa-bolt text-base mb-0.5"></i>
        <span>Summary</span>
      </button>
    </div>
  </nav>

  <!-- Toast / Message Box (Replaces alert()) -->
  <div id="toastBox" class="fixed top-20 left-1/2 -translate-x-1/2 z-50 hidden max-w-sm w-[92%] bg-slate-900 text-white px-4 py-3 rounded-2xl shadow-2xl border border-white/15 flex items-center gap-3 animate-pop">
    <span id="toastIcon" class="text-xl">🌟</span>
    <p id="toastText" class="text-sm font-medium leading-snug"></p>
  </div>

  <script>
    // =========================================================================
    // 1. GLOBAL STATE & WEB AUDIO API SOUND ENGINE
    // =========================================================================
    const state = {
      activeTab: 'study',
      activeStudyTopic: 'disasters',
      activeTestTopic: 'all',
      stars: parseInt(localStorage.getItem('mks_y3_ss_stars') || '0', 10),
      solvedTests: JSON.parse(localStorage.getItem('mks_y3_ss_solved') || '{}'),
      soundEnabled: true,

      // Arcade Games State
      activeGame: 'disaster', // 'disaster' | 'pollution' | 'wonders' | 'manners'
      game1: { index: 0, score: 0, streak: 0, feedback: null, finished: false },
      game2: { index: 0, score: 0, streak: 0, feedback: null, finished: false },
      game3: { selectedWonder: null, matchedIds: [], wrongPair: null, score: 0 },
      game4: { subMode: 'stars', starIndex: 0, starScore: 0, starFeedback: null, blankAnswers: {}, blankChecked: false },

      // Past Papers State
      activePaperId: null,
      paperAnswers: {},
      paperSubmitted: false,
      paperTimed: false,
      timerSeconds: 1500, // 25 mins
      timerInterval: null
    };

    let audioCtx = null;
    function playTone(type) {
      if (!state.soundEnabled) return;
      try {
        if (!audioCtx) audioCtx = new (window.AudioContext || window.webkitAudioContext)();
        if (audioCtx.state === 'suspended') audioCtx.resume();
        const osc = audioCtx.createOscillator();
        const gain = audioCtx.createGain();
        osc.connect(gain);
        gain.connect(audioCtx.destination);
        const now = audioCtx.currentTime;

        if (type === 'correct') {
          osc.type = 'triangle';
          osc.frequency.setValueAtTime(523.25, now);
          osc.frequency.setValueAtTime(659.25, now + 0.08);
          osc.frequency.setValueAtTime(783.99, now + 0.16);
          gain.gain.setValueAtTime(0.18, now);
          gain.gain.exponentialRampToValueAtTime(0.001, now + 0.4);
          osc.start(now);
          osc.stop(now + 0.4);
        } else if (type === 'wrong') {
          osc.type = 'sawtooth';
          osc.frequency.setValueAtTime(210, now);
          osc.frequency.linearRampToValueAtTime(160, now + 0.24);
          gain.gain.setValueAtTime(0.12, now);
          gain.gain.exponentialRampToValueAtTime(0.001, now + 0.26);
          osc.start(now);
          osc.stop(now + 0.26);
        } else {
          osc.type = 'sine';
          osc.frequency.setValueAtTime(460, now);
          gain.gain.setValueAtTime(0.07, now);
          gain.gain.exponentialRampToValueAtTime(0.001, now + 0.09);
          osc.start(now);
          osc.stop(now + 0.09);
        }
      } catch (e) {}
    }

    function toggleSound() {
      state.soundEnabled = !state.soundEnabled;
      const icon = document.getElementById('soundIcon');
      icon.className = state.soundEnabled ? 'fa-solid fa-volume-high' : 'fa-solid fa-volume-xmark text-rose-300';
      showToast(state.soundEnabled ? 'Sound effects ON' : 'Sound effects muted', state.soundEnabled ? '🔊' : '🔇');
    }

    function addStars(points, uniqueId) {
      if (uniqueId && state.solvedTests[uniqueId]) return;
      if (uniqueId) {
        state.solvedTests[uniqueId] = true;
        localStorage.setItem('mks_y3_ss_solved', JSON.stringify(state.solvedTests));
      }
      state.stars += points;
      localStorage.setItem('mks_y3_ss_stars', String(state.stars));
      const countEl = document.getElementById('starCount');
      const badgeEl = document.getElementById('starBadge');
      if (countEl) countEl.textContent = state.stars;
      if (badgeEl) {
        badgeEl.classList.remove('star-pulse');
        void badgeEl.offsetWidth;
        badgeEl.classList.add('star-pulse');
      }
    }

    let toastTimer = null;
    function showToast(msg, icon = '🌟') {
      const box = document.getElementById('toastBox');
      document.getElementById('toastIcon').textContent = icon;
      document.getElementById('toastText').textContent = msg;
      box.classList.remove('hidden');
      clearTimeout(toastTimer);
      toastTimer = setTimeout(() => box.classList.add('hidden'), 2800);
    }

    // =========================================================================
    // 2. CUSTOM INLINE SVG ILLUSTRATIONS (Zero External Image Dependencies)
    // =========================================================================
    function getIllustrationSVG(key) {
      const svgs = {
        // --- NATURAL DISASTERS ---
        flood: `<svg viewBox="0 0 180 120" class="w-40 h-28 mx-auto rounded-xl bg-sky-100 border border-sky-200">
          <rect x="65" y="32" width="50" height="38" fill="#fef3c7" stroke="#0f294a" stroke-width="2.5"/>
          <polygon points="58,32 90,12 122,32" fill="#f43f5e" stroke="#0f294a" stroke-width="2.5"/>
          <rect x="83" y="46" width="14" height="24" fill="#92400e"/>
          <path d="M 0 68 Q 30 58 60 68 T 120 68 T 180 68 L 180 120 L 0 120 Z" fill="#0284c7" opacity="0.88"/>
          <path d="M 0 85 Q 30 75 60 85 T 120 85 T 180 85 L 180 120 L 0 120 Z" fill="#0369a1"/>
        </svg>`,
        earthquake: `<svg viewBox="0 0 180 120" class="w-40 h-28 mx-auto rounded-xl bg-amber-50 border border-amber-200">
          <rect x="28" y="34" width="42" height="50" transform="rotate(-7 49 59)" fill="#cbd5e1" stroke="#0f294a" stroke-width="2.5"/>
          <rect x="110" y="34" width="42" height="50" transform="rotate(7 131 59)" fill="#cbd5e1" stroke="#0f294a" stroke-width="2.5"/>
          <rect x="0" y="84" width="180" height="36" fill="#92400e"/>
          <polyline points="90,84 82,95 96,104 86,118" fill="none" stroke="#fef08a" stroke-width="3.5" stroke-linecap="round"/>
          <path d="M 18 28 Q 10 38 18 48" fill="none" stroke="#f43f5e" stroke-width="2.5"/>
          <path d="M 162 28 Q 170 38 162 48" fill="none" stroke="#f43f5e" stroke-width="2.5"/>
        </svg>`,
        tornado: `<svg viewBox="0 0 180 120" class="w-40 h-28 mx-auto rounded-xl bg-slate-200 border border-slate-300">
          <ellipse cx="90" cy="24" rx="58" ry="12" fill="#475569"/>
          <ellipse cx="90" cy="40" rx="44" ry="10" fill="#64748b"/>
          <ellipse cx="88" cy="56" rx="30" ry="8" fill="#475569"/>
          <ellipse cx="92" cy="72" rx="19" ry="6" fill="#64748b"/>
          <ellipse cx="89" cy="87" rx="11" ry="4" fill="#334155"/>
          <polygon points="84,90 94,90 90,108" fill="#1e293b"/>
          <rect x="0" y="106" width="180" height="14" fill="#65a30d"/>
        </svg>`,
        tsunami: `<svg viewBox="0 0 180 120" class="w-40 h-28 mx-auto rounded-xl bg-sky-100 border border-sky-200">
          <path d="M 10 105 C 20 25, 95 10, 125 42 C 102 42, 92 64, 122 82 L 175 82 L 175 105 Z" fill="#0284c7" stroke="#0f294a" stroke-width="2.5"/>
          <path d="M 118 36 C 128 32, 134 45, 123 50" fill="none" stroke="#ffffff" stroke-width="4" stroke-linecap="round"/>
          <rect x="136" y="64" width="24" height="22" fill="#fde68a" stroke="#0f294a" stroke-width="2"/>
          <polygon points="132,64 148,52 164,64" fill="#f43f5e" stroke="#0f294a" stroke-width="2"/>
          <rect x="0" y="104" width="180" height="16" fill="#0369a1"/>
        </svg>`,
        avalanche: `<svg viewBox="0 0 180 120" class="w-40 h-28 mx-auto rounded-xl bg-indigo-50 border border-indigo-200">
          <polygon points="15,110 78,18 155,110" fill="#64748b" stroke="#0f294a" stroke-width="2.5"/>
          <polygon points="78,18 55,52 72,48 82,58 98,46" fill="#ffffff"/>
          <circle cx="95" cy="70" r="14" fill="#ffffff" stroke="#cbd5e1" stroke-width="2"/>
          <circle cx="114" cy="84" r="18" fill="#ffffff" stroke="#cbd5e1" stroke-width="2"/>
          <circle cx="134" cy="96" r="16" fill="#ffffff" stroke="#cbd5e1" stroke-width="2"/>
        </svg>`,
        firstaid: `<svg viewBox="0 0 180 120" class="w-40 h-28 mx-auto rounded-xl bg-rose-50 border border-rose-200">
          <rect x="42" y="28" width="96" height="68" rx="12" fill="#ffffff" stroke="#e11d48" stroke-width="3.5"/>
          <path d="M 72 28 L 72 18 L 108 18 L 108 28" fill="none" stroke="#0f294a" stroke-width="3.5"/>
          <rect x="83" y="42" width="14" height="40" rx="3" fill="#e11d48"/>
          <rect x="70" y="55" width="40" height="14" rx="3" fill="#e11d48"/>
        </svg>`,

        // --- POLLUTION SCENES (Page 2 of PDF) ---
        air_pollution: `<svg viewBox="0 0 180 120" class="w-44 h-28 mx-auto rounded-xl bg-slate-300 border border-slate-400">
          <rect x="20" y="52" width="52" height="54" fill="#9a3412" stroke="#0f294a" stroke-width="2"/>
          <rect x="30" y="24" width="12" height="28" fill="#dc2626" stroke="#0f294a" stroke-width="2"/>
          <rect x="50" y="30" width="10" height="22" fill="#475569" stroke="#0f294a" stroke-width="2"/>
          <circle cx="36" cy="16" r="9" fill="#f8fafc" opacity="0.9"/>
          <circle cx="48" cy="11" r="11" fill="#e2e8f0" opacity="0.9"/>
          <rect x="92" y="84" width="44" height="18" rx="4" fill="#ef4444" stroke="#0f294a" stroke-width="2"/>
          <circle cx="102" cy="103" r="5" fill="#0f294a"/>
          <circle cx="126" cy="103" r="5" fill="#0f294a"/>
          <circle cx="146" cy="92" r="7" fill="#cbd5e1"/>
          <circle cx="158" cy="86" r="9" fill="#94a3b8"/>
          <rect x="0" y="106" width="180" height="14" fill="#334155"/>
        </svg>`,
        water_pollution: `<svg viewBox="0 0 180 120" class="w-44 h-28 mx-auto rounded-xl bg-sky-100 border border-sky-200">
          <rect x="135" y="15" width="45" height="75" fill="#cbd5e1" stroke="#0f294a" stroke-width="2"/>
          <rect x="105" y="34" width="34" height="16" fill="#65a30d" stroke="#0f294a" stroke-width="2"/>
          <path d="M 105 42 C 92 42, 92 78, 96 90 L 114 90 C 110 72, 114 50, 114 42 Z" fill="#4d7c0f"/>
          <rect x="0" y="84" width="180" height="36" fill="#0284c7"/>
          <ellipse cx="105" cy="88" rx="26" ry="6" fill="#3f6212"/>
          <ellipse cx="44" cy="78" rx="14" ry="8" fill="#fef3c7" stroke="#0f294a" stroke-width="1.5"/>
          <circle cx="34" cy="70" r="6" fill="#fef3c7" stroke="#0f294a" stroke-width="1.5"/>
          <polygon points="28,70 21,72 28,74" fill="#f97316"/>
        </svg>`,
        land_pollution: `<svg viewBox="0 0 180 120" class="w-44 h-28 mx-auto rounded-xl bg-lime-100 border border-lime-300">
          <rect x="0" y="75" width="180" height="45" fill="#84cc16"/>
          <rect x="122" y="45" width="32" height="38" fill="#64748b" stroke="#0f294a" stroke-width="2"/>
          <circle cx="132" cy="42" r="8" fill="#f59e0b"/>
          <circle cx="144" cy="43" r="7" fill="#ef4444"/>
          <path d="M 20 96 Q 62 62 105 96 Z" fill="#78350f"/>
          <rect x="42" y="76" width="16" height="10" rx="2" transform="rotate(-20 42 76)" fill="#38bdf8" stroke="#0f294a" stroke-width="1.5"/>
          <circle cx="74" cy="84" r="7" fill="#f43f5e" stroke="#0f294a" stroke-width="1.5"/>
          <rect x="86" y="78" width="12" height="12" fill="#fde047" stroke="#0f294a" stroke-width="1.5"/>
        </svg>`,

        // --- SEVEN WONDERS (Page 3 of PDF) ---
        petra: `<svg viewBox="0 0 180 120" class="w-44 h-28 mx-auto rounded-xl bg-amber-100 border border-amber-300">
          <rect x="28" y="16" width="124" height="94" fill="#c2410c" stroke="#0f294a" stroke-width="2"/>
          <polygon points="50,34 90,18 130,34" fill="#fb923c" stroke="#0f294a" stroke-width="2"/>
          <rect x="54" y="34" width="10" height="68" fill="#fed7aa"/>
          <rect x="76" y="34" width="10" height="68" fill="#fed7aa"/>
          <rect x="94" y="34" width="10" height="68" fill="#fed7aa"/>
          <rect x="116" y="34" width="10" height="68" fill="#fed7aa"/>
          <rect x="83" y="74" width="14" height="28" fill="#431407"/>
        </svg>`,
        great_wall: `<svg viewBox="0 0 180 120" class="w-44 h-28 mx-auto rounded-xl bg-emerald-100 border border-emerald-300">
          <polygon points="0,115 55,42 115,115" fill="#16a34a"/>
          <polygon points="65,115 130,32 180,115" fill="#15803d"/>
          <path d="M 15 95 Q 65 55 110 72 T 165 44" fill="none" stroke="#d6d3d1" stroke-width="14" stroke-linecap="round"/>
          <path d="M 15 95 Q 65 55 110 72 T 165 44" fill="none" stroke="#0f294a" stroke-width="2" stroke-dasharray="6 4"/>
          <rect x="102" y="56" width="18" height="18" fill="#a8a29e" stroke="#0f294a" stroke-width="2"/>
        </svg>`,
        pyramids: `<svg viewBox="0 0 180 120" class="w-44 h-28 mx-auto rounded-xl bg-amber-50 border border-amber-200">
          <circle cx="145" cy="26" r="12" fill="#facc15"/>
          <polygon points="22,96 74,26 124,96" fill="#f59e0b" stroke="#0f294a" stroke-width="2"/>
          <polygon points="74,26 124,96 96,96" fill="#d97706"/>
          <polygon points="88,96 128,44 166,96" fill="#fbbf24" stroke="#0f294a" stroke-width="2"/>
          <rect x="0" y="96" width="180" height="24" fill="#fde68a"/>
        </svg>`,
        colossus: `<svg viewBox="0 0 180 120" class="w-44 h-28 mx-auto rounded-xl bg-sky-100 border border-sky-200">
          <rect x="0" y="94" width="180" height="26" fill="#0284c7"/>
          <rect x="44" y="82" width="24" height="14" fill="#94a3b8" stroke="#0f294a" stroke-width="2"/>
          <rect x="112" y="82" width="24" height="14" fill="#94a3b8" stroke="#0f294a" stroke-width="2"/>
          <path d="M 56 82 L 78 46 L 102 46 L 124 82" fill="none" stroke="#d97706" stroke-width="9" stroke-linecap="round"/>
          <rect x="76" y="30" width="28" height="24" rx="4" fill="#f59e0b" stroke="#0f294a" stroke-width="2"/>
          <circle cx="90" cy="20" r="8" fill="#fbbf24" stroke="#0f294a" stroke-width="2"/>
          <line x1="104" y1="36" x2="124" y2="18" stroke="#f59e0b" stroke-width="6" stroke-linecap="round"/>
          <circle cx="126" cy="15" r="6" fill="#ef4444"/>
        </svg>`,
        babylon: `<svg viewBox="0 0 180 120" class="w-44 h-28 mx-auto rounded-xl bg-emerald-50 border border-emerald-200">
          <rect x="26" y="76" width="128" height="26" fill="#d97706" stroke="#0f294a" stroke-width="2"/>
          <rect x="42" y="52" width="96" height="24" fill="#f59e0b" stroke="#0f294a" stroke-width="2"/>
          <rect x="60" y="30" width="60" height="22" fill="#fbbf24" stroke="#0f294a" stroke-width="2"/>
          <path d="M 28 76 Q 36 90 44 76 T 60 76 T 76 76 T 92 76 T 108 76 T 124 76 T 140 76" fill="none" stroke="#16a34a" stroke-width="6"/>
          <path d="M 44 52 Q 52 64 60 52 T 76 52 T 92 52 T 108 52 T 124 52" fill="none" stroke="#22c55e" stroke-width="5"/>
        </svg>`,
        pisa: `<svg viewBox="0 0 180 120" class="w-44 h-28 mx-auto rounded-xl bg-sky-50 border border-sky-200">
          <g transform="rotate(11 90 105)">
            <rect x="72" y="22" width="36" height="84" rx="4" fill="#f8fafc" stroke="#0f294a" stroke-width="2.5"/>
            <line x1="72" y1="38" x2="108" y2="38" stroke="#0f294a" stroke-width="2"/>
            <line x1="72" y1="54" x2="108" y2="54" stroke="#0f294a" stroke-width="2"/>
            <line x1="72" y1="70" x2="108" y2="70" stroke="#0f294a" stroke-width="2"/>
            <line x1="72" y1="86" x2="108" y2="86" stroke="#0f294a" stroke-width="2"/>
            <rect x="78" y="12" width="24" height="10" fill="#e2e8f0" stroke="#0f294a" stroke-width="2"/>
          </g>
          <rect x="0" y="104" width="180" height="16" fill="#4ade80"/>
        </svg>`
      };
      return svgs[key] || '';
    }

    // =========================================================================
    // 3. DATA BANKS FOR ARCADE GAMES, SELF-CORRECTING TESTS & PAST PAPERS
    // =========================================================================
    // Game 1 Data: Exercise 1 & 2
    const disasterScenarios = [
      { prompt: '“Too much water is flowing from the river!”', svg: 'flood', answer: 'Flood', options: ['Flood', 'Earthquake', 'Tornado', 'Tsunami', 'Avalanche'] },
      { prompt: '“The whole ground is shaking under me!”', svg: 'earthquake', answer: 'Earthquake', options: ['Flood', 'Earthquake', 'Tornado', 'Tsunami', 'Avalanche'] },
      { prompt: '“Watch out! An air funnel is coming close.”', svg: 'tornado', answer: 'Tornado', options: ['Flood', 'Earthquake', 'Tornado', 'Tsunami', 'Avalanche'] },
      { prompt: '“Look! The water waves are so high!”', svg: 'tsunami', answer: 'Tsunami', options: ['Flood', 'Earthquake', 'Tornado', 'Tsunami', 'Avalanche'] },
      { prompt: '“Look at the snow! The mountain is breaking up!”', svg: 'avalanche', answer: 'Avalanche', options: ['Flood', 'Earthquake', 'Tornado', 'Tsunami', 'Avalanche'] },
      { prompt: 'Someone falls and gets hurt. What might help?', svg: 'firstaid', answer: 'Rubbing alcohol', options: ['Rubbing alcohol', 'A flashlight', 'A book', 'Perfume'] },
      { prompt: 'The light goes off during a storm. What should you use?', svg: 'firstaid', answer: 'A flashlight', options: ['A flashlight', 'Rubbing alcohol', 'A book', 'Perfume'] },
      { prompt: 'Someone burns their finger. What should you use?', svg: 'firstaid', answer: 'Bandages', options: ['Bandages', 'Perfume', 'A book', 'Drink water'] }
    ];

    // Game 2 Data: Exercise 3 & 5 (Pollution Sorter)
    const pollutionCards = [
      { title: 'Factories and cars releasing thick smoke into the sky', svg: 'air_pollution', answer: 'Air pollution' },
      { title: 'A green pipe dumping dirty sewage into a river where a duck swims', svg: 'water_pollution', answer: 'Water pollution' },
      { title: 'Overflowing trash cans, old tires, and garbage piled on the grass', svg: 'land_pollution', answer: 'Land pollution' },
      { title: 'Ships throwing their garbage into the sea', svg: 'water_pollution', answer: 'Water pollution' },
      { title: 'Dumping a broken washing machine and old mattresses in the forest', svg: 'land_pollution', answer: 'Land pollution' },
      { title: 'A boy coughing from dark exhaust smoke on a busy street', svg: 'air_pollution', answer: 'Air pollution' }
    ];

    // Game 3 Data: Exercise 4 (Seven Wonders)
    const wondersList = [
      { id: 'w1', name: 'Petra', country: 'Jordan', svg: 'petra' },
      { id: 'w2', name: 'Great Wall of China', country: 'China', svg: 'great_wall' },
      { id: 'w3', name: 'Pyramids of Giza', country: 'Egypt', svg: 'pyramids' },
      { id: 'w4', name: 'Colossus of Rhodes', country: 'Greece', svg: 'colossus' },
      { id: 'w5', name: 'Hanging Gardens of Babylon', country: 'Iraq', svg: 'babylon' },
      { id: 'w6', name: 'Leaning Tower of Pisa', country: 'Italy', svg: 'pisa' }
    ];

    // Game 4 Data: Exercise 6 & 9 (Star Sorter: Green = Well-Mannered / Good Friend, Red = Not Well-Mannered)
    const starScenarios = [
      { text: 'Layla took Samir’s pencil and kept it without asking.', isGood: false, reason: 'Taking things without asking is NOT well-mannered (Red Star).' },
      { text: 'Omar couldn’t solve a problem in class. Leila stayed after school to help him.', isGood: true, reason: 'Helping a classmate is kind and well-mannered (Green Star)!' },
      { text: 'Tamer always uses his classmates’ toys without permission and never returns them.', isGood: false, reason: 'Using toys without permission and not returning them is NOT well-mannered (Red Star).' },
      { text: 'Noor asked, “May I please use your phone to call my parent?” before asking.', isGood: true, reason: 'Asking politely with “May I please...” is well-mannered (Green Star)!' },
      { text: 'Your friend borrows your book and returns it on time and in good condition.', isGood: true, reason: 'Returning borrowed items safely shows good friendship (Green Star)!' },
      { text: 'Your friend laughs at you when you make a mistake in front of others.', isGood: false, reason: 'Laughing at others’ mistakes is hurtful (Red Star).' },
      { text: 'Your friend shares their snack with you when you forget yours.', isGood: true, reason: 'Sharing food with a friend shows kindness (Green Star)!' },
      { text: 'Your friend spreads a secret you told them to other classmates.', isGood: false, reason: 'Spreading secrets breaks trust (Red Star).' },
      { text: 'Your friend congratulates you when you win a game, even if they lose.', isGood: true, reason: 'Being happy for a friend’s win shows great sportsmanship (Green Star)!' },
      { text: 'Your friends blame you for something they did, and never apologize.', isGood: false, reason: 'Blaming others without apologizing is unfair (Red Star).' }
    ];

    // Self-Correcting Test Bank (All Exercises 1–11)
    const testQuestions = [
      // Disasters & Safety (Ex 1, 2, 5)
      {
        id: 'q1',
        topic: 'disasters',
        exLabel: 'Exercise 1 • Natural Disasters',
        prompt: '“Too much water is flowing from the river!” Which natural disaster is this?',
        svg: 'flood',
        options: ['Flood', 'Earthquake', 'Tornado', 'Avalanche'],
        answer: 'Flood',
        hint: 'When a river overflows onto dry land, it causes a...',
        explanation: 'A Flood occurs when too much water overflows from a river or heavy rain.'
      },
      {
        id: 'q2',
        topic: 'disasters',
        exLabel: 'Exercise 1 • Natural Disasters',
        prompt: '“Watch out! An air funnel is coming close.” Which natural disaster is this?',
        svg: 'tornado',
        options: ['Tsunami', 'Tornado', 'Flood', 'Earthquake'],
        answer: 'Tornado',
        hint: 'A spinning funnel of strong wind touching the ground.',
        explanation: 'A Tornado is a violently spinning funnel of air.'
      },
      {
        id: 'q3',
        topic: 'disasters',
        exLabel: 'Exercise 1 • Natural Disasters',
        prompt: '“Look at the snow! The mountain is breaking up!” Which natural disaster is this?',
        svg: 'avalanche',
        options: ['Avalanche', 'Tsunami', 'Earthquake', 'Flood'],
        answer: 'Avalanche',
        hint: 'A huge mass of snow sliding rapidly down a mountain.',
        explanation: 'An Avalanche happens when snow breaks loose and slides down a mountain.'
      },
      {
        id: 'q4',
        topic: 'disasters',
        exLabel: 'Exercise 2 & 5 • First-Aid & Emergency Kit',
        prompt: 'What might help if someone falls and gets hurt?',
        svg: 'firstaid',
        options: ['Drink water', 'Rubbing alcohol', 'A book', 'Perfume'],
        answer: 'Rubbing alcohol',
        hint: 'Used to clean a cut or scrape so it does not get infected.',
        explanation: 'Rubbing alcohol helps clean wounds when someone falls and gets hurt.'
      },
      {
        id: 'q5',
        topic: 'disasters',
        exLabel: 'Exercise 2 • Emergency Safety',
        prompt: 'What should you use if someone burns their finger?',
        options: ['Perfume', 'Bandages', 'A book'],
        answer: 'Bandages',
        hint: 'Never put perfume on a burn! Protect the skin with clean...',
        explanation: 'Clean bandages protect a burned finger; perfume would sting and harm the skin.'
      },

      // Pollution & Wonders (Ex 3, 4, 5)
      {
        id: 'q6',
        topic: 'pollution',
        exLabel: 'Exercise 5 • Pollution & Wildlife',
        prompt: 'Water pollution might be caused by _______ that throw their garbage in the sea.',
        svg: 'water_pollution',
        options: ['farmers', 'ships', 'teachers', 'doctors'],
        answer: 'ships',
        hint: 'Which one travels across the sea and ocean?',
        explanation: 'Ships that dump waste or garbage into the sea cause water pollution.'
      },
      {
        id: 'q7',
        topic: 'pollution',
        exLabel: 'Exercise 5 • Endangered Animals',
        prompt: 'A(n) _______ animal might not exist after a few years.',
        options: ['common', 'endangered', 'noisy', 'farm'],
        answer: 'endangered',
        hint: 'Animals in danger of disappearing forever are called...',
        explanation: 'Endangered animals have very small populations and may disappear if we do not protect them.'
      },
      {
        id: 'q8',
        topic: 'wonders',
        exLabel: 'Exercise 4 • World Wonders',
        prompt: 'In which country is Petra located?',
        svg: 'petra',
        options: ['China', 'Jordan', 'Italy', 'Greece'],
        answer: 'Jordan',
        hint: 'Petra is the famous rose-red city carved into rock in the Middle East.',
        explanation: 'Petra is located in Jordan.'
      },
      {
        id: 'q9',
        topic: 'wonders',
        exLabel: 'Exercise 4 • World Wonders',
        prompt: 'In which country is the Colossus of Rhodes located?',
        svg: 'colossus',
        options: ['Iraq', 'Jordan', 'Greece', 'Egypt'],
        answer: 'Greece',
        hint: 'The island of Rhodes is part of this European country.',
        explanation: 'The Colossus of Rhodes stood in Greece.'
      },
      {
        id: 'q10',
        topic: 'wonders',
        exLabel: 'Exercise 4 • World Wonders',
        prompt: 'In which country were the Hanging Gardens of Babylon located?',
        svg: 'babylon',
        options: ['Italy', 'Greece', 'Iraq', 'Jordan'],
        answer: 'Iraq',
        hint: 'Ancient Babylon was located in Mesopotamia, modern-day...',
        explanation: 'The Hanging Gardens of Babylon were located in Iraq.'
      },
      {
        id: 'q11',
        topic: 'wonders',
        exLabel: 'Exercise 4 • World Wonders',
        prompt: 'In which country is the Leaning Tower of Pisa?',
        svg: 'pisa',
        options: ['Italy', 'China', 'Egypt', 'Greece'],
        answer: 'Italy',
        hint: 'Pisa is a famous city in the same country as Rome.',
        explanation: 'The Leaning Tower of Pisa is in Italy.'
      },

      // Hygiene, Habits & Manners (Ex 6, 7, 10, 11)
      {
        id: 'q12',
        topic: 'habits',
        exLabel: 'Exercise 7 • Personal Hygiene',
        prompt: 'You finished practicing football, and you are very sweaty. You should _______.',
        options: ['wash your hands only', 'take a shower', 'put on dirty clothes', 'skip dinner'],
        answer: 'take a shower',
        hint: 'Sweat covers your whole body after sports!',
        explanation: 'Taking a shower cleans sweat and germs off your whole body after sports.'
      },
      {
        id: 'q13',
        topic: 'habits',
        exLabel: 'Exercise 7 • Personal Hygiene',
        prompt: 'Something is wrong with your nails. They need _______.',
        options: ['to be painted only', 'trimming and cleaning', 'to be ignored', 'to be buried'],
        answer: 'trimming and cleaning',
        hint: 'Long nails trap dirt and bacteria underneath.',
        explanation: 'Keeping nails trimmed and clean prevents dirt and germs from building up.'
      },
      {
        id: 'q14',
        topic: 'habits',
        exLabel: 'Exercise 7 • Bathroom Habits',
        prompt: 'You are in the bathroom. You should not leave before _______.',
        options: ['turning off the tap and washing your hands', 'shouting loudly', 'throwing away your towel', 'locking the door outside'],
        answer: 'turning off the tap and washing your hands',
        hint: 'Save water and keep your hands clean!',
        explanation: 'Always turn off the tap to save water and wash your hands with soap.'
      },
      {
        id: 'q15',
        topic: 'habits',
        exLabel: 'Exercise 10 • Healthy Lifestyle',
        prompt: 'Video games might make you stay seated for a long time, and your body will be _______.',
        options: ['tired', 'hungry', 'comfortable', 'idle (lazy)'],
        answer: 'idle (lazy)',
        hint: 'Sitting too long without moving makes your body inactive or...',
        explanation: 'Too much screen time makes your body idle (lazy); playing sports keeps you active!'
      },
      {
        id: 'q16',
        topic: 'habits',
        exLabel: 'Exercise 11 • Polite Magic Words',
        prompt: 'Which pair shows polite words to remember (“magic words”)?',
        options: ['rude and idle', 'sorry and excuse me!', 'food and smell'],
        answer: 'sorry and excuse me!',
        hint: 'Words we say when we bump into someone or want to speak politely.',
        explanation: '“Sorry” and “Excuse me!” are polite magic words.'
      },

      // Leaders, Followers & Friendship (Ex 8, 9, 10, 11)
      {
        id: 'q17',
        topic: 'leadership',
        exLabel: 'Exercise 8 • Reading Comprehension (Robin & Samia)',
        prompt: 'Story: “Robin does not like to do anything on his own. He asks Samia about everything he wants to do. Sometimes Samia decides what Robin has to eat too. He never complains.” Who makes most of the decisions in the story?',
        options: ['Samia', 'Robin', 'The teacher'],
        answer: 'Samia',
        hint: 'Robin asks her about everything he wants to do.',
        explanation: 'Samia acts as the leader and makes most of the decisions in the story.'
      },
      {
        id: 'q18',
        topic: 'leadership',
        exLabel: 'Exercise 8 • Reading Comprehension (Robin & Samia)',
        prompt: 'In the same story, what are two actions Robin does that show he is a follower?',
        options: [
          'He asks Samia about everything and joins any activity she tells him to do',
          'He gives orders to Samia and complains every day',
          'He refuses to eat and runs away'
        ],
        answer: 'He asks Samia about everything and joins any activity she tells him to do',
        hint: 'Look at sentences 2 and 3 of the passage.',
        explanation: 'Robin asks Samia before doing anything, follows her activity choices, and eats what she decides.'
      },
      {
        id: 'q19',
        topic: 'leadership',
        exLabel: 'Exercise 8 • Reading Comprehension (Robin & Samia)',
        prompt: 'Does Robin ever complain about Samia’s decisions? (Yes / No)',
        options: ['No', 'Yes'],
        answer: 'No',
        hint: 'Read the last sentence: “He never complains.”',
        explanation: 'No — the passage states, “He never complains.”'
      },
      {
        id: 'q20',
        topic: 'leadership',
        exLabel: 'Exercise 10 & 11 • Good Leaders',
        prompt: 'A _______ should help followers and _______ things with them.',
        options: ['leader / share', 'follower / steal', 'teacher / hide', 'stranger / take'],
        answer: 'leader / share',
        hint: 'Good leaders listen, help others, and share ideas.',
        explanation: 'A good leader helps followers and shares things and ideas with them.'
      },
      {
        id: 'q21',
        topic: 'leadership',
        exLabel: 'Exercise 9 • Good Friendship',
        prompt: 'Your friend helps you carry heavy books when you are struggling. Does this show good friendship?',
        options: ['Yes', 'No'],
        answer: 'Yes',
        hint: 'Helping a friend in need is a caring action.',
        explanation: 'Yes! Helping a friend who is struggling shows true friendship.'
      }
    ];

    // Past Papers Data (2 Complete Exam Papers)
    const pastPapers = {
      paper1: {
        id: 'paper1',
        title: 'Past Paper 1: Official MKS Enrichment Exam',
        subtitle: 'All 11 Worksheet Exercises • 15 Questions • Full Curriculum Coverage',
        minutes: 25,
        questions: [
          { id: 'p1_1', topic: 'Disasters & Safety', prompt: '1. “Look! The water waves are so high!” Which natural disaster is this?', svg: 'tsunami', options: ['Flood', 'Tsunami', 'Tornado', 'Avalanche'], answer: 'Tsunami', explanation: 'Giant ocean waves are caused by a Tsunami.' },
          { id: 'p1_2', topic: 'Disasters & Safety', prompt: '2. “The whole ground is shaking under me!” Which natural disaster is this?', svg: 'earthquake', options: ['Earthquake', 'Flood', 'Avalanche', 'Tsunami'], answer: 'Earthquake', explanation: 'Shaking ground is an Earthquake.' },
          { id: 'p1_3', topic: 'Disasters & Safety', prompt: '3. What should you use if the light goes off?', options: ['A book', 'A flashlight', 'Perfume'], answer: 'A flashlight', explanation: 'A flashlight provides safe light during a power outage.' },
          { id: 'p1_4', topic: 'Pollution & Wonders', prompt: '4. Factories and cars releasing smoke into the sky cause _______.', svg: 'air_pollution', options: ['Air pollution', 'Water pollution', 'Land pollution'], answer: 'Air pollution', explanation: 'Smoke and exhaust gases pollute the air we breathe.' },
          { id: 'p1_5', topic: 'Pollution & Wonders', prompt: '5. Choose the correct country for the Pyramids of Giza.', svg: 'pyramids', options: ['Jordan', 'Egypt', 'Greece', 'Iraq'], answer: 'Egypt', explanation: 'The Pyramids of Giza are located in Egypt.' },
          { id: 'p1_6', topic: 'Pollution & Wonders', prompt: '6. Choose the correct country for the Great Wall of China.', svg: 'great_wall', options: ['China', 'Italy', 'Jordan', 'Egypt'], answer: 'China', explanation: 'The Great Wall is located in China.' },
          { id: 'p1_7', topic: 'Pollution & Wonders', prompt: '7. A(n) _______ animal might not exist after a few years.', options: ['common', 'endangered', 'noisy', 'farm'], answer: 'endangered', explanation: 'Endangered animals are at risk of extinction.' },
          { id: 'p1_8', topic: 'Manners & Hygiene', prompt: '8. Fill in the blank: Noor asked, “May I please use your phone to call my _______?” before asking.', options: ['parent', 'return', 'permission', 'help'], answer: 'parent', explanation: 'Noor politely asked permission to call her parent.' },
          { id: 'p1_9', topic: 'Manners & Hygiene', prompt: '9. You are getting ready to go to bed. Don’t forget to _______.', options: ['run outside', 'eat lots of candy', 'brush your teeth', 'watch a long movie'], answer: 'brush your teeth', explanation: 'Brushing your teeth before bed keeps them healthy and clean.' },
          { id: 'p1_10', topic: 'Manners & Hygiene', prompt: '10. Before leaving a play area, we must make sure it is _______.', options: ['messy', 'clean and neat', 'locked', 'noisy'], answer: 'clean and neat', explanation: 'Good citizens always leave play areas clean and neat.' },
          { id: 'p1_11', topic: 'Manners & Hygiene', prompt: '11. _______ foods keep my body in good shape.', options: ['Junk', 'Sweet', 'Healthy', 'Spicy'], answer: 'Healthy', explanation: 'Healthy foods give us energy and keep our bodies strong.' },
          { id: 'p1_12', topic: 'Manners & Hygiene', prompt: '12. After playing sports, you should _______.', options: ['take off your shoes', 'wash and change your clothes', 'do both a and b'], answer: 'do both a and b', explanation: 'After sports, take off your sweaty shoes, wash up, and put on clean clothes.' },
          { id: 'p1_13', topic: 'Leaders & Friendship', prompt: '13. In the story about Robin and Samia, who follows the other’s choices?', options: ['Robin', 'Samia', 'Both equally'], answer: 'Robin', explanation: 'Robin asks Samia about everything and follows her choices.' },
          { id: 'p1_14', topic: 'Leaders & Friendship', prompt: '14. Which quality helps you become a good leader?', options: ['listening and sharing ideas', 'giving orders only', 'making fun of others'], answer: 'listening and sharing ideas', explanation: 'Good leaders listen to others and share ideas.' },
          { id: 'p1_15', topic: 'Leaders & Friendship', prompt: '15. Your friend ignores you when you ask for help with homework. Does this show good friendship?', options: ['Yes', 'No'], answer: 'No', explanation: 'No — good friends help and support each other.' }
        ]
      },
      paper2: {
        id: 'paper2',
        title: 'Past Paper 2: Term 1 Challenge Mock Exam',
        subtitle: 'Fresh Exam Scenarios • 12 Questions • Self-Marking Report',
        minutes: 20,
        questions: [
          { id: 'p2_1', topic: 'Disasters & Safety', prompt: '1. Heavy rain makes a river overflow into nearby houses. Which disaster is happening?', svg: 'flood', options: ['Flood', 'Tornado', 'Avalanche', 'Earthquake'], answer: 'Flood', explanation: 'Overflowing river water causes a Flood.' },
          { id: 'p2_2', topic: 'Disasters & Safety', prompt: '2. Which item belongs inside an emergency first-aid kit?', svg: 'firstaid', options: ['Bandages', 'Toys', 'Pencils', 'Pillows'], answer: 'Bandages', explanation: 'Bandages are essential first-aid kit supplies.' },
          { id: 'p2_3', topic: 'Pollution & Wonders', prompt: '3. People leave plastic bottles, old tires, and garbage in a park. What type of pollution is this?', svg: 'land_pollution', options: ['Land pollution', 'Air pollution', 'Water pollution'], answer: 'Land pollution', explanation: 'Dumping trash on the ground causes Land pollution.' },
          { id: 'p2_4', topic: 'Pollution & Wonders', prompt: '4. Which of these is one of the famous World Wonders?', options: ['A supermarket', 'The Great Wall of China', 'A hospital', 'A library'], answer: 'The Great Wall of China', explanation: 'The Great Wall of China is one of the Wonders of the World.' },
          { id: 'p2_5', topic: 'Pollution & Wonders', prompt: '5. Match the wonder to its country: Leaning Tower of Pisa is in _______.', svg: 'pisa', options: ['Greece', 'Jordan', 'Italy', 'Iraq'], answer: 'Italy', explanation: 'The Leaning Tower of Pisa is located in Italy.' },
          { id: 'p2_6', topic: 'Manners & Hygiene', prompt: '6. A person who does not act in a bad way towards others is _______.', options: ['rude', 'well-mannered', 'jealous', 'careless'], answer: 'well-mannered', explanation: 'Treating others kindly and politely means being well-mannered.' },
          { id: 'p2_7', topic: 'Manners & Hygiene', prompt: '7. You are preparing to go to school in the morning. Make sure your hair and teeth are _______.', options: ['messy and sticky', 'covered with paint', 'wet and cold', 'clean and tidy'], answer: 'clean and tidy', explanation: 'Clean teeth and tidy hair are important morning hygiene habits.' },
          { id: 'p2_8', topic: 'Manners & Hygiene', prompt: '8. Instead of playing video games all the time, it is better to _______.', options: ['practice sports', 'sleep during the day', 'stay seated all day'], answer: 'practice sports', explanation: 'Practicing sports keeps your body healthy and active.' },
          { id: 'p2_9', topic: 'Manners & Hygiene', prompt: '9. Your friends are ordering food for dinner. You should choose _______.', options: ['without telling them', 'healthy food you like and share politely', 'the most expensive thing always', 'only dessert'], answer: 'healthy food you like and share politely', explanation: 'Choosing healthy food and sharing politely shows good table manners.' },
          { id: 'p2_10', topic: 'Leaders & Friendship', prompt: '10. Why might someone follow another person’s choices (like Robin follows Samia)?', options: ['Because they trust their friend or feel shy deciding alone', 'Because they want to be rude', 'Because they hate their friends'], answer: 'Because they trust their friend or feel shy deciding alone', explanation: 'People often follow others when they trust their friend’s ideas or feel unsure deciding alone.' },
          { id: 'p2_11', topic: 'Leaders & Friendship', prompt: '11. We have to choose _______ who can make us happy.', options: ['doors', 'always', 'friends', 'loudly'], answer: 'friends', explanation: 'Choosing kind, caring friends makes us happy.' },
          { id: 'p2_12', topic: 'Leaders & Friendship', prompt: '12. Your friend borrows your pencil after asking permission and returns it neatly. Is this well-mannered?', options: ['Yes (Green Star)', 'No (Red Star)'], answer: 'Yes (Green Star)', explanation: 'Asking permission and returning borrowed items earns a Green Star!' }
        ]
      }
    };

    // =========================================================================
    // 4. TAB NAVIGATION & SHELL RENDERER
    // =========================================================================
    function switchTab(tab) {
      playTone('click');
      state.activeTab = tab;
      if (tab !== 'papers') clearInterval(state.timerInterval);
      updateNavStyles();
      renderCurrentView();
      window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    function updateNavStyles() {
      document.querySelectorAll('.nav-btn').forEach(btn => {
        const active = btn.dataset.tab === state.activeTab;
        btn.className = active
          ? 'nav-btn py-2.5 px-3 rounded-xl font-display font-semibold text-sm flex items-center justify-center gap-2 transition bg-amber-400 text-mksNavy shadow-md'
          : 'nav-btn py-2.5 px-3 rounded-xl font-display font-semibold text-sm flex items-center justify-center gap-2 transition text-white/85 hover:bg-white/10';
      });
      document.querySelectorAll('.mobile-nav-btn').forEach(btn => {
        const active = btn.dataset.tab === state.activeTab;
        btn.className = active
          ? 'mobile-nav-btn min-h-[52px] flex flex-col items-center justify-center py-1.5 px-1 rounded-xl text-[11px] font-bold transition bg-teal-50 text-mksTeal ring-1 ring-teal-200'
          : 'mobile-nav-btn min-h-[52px] flex flex-col items-center justify-center py-1.5 px-1 rounded-xl text-[11px] font-medium transition text-slate-500 hover:text-slate-800';
      });
    }

    function renderCurrentView() {
      const container = document.getElementById('appContainer');
      if (state.activeTab === 'study') container.innerHTML = renderStudyHubView();
      else if (state.activeTab === 'games') container.innerHTML = renderGamesView();
      else if (state.activeTab === 'tests') container.innerHTML = renderTestsView();
      else if (state.activeTab === 'papers') container.innerHTML = renderPapersView();
      else if (state.activeTab === 'cheatsheet') container.innerHTML = renderCheatSheetView();
    }

    // =========================================================================
    // 5. TAB 1: STUDY HUB (Visual Interactive Revision Cards)
    // =========================================================================
    function setStudyTopic(topic) {
      playTone('click');
      state.activeStudyTopic = topic;
      renderCurrentView();
    }

    function renderStudyHubView() {
      const topics = [
        { id: 'disasters', label: '1. Disasters & First-Aid', icon: 'fa-house-crack', color: 'bg-rose-600' },
        { id: 'pollution', label: '2. Pollution & Animals', icon: 'fa-earth-americas', color: 'bg-emerald-600' },
        { id: 'wonders', label: '3. 7 Wonders & Countries', icon: 'fa-landmark', color: 'bg-amber-600' },
        { id: 'habits', label: '4. Manners & Hygiene', icon: 'fa-hands-bubbles', color: 'bg-sky-600' },
        { id: 'leadership', label: '5. Leaders & Friends', icon: 'fa-user-group', color: 'bg-indigo-600' }
      ];

      const pills = topics.map(t => {
        const active = state.activeStudyTopic === t.id;
        return `
          <button onclick="setStudyTopic('${t.id}')" class="shrink-0 min-h-[48px] px-4 py-2.5 rounded-2xl font-display font-semibold text-xs sm:text-sm flex items-center gap-2 transition shadow-sm ${active ? `${t.color} text-white scale-[1.02]` : 'bg-white text-slate-700 border border-slate-200 hover:bg-slate-50'}">
            <i class="fa-solid ${t.icon}"></i> ${t.label}
          </button>
        `;
      }).join('');

      let bodyHTML = '';
      if (state.activeStudyTopic === 'disasters') {
        bodyHTML = `
          <div class="space-y-4 animate-pop">
            <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200">
              <h3 class="font-display font-bold text-lg text-mksNavy mb-1">Natural Disasters (Exercise 1 &amp; 5)</h3>
              <p class="text-xs text-slate-600 mb-4">Learn each natural disaster and how to recognize it:</p>
              <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-3">
                <div class="p-3.5 rounded-2xl bg-sky-50 border border-sky-200 text-center">
                  ${getIllustrationSVG('flood')}
                  <div class="font-display font-bold text-base text-sky-950 mt-2">Flood</div>
                  <p class="text-xs text-sky-800 mt-1">Too much water flows over an area from a river or heavy rain.</p>
                </div>
                <div class="p-3.5 rounded-2xl bg-amber-50 border border-amber-200 text-center">
                  ${getIllustrationSVG('earthquake')}
                  <div class="font-display font-bold text-base text-amber-950 mt-2">Earthquake</div>
                  <p class="text-xs text-amber-800 mt-1">The ground under us suddenly starts shaking.</p>
                </div>
                <div class="p-3.5 rounded-2xl bg-slate-100 border border-slate-300 text-center">
                  ${getIllustrationSVG('tornado')}
                  <div class="font-display font-bold text-base text-slate-900 mt-2">Tornado</div>
                  <p class="text-xs text-slate-700 mt-1">A powerful spinning air funnel touching the ground.</p>
                </div>
                <div class="p-3.5 rounded-2xl bg-cyan-50 border border-cyan-200 text-center">
                  ${getIllustrationSVG('tsunami')}
                  <div class="font-display font-bold text-base text-cyan-950 mt-2">Tsunami</div>
                  <p class="text-xs text-cyan-800 mt-1">Giant ocean water waves rushing onto the shore.</p>
                </div>
                <div class="p-3.5 rounded-2xl bg-indigo-50 border border-indigo-200 text-center">
                  ${getIllustrationSVG('avalanche')}
                  <div class="font-display font-bold text-base text-indigo-950 mt-2">Avalanche</div>
                  <p class="text-xs text-indigo-800 mt-1">A huge mass of snow breaking up and sliding down a mountain.</p>
                </div>
                <div class="p-3.5 rounded-2xl bg-rose-50 border border-rose-200 text-center">
                  ${getIllustrationSVG('firstaid')}
                  <div class="font-display font-bold text-base text-rose-950 mt-2">Emergency First-Aid Kit</div>
                  <ul class="text-xs text-rose-900 mt-1 text-left space-y-1">
                    <li>• <strong>Fall/hurt:</strong> Rubbing alcohol</li>
                    <li>• <strong>Light goes off:</strong> Flashlight</li>
                    <li>• <strong>Burned finger:</strong> Bandages</li>
                  </ul>
                </div>
              </div>
            </div>
          </div>
        `;
      } else if (state.activeStudyTopic === 'pollution') {
        bodyHTML = `
          <div class="space-y-4 animate-pop">
            <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200">
              <h3 class="font-display font-bold text-lg text-mksNavy mb-1">Types of Pollution (Exercise 3 &amp; 5)</h3>
              <p class="text-xs text-slate-600 mb-4">Match each picture and cause to Air, Water, or Land pollution:</p>
              <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                <div class="p-4 rounded-2xl bg-slate-100 border border-slate-300 text-center">
                  ${getIllustrationSVG('air_pollution')}
                  <span class="inline-block mt-2 px-3 py-1 rounded-full bg-slate-700 text-white text-xs font-bold">Air Pollution</span>
                  <p class="text-xs text-slate-700 mt-2">Smoke from factory chimneys, cars, and trucks makes the air dirty and hard to breathe.</p>
                </div>
                <div class="p-4 rounded-2xl bg-sky-50 border border-sky-200 text-center">
                  ${getIllustrationSVG('water_pollution')}
                  <span class="inline-block mt-2 px-3 py-1 rounded-full bg-sky-700 text-white text-xs font-bold">Water Pollution</span>
                  <p class="text-xs text-sky-900 mt-2">Dirty pipes pouring waste into rivers and <strong>ships throwing garbage in the sea</strong> harm ducks and fish.</p>
                </div>
                <div class="p-4 rounded-2xl bg-lime-50 border border-lime-300 text-center">
                  ${getIllustrationSVG('land_pollution')}
                  <span class="inline-block mt-2 px-3 py-1 rounded-full bg-lime-700 text-white text-xs font-bold">Land Pollution</span>
                  <p class="text-xs text-lime-950 mt-2">Dumping trash, old machines, and litter on soil and forests ruins nature.</p>
                </div>
              </div>
              <div class="mt-4 p-4 rounded-2xl bg-amber-50 border border-amber-200 flex items-center gap-3">
                <span class="text-2xl">🐼</span>
                <p class="text-xs sm:text-sm text-amber-950"><strong>Endangered Animals:</strong> Pollution and habitat loss put wildlife in danger. An <strong>endangered</strong> animal might not exist after a few years!</p>
              </div>
            </div>
          </div>
        `;
      } else if (state.activeStudyTopic === 'wonders') {
        const cards = wondersList.map(w => `
          <div class="p-3.5 rounded-2xl bg-slate-50 border border-slate-200 text-center">
            ${getIllustrationSVG(w.svg)}
            <div class="font-display font-bold text-base text-mksNavy mt-2">${w.name}</div>
            <div class="inline-block mt-1 px-3 py-1 rounded-full bg-amber-100 text-amber-900 text-xs font-bold">
              <i class="fa-solid fa-location-dot text-rose-600 mr-1"></i>${w.country}
            </div>
          </div>
        `).join('');

        bodyHTML = `
          <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200 animate-pop">
            <h3 class="font-display font-bold text-lg text-mksNavy mb-1">Wonders of the World &amp; Countries (Exercise 4)</h3>
            <p class="text-xs text-slate-600 mb-4">Memorize each famous world wonder and the country where it stands:</p>
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-3">
              ${cards}
            </div>
          </div>
        `;
      } else if (state.activeStudyTopic === 'habits') {
        bodyHTML = `
          <div class="space-y-4 animate-pop">
            <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200">
              <h3 class="font-display font-bold text-lg text-mksNavy mb-3">Good Manners, Hygiene &amp; Healthy Habits (Exercises 6, 7, 10, 11)</h3>
              <div class="grid grid-cols-1 md:grid-cols-2 gap-3 text-xs sm:text-sm">
                <div class="p-4 rounded-2xl bg-emerald-50 border border-emerald-200 space-y-1.5">
                  <div class="font-display font-bold text-base text-emerald-950">✨ Polite “Magic Words” &amp; Manners</div>
                  <p class="text-emerald-900">• Always say <strong>“Sorry”</strong> and <strong>“Excuse me!”</strong></p>
                  <p class="text-emerald-900">• Never take or use classmates’ pencils or toys without <strong>asking permission</strong>, and always <strong>return</strong> them.</p>
                  <p class="text-emerald-900">• A <strong>well-mannered</strong> person does not act in a bad way towards others.</p>
                </div>
                <div class="p-4 rounded-2xl bg-sky-50 border border-sky-200 space-y-1.5">
                  <div class="font-display font-bold text-base text-sky-950">🧼 Personal Hygiene Checklist</div>
                  <p class="text-sky-900">• <strong>After football/sports:</strong> Take off shoes, <strong>take a shower</strong>, and change into clean clothes.</p>
                  <p class="text-sky-900">• <strong>Morning &amp; Bedtime:</strong> Keep hair tidy and <strong>brush your teeth</strong>.</p>
                  <p class="text-sky-900">• <strong>Nails &amp; Bathroom:</strong> Trim and clean nails; turn off the tap and wash hands.</p>
                </div>
                <div class="p-4 rounded-2xl bg-amber-50 border border-amber-200 space-y-1.5 md:col-span-2">
                  <div class="font-display font-bold text-base text-amber-950">⚽ Healthy Body &amp; Clean Environment</div>
                  <p class="text-amber-900">• Eat <strong>healthy foods</strong> to keep your body in good shape, and choose politely when dining with friends.</p>
                  <p class="text-amber-900">• Playing video games for too long makes your body <strong>idle (lazy)</strong> — <strong>practice sports</strong> instead!</p>
                  <p class="text-amber-900">• Before leaving a play area, always make sure it is <strong>clean and neat</strong>.</p>
                </div>
              </div>
            </div>
          </div>
        `;
      } else {
        bodyHTML = `
          <div class="space-y-4 animate-pop">
            <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200 space-y-4">
              <h3 class="font-display font-bold text-lg text-mksNavy">Leaders, Followers &amp; Friendship (Exercises 8, 9, 10, 11)</h3>
              <div class="p-4 rounded-2xl bg-indigo-50 border border-indigo-200 text-xs sm:text-sm space-y-2">
                <div class="font-display font-bold text-base text-indigo-950">📖 Reading Passage Summary: Robin &amp; Samia</div>
                <p class="italic text-indigo-900 bg-white/80 p-3 rounded-xl border border-indigo-100">
                  “Robin does not like to do anything on his own. He asks Samia about everything he wants to do. If Samia tells him to participate in another activity, he does that. Sometimes Samia decides what Robin has to eat too. He never complains.”
                </p>
                <ul class="text-indigo-950 space-y-1">
                  <li>• <strong>Leader (Makes decisions):</strong> Samia</li>
                  <li>• <strong>Follower (Follows choices):</strong> Robin (asks Samia about everything &amp; joins activities she picks)</li>
                  <li>• <strong>Does Robin ever complain?</strong> No!</li>
                  <li>• <strong>Why follow others?</strong> Because you trust your friend’s ideas or feel shy deciding alone.</li>
                </ul>
              </div>

              <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 text-xs sm:text-sm">
                <div class="p-4 rounded-2xl bg-teal-50 border border-teal-200">
                  <div class="font-display font-bold text-base text-teal-950 mb-1">🌟 Good Leader Qualities</div>
                  <p class="text-teal-900">• Listens and shares ideas (never just gives orders or makes fun of others).</p>
                  <p class="text-teal-900 mt-1">• Helps followers and shares things with them.</p>
                </div>
                <div class="p-4 rounded-2xl bg-rose-50 border border-rose-200">
                  <div class="font-display font-bold text-base text-rose-950 mb-1">🤝 Good Friendship Rules</div>
                  <p class="text-rose-900">• Return borrowed books on time, share snacks, help carry heavy books, and congratulate friends when they win.</p>
                  <p class="text-rose-900 mt-1">• Never laugh at mistakes, spread secrets, ignore friends, or blame others.</p>
                </div>
              </div>
            </div>
          </div>
        `;
      }

      return `
        <div class="space-y-4">
          <div class="bg-gradient-to-r from-mksNavy to-teal-900 text-white rounded-3xl p-5 shadow-md">
            <h2 class="font-display font-bold text-xl sm:text-2xl">Social Studies Study Hub</h2>
            <p class="text-xs sm:text-sm text-teal-100 mt-1">Illustrated revision notes covering every exercise in your Year 3 Term 1 worksheet.</p>
          </div>

          <div class="flex gap-2 overflow-x-auto no-scrollbar pb-1">
            ${pills}
          </div>

          ${bodyHTML}

          <div class="pt-1 text-center">
            <button onclick="switchTab('games')" class="min-h-[52px] inline-flex items-center gap-2 bg-amber-400 hover:bg-amber-500 text-mksNavy font-display font-bold px-6 py-3 rounded-2xl shadow-md transition">
              <i class="fa-solid fa-gamepad"></i>
              <span>Play Interactive Revision Games!</span>
            </button>
          </div>
        </div>
      `;
    }

    // =========================================================================
    // 6. TAB 2: ARCADE GAMES (4 Touch-Friendly Interactive Games)
    // =========================================================================
    function selectGame(gameKey) {
      playTone('click');
      state.activeGame = gameKey;
      renderCurrentView();
    }

    // --- GAME 1 LOGIC: Disaster & Emergency Rescue Match ---
    function handleGame1Answer(choice) {
      const g = state.game1;
      if (g.feedback) return;
      const current = disasterScenarios[g.index];
      const isRight = choice === current.answer;
      if (isRight) {
        playTone('correct');
        g.score += 10;
        g.streak++;
        addStars(10);
        g.feedback = { ok: true, msg: `Spot on! That is ${current.answer}! (+10 Stars)` };
      } else {
        playTone('wrong');
        g.streak = 0;
        g.feedback = { ok: false, msg: `Oops! The correct answer is ${current.answer}.` };
      }
      renderCurrentView();
    }

    function nextGame1() {
      playTone('click');
      const g = state.game1;
      g.feedback = null;
      if (g.index + 1 >= disasterScenarios.length) {
        g.finished = true;
      } else {
        g.index++;
      }
      renderCurrentView();
    }

    function resetGame1() {
      playTone('click');
      state.game1 = { index: 0, score: 0, streak: 0, feedback: null, finished: false };
      renderCurrentView();
    }

    // --- GAME 2 LOGIC: Eco-Cleaner Pollution Sorter ---
    function handleGame2Sort(binName) {
      const g = state.game2;
      if (g.feedback) return;
      const current = pollutionCards[g.index];
      if (binName === current.answer) {
        playTone('correct');
        g.score += 10;
        g.streak++;
        addStars(10);
        g.feedback = { ok: true, msg: `Clean-up hero! Sorted into ${binName}! (+10 Stars)` };
      } else {
        playTone('wrong');
        g.streak = 0;
        g.feedback = { ok: false, msg: `Not quite! That scene belongs to ${current.answer}.` };
      }
      renderCurrentView();
    }

    function nextGame2() {
      playTone('click');
      const g = state.game2;
      g.feedback = null;
      if (g.index + 1 >= pollutionCards.length) g.finished = true;
      else g.index++;
      renderCurrentView();
    }

    function resetGame2() {
      playTone('click');
      state.game2 = { index: 0, score: 0, streak: 0, feedback: null, finished: false };
      renderCurrentView();
    }

    // --- GAME 3 LOGIC: World Wonders Passport Explorer ---
    function tapWonderCard(wId) {
      const g = state.game3;
      if (g.matchedIds.includes(wId)) return;
      playTone('click');
      g.selectedWonder = wId;
      g.wrongPair = null;
      renderCurrentView();
    }

    function tapCountryCard(countryName) {
      const g = state.game3;
      if (!g.selectedWonder) {
        showToast('First tap a World Wonder card on the left/top!', '🏛️');
        return;
      }
      const wonder = wondersList.find(w => w.id === g.selectedWonder);
      if (wonder && wonder.country === countryName) {
        playTone('correct');
        g.matchedIds.push(wonder.id);
        g.selectedWonder = null;
        g.wrongPair = null;
        g.score += 15;
        addStars(15);
        showToast(`Passport Stamped! ${wonder.name} → ${countryName} (+15 Stars)`, '🛂');
      } else {
        playTone('wrong');
        g.wrongPair = countryName;
        showToast(`Try again! ${wonder.name} is not in ${countryName}.`, '❌');
      }
      renderCurrentView();
    }

    function resetGame3() {
      playTone('click');
      state.game3 = { selectedWonder: null, matchedIds: [], wrongPair: null, score: 0 };
      renderCurrentView();
    }

    // --- GAME 4 LOGIC: Manners & Friendship Star Sorter + Word Bank ---
    function setGame4SubMode(mode) {
      playTone('click');
      state.game4.subMode = mode;
      renderCurrentView();
    }

    function colorStarChoice(choseGreen) {
      const g = state.game4;
      if (g.starFeedback) return;
      const item = starScenarios[g.starIndex];
      if (choseGreen === item.isGood) {
        playTone('correct');
        g.starScore += 10;
        addStars(10);
        g.starFeedback = { ok: true, color: choseGreen ? 'green' : 'red', msg: `Great job! ${item.reason} (+10 Stars)` };
      } else {
        playTone('wrong');
        g.starFeedback = { ok: false, color: item.isGood ? 'green' : 'red', msg: `Careful! ${item.reason}` };
      }
      renderCurrentView();
    }

    function nextStarScenario() {
      playTone('click');
      const g = state.game4;
      g.starFeedback = null;
      g.starIndex = (g.starIndex + 1) % starScenarios.length;
      renderCurrentView();
    }

    function setBlankAnswer(blankKey, val) {
      playTone('click');
      state.game4.blankAnswers[blankKey] = val;
      state.game4.blankChecked = false;
      renderCurrentView();
    }

    function checkEx6Blanks() {
      const ans = state.game4.blankAnswers;
      if (!ans.b1 || !ans.b2 || !ans.b3 || !ans.b4 || !ans.b5) {
        showToast('Please select a word from the word bank for all 5 blanks!', '✏️');
        return;
      }
      state.game4.blankChecked = true;
      const correctMap = { b1: 'asking', b2: 'help', b3: 'permission', b4: 'return', b5: 'parent' };
      let right = 0;
      Object.keys(correctMap).forEach(k => { if (ans[k] === correctMap[k]) right++; });
      if (right === 5) {
        playTone('correct');
        addStars(25, 'ex6_blanks_mastered');
        showToast('All 5 blanks are 100% correct! +25 Stars!', '🌟');
      } else {
        playTone('wrong');
        showToast(`You got ${right}/5 right! Check the highlighted boxes.`, '💡');
      }
      renderCurrentView();
    }

    function renderGamesView() {
      const gameTabs = [
        { id: 'disaster', label: '1. Disaster Rescue', icon: 'fa-truck-medical' },
        { id: 'pollution', label: '2. Pollution Sorter', icon: 'fa-recycle' },
        { id: 'wonders', label: '3. Wonders Passport', icon: 'fa-earth-asia' },
        { id: 'manners', label: '4. Star Sorter & Word Bank', icon: 'fa-star' }
      ];

      const selectorHTML = gameTabs.map(gt => {
        const active = state.activeGame === gt.id;
        return `
          <button onclick="selectGame('${gt.id}')" class="shrink-0 min-h-[48px] px-4 py-2.5 rounded-2xl font-display font-semibold text-xs sm:text-sm flex items-center gap-2 transition ${active ? 'bg-mksNavy text-amber-300 shadow-md' : 'bg-white text-slate-700 border border-slate-200 hover:bg-slate-50'}">
            <i class="fa-solid ${gt.icon}"></i> ${gt.label}
          </button>
        `;
      }).join('');

      let gameArea = '';

      // --- RENDER GAME 1 ---
      if (state.activeGame === 'disaster') {
        const g = state.game1;
        if (g.finished) {
          gameArea = `
            <div class="bg-white rounded-3xl p-6 text-center shadow-sm border border-slate-200 space-y-4 animate-pop">
              <div class="text-5xl">🚒🏆</div>
              <h3 class="font-display font-bold text-2xl text-mksNavy">Disaster Rescue Complete!</h3>
              <p class="text-sm text-slate-600">You scored <strong class="text-mksTeal text-lg">${g.score} points</strong>!</p>
              <button onclick="resetGame1()" class="min-h-[50px] px-6 py-3 rounded-2xl bg-amber-400 hover:bg-amber-500 text-mksNavy font-display font-bold shadow">
                <i class="fa-solid fa-rotate-right mr-1.5"></i> Play Again
              </button>
            </div>
          `;
        } else {
          const item = disasterScenarios[g.index];
          const opts = item.options.map(opt => {
            let cls = 'bg-slate-50 hover:bg-rose-50 border-slate-200 text-slate-800';
            if (g.feedback) {
              if (opt === item.answer) cls = 'bg-emerald-100 border-emerald-500 text-emerald-950 font-bold';
              else cls = 'bg-slate-50 border-slate-200 opacity-60';
            }
            return `
              <button ${g.feedback ? 'disabled' : ''} onclick="handleGame1Answer('${opt.replace(/'/g, "\\'")}')" class="min-h-[50px] p-3.5 rounded-2xl border-2 font-display font-semibold text-sm sm:text-base transition ${cls}">
                ${opt}
              </button>
            `;
          }).join('');

          gameArea = `
            <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200 space-y-4 animate-pop">
              <div class="flex items-center justify-between text-xs font-bold">
                <span class="px-3 py-1 rounded-full bg-rose-100 text-rose-800">Round ${g.index + 1} / ${disasterScenarios.length}</span>
                <span class="px-3 py-1 rounded-full bg-amber-100 text-amber-900">🔥 Streak: ${g.streak} • Score: ${g.score}</span>
              </div>
              <div class="text-center space-y-3 py-2">
                ${getIllustrationSVG(item.svg)}
                <p class="font-display font-bold text-lg sm:text-xl text-mksNavy">${item.prompt}</p>
              </div>
              <div class="grid grid-cols-1 sm:grid-cols-2 gap-2.5">${opts}</div>
              ${g.feedback ? `
                <div class="p-4 rounded-2xl ${g.feedback.ok ? 'bg-emerald-50 border border-emerald-300 text-emerald-900' : 'bg-rose-50 border border-rose-300 text-rose-900'} flex flex-col sm:flex-row items-center justify-between gap-3">
                  <span class="font-semibold text-sm">${g.feedback.msg}</span>
                  <button onclick="nextGame1()" class="w-full sm:w-auto min-h-[48px] px-5 py-2.5 rounded-xl bg-mksNavy text-white font-display font-bold text-sm">
                    Next Round <i class="fa-solid fa-arrow-right ml-1"></i>
                  </button>
                </div>
              ` : ''}
            </div>
          `;
        }
      }

      // --- RENDER GAME 2 ---
      else if (state.activeGame === 'pollution') {
        const g = state.game2;
        if (g.finished) {
          gameArea = `
            <div class="bg-white rounded-3xl p-6 text-center shadow-sm border border-slate-200 space-y-4 animate-pop">
              <div class="text-5xl">🌍♻️</div>
              <h3 class="font-display font-bold text-2xl text-mksNavy">Planet Eco-Cleaner Champion!</h3>
              <p class="text-sm text-slate-600">You sorted every pollution scene and earned <strong class="text-emerald-700 text-lg">${g.score} points</strong>!</p>
              <button onclick="resetGame2()" class="min-h-[50px] px-6 py-3 rounded-2xl bg-emerald-600 text-white font-display font-bold shadow">
                <i class="fa-solid fa-rotate-right mr-1.5"></i> Sort Again
              </button>
            </div>
          `;
        } else {
          const item = pollutionCards[g.index];
          gameArea = `
            <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200 space-y-4 animate-pop">
              <div class="flex items-center justify-between text-xs font-bold">
                <span class="px-3 py-1 rounded-full bg-emerald-100 text-emerald-800">Card ${g.index + 1} / ${pollutionCards.length}</span>
                <span class="px-3 py-1 rounded-full bg-amber-100 text-amber-900">Score: ${g.score}</span>
              </div>
              <div class="bg-slate-50 rounded-2xl p-4 border border-slate-200 text-center space-y-3">
                ${getIllustrationSVG(item.svg)}
                <p class="font-semibold text-base sm:text-lg text-mksNavy">${item.title}</p>
                <p class="text-xs text-slate-500">Tap the matching pollution bin below:</p>
              </div>
              <div class="grid grid-cols-1 sm:grid-cols-3 gap-3">
                <button ${g.feedback ? 'disabled' : ''} onclick="handleGame2Sort('Air pollution')" class="min-h-[56px] p-3.5 rounded-2xl bg-slate-700 hover:bg-slate-800 text-white font-display font-bold text-sm flex items-center justify-center gap-2 shadow">
                  <i class="fa-solid fa-smog"></i> Air Pollution
                </button>
                <button ${g.feedback ? 'disabled' : ''} onclick="handleGame2Sort('Water pollution')" class="min-h-[56px] p-3.5 rounded-2xl bg-sky-600 hover:bg-sky-700 text-white font-display font-bold text-sm flex items-center justify-center gap-2 shadow">
                  <i class="fa-solid fa-water"></i> Water Pollution
                </button>
                <button ${g.feedback ? 'disabled' : ''} onclick="handleGame2Sort('Land pollution')" class="min-h-[56px] p-3.5 rounded-2xl bg-lime-600 hover:bg-lime-700 text-white font-display font-bold text-sm flex items-center justify-center gap-2 shadow">
                  <i class="fa-solid fa-trash-can"></i> Land Pollution
                </button>
              </div>
              ${g.feedback ? `
                <div class="p-4 rounded-2xl ${g.feedback.ok ? 'bg-emerald-50 border border-emerald-300 text-emerald-900' : 'bg-rose-50 border border-rose-300 text-rose-900'} flex flex-col sm:flex-row items-center justify-between gap-3">
                  <span class="font-semibold text-sm">${g.feedback.msg}</span>
                  <button onclick="nextGame2()" class="w-full sm:w-auto min-h-[48px] px-5 py-2.5 rounded-xl bg-mksNavy text-white font-display font-bold text-sm">
                    Next Card <i class="fa-solid fa-arrow-right ml-1"></i>
                  </button>
                </div>
              ` : ''}
            </div>
          `;
        }
      }

      // --- RENDER GAME 3 ---
      else if (state.activeGame === 'wonders') {
        const g = state.game3;
        const allMatched = g.matchedIds.length === wondersList.length;
        const countriesOrder = ['Greece', 'Jordan', 'Italy', 'Egypt', 'Iraq', 'China'];

        const wonderBtns = wondersList.map(w => {
          const matched = g.matchedIds.includes(w.id);
          const selected = g.selectedWonder === w.id;
          return `
            <button ${matched ? 'disabled' : ''} onclick="tapWonderCard('${w.id}')" class="p-3 rounded-2xl border-2 text-left transition flex items-center gap-3 min-h-[60px] ${matched ? 'bg-emerald-50 border-emerald-400 opacity-75' : selected ? 'bg-amber-100 border-amber-500 ring-2 ring-amber-400/40' : 'bg-white border-slate-200 hover:border-amber-400'}">
              <div class="w-14 shrink-0">${getIllustrationSVG(w.svg).replace('w-44 h-28', 'w-14 h-10')}</div>
              <div class="flex-1">
                <div class="font-display font-bold text-xs sm:text-sm text-mksNavy">${w.name}</div>
                ${matched ? `<div class="text-[11px] font-bold text-emerald-700">✓ ${w.country}</div>` : `<div class="text-[11px] text-slate-500">${selected ? 'Now tap its country!' : 'Tap to select'}</div>`}
              </div>
            </button>
          `;
        }).join('');

        const countryBtns = countriesOrder.map(c => {
          const matchedObj = wondersList.find(w => w.country === c && g.matchedIds.includes(w.id));
          const isWrong = g.wrongPair === c;
          return `
            <button ${matchedObj ? 'disabled' : ''} onclick="tapCountryCard('${c}')" class="min-h-[56px] p-3.5 rounded-2xl border-2 font-display font-bold text-sm sm:text-base transition flex items-center justify-center gap-2 ${matchedObj ? 'bg-emerald-600 border-emerald-600 text-white' : isWrong ? 'bg-rose-100 border-rose-500 text-rose-900 shake-wrong' : 'bg-indigo-50 hover:bg-indigo-100 border-indigo-200 text-indigo-950'}">
              <i class="fa-solid ${matchedObj ? 'fa-circle-check' : 'fa-flag'}"></i>
              <span>${c}</span>
            </button>
          `;
        }).join('');

        gameArea = `
          <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200 space-y-4 animate-pop">
            <div class="flex items-center justify-between">
              <div>
                <h3 class="font-display font-bold text-lg text-mksNavy">World Wonders Passport Matcher</h3>
                <p class="text-xs text-slate-600">Step 1: Tap a Wonder • Step 2: Tap its Country!</p>
              </div>
              <span class="px-3 py-1 rounded-full bg-amber-100 text-amber-900 text-xs font-bold">${g.matchedIds.length}/6 Matched</span>
            </div>

            ${allMatched ? `
              <div class="p-5 rounded-2xl bg-emerald-50 border border-emerald-300 text-center space-y-3">
                <div class="text-4xl">🛂🎉</div>
                <div class="font-display font-bold text-xl text-emerald-950">All 6 World Wonders Matched!</div>
                <button onclick="resetGame3()" class="min-h-[48px] px-5 py-2.5 rounded-xl bg-mksNavy text-white font-display font-bold text-sm">Play Again</button>
              </div>
            ` : `
              <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                <div class="space-y-2">
                  <div class="text-xs font-bold uppercase text-slate-500">1. Famous Wonders</div>
                  <div class="grid grid-cols-1 gap-2">${wonderBtns}</div>
                </div>
                <div class="space-y-2">
                  <div class="text-xs font-bold uppercase text-slate-500">2. Countries</div>
                  <div class="grid grid-cols-2 gap-2.5">${countryBtns}</div>
                </div>
              </div>
            `}
          </div>
        `;
      }

      // --- RENDER GAME 4 (Exercise 6 & 9 Star Sorter + Word Bank) ---
      else {
        const g = state.game4;
        const item = starScenarios[g.starIndex];
        const starFill = !g.starFeedback ? '#e2e8f0' : g.starFeedback.color === 'green' ? '#16a34a' : '#e11d48';
        const wordBank = ['help', 'permission', 'return', 'parent', 'asking'];

        const renderSelect = (key) => {
          const val = g.blankAnswers[key] || '';
          const correctMap = { b1: 'asking', b2: 'help', b3: 'permission', b4: 'return', b5: 'parent' };
          let borderCls = 'border-indigo-300 bg-indigo-50 text-mksNavy';
          if (g.blankChecked) {
            borderCls = val === correctMap[key] ? 'border-emerald-500 bg-emerald-100 text-emerald-950' : 'border-rose-500 bg-rose-100 text-rose-950';
          }
          const options = wordBank.map(w => `<option value="${w}" ${val === w ? 'selected' : ''}>${w}</option>`).join('');
          return `
            <select onchange="setBlankAnswer('${key}', this.value)" class="inline-block min-h-[40px] px-2.5 py-1 rounded-xl border-2 font-bold text-sm ${borderCls}">
              <option value="">-- choose --</option>
              ${options}
            </select>
          `;
        };

        gameArea = `
          <div class="space-y-4 animate-pop">
            <div class="flex gap-2">
              <button onclick="setGame4SubMode('stars')" class="flex-1 min-h-[48px] py-2.5 px-3 rounded-2xl font-display font-bold text-xs sm:text-sm border-2 transition ${g.subMode === 'stars' ? 'bg-emerald-600 border-emerald-600 text-white' : 'bg-white border-slate-200 text-slate-700'}">
                ⭐ Colour the Star (Green / Red)
              </button>
              <button onclick="setGame4SubMode('blanks')" class="flex-1 min-h-[48px] py-2.5 px-3 rounded-2xl font-display font-bold text-xs sm:text-sm border-2 transition ${g.subMode === 'blanks' ? 'bg-indigo-600 border-indigo-600 text-white' : 'bg-white border-slate-200 text-slate-700'}">
                ✏️ Exercise 6 Word Bank
              </button>
            </div>

            ${g.subMode === 'stars' ? `
              <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200 space-y-4 text-center">
                <div class="flex justify-between text-xs font-bold">
                  <span class="px-3 py-1 rounded-full bg-slate-100 text-slate-700">Scenario ${g.starIndex + 1} / ${starScenarios.length}</span>
                  <span class="px-3 py-1 rounded-full bg-amber-100 text-amber-900">Star Score: ${g.starScore}</span>
                </div>

                <svg viewBox="0 0 120 115" class="w-28 h-28 mx-auto drop-shadow">
                  <polygon points="60,8 75,40 110,45 85,70 91,105 60,88 29,105 35,70 10,45 45,40" fill="${starFill}" stroke="#0f294a" stroke-width="4" stroke-linejoin="round"/>
                </svg>

                <p class="font-display font-bold text-base sm:text-lg text-mksNavy max-w-xl mx-auto">“${item.text}”</p>

                <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 max-w-lg mx-auto">
                  <button ${g.starFeedback ? 'disabled' : ''} onclick="colorStarChoice(true)" class="min-h-[56px] p-3.5 rounded-2xl bg-emerald-600 hover:bg-emerald-700 text-white font-display font-bold text-sm sm:text-base shadow">
                    🟢 Colour Star GREEN<br><span class="text-xs font-normal opacity-90">(Well-Mannered / Good Friend)</span>
                  </button>
                  <button ${g.starFeedback ? 'disabled' : ''} onclick="colorStarChoice(false)" class="min-h-[56px] p-3.5 rounded-2xl bg-rose-600 hover:bg-rose-700 text-white font-display font-bold text-sm sm:text-base shadow">
                    🔴 Colour Star RED<br><span class="text-xs font-normal opacity-90">(Not Well-Mannered)</span>
                  </button>
                </div>

                ${g.starFeedback ? `
                  <div class="p-4 rounded-2xl ${g.starFeedback.ok ? 'bg-emerald-50 border border-emerald-300 text-emerald-950' : 'bg-rose-50 border border-rose-300 text-rose-950'} space-y-3">
                    <p class="font-semibold text-sm">${g.starFeedback.msg}</p>
                    <button onclick="nextStarScenario()" class="min-h-[48px] px-6 py-2.5 rounded-xl bg-mksNavy text-white font-display font-bold text-sm">
                      Next Scenario <i class="fa-solid fa-arrow-right ml-1"></i>
                    </button>
                  </div>
                ` : ''}
              </div>
            ` : `
              <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200 space-y-4">
                <div>
                  <h3 class="font-display font-bold text-lg text-mksNavy">Exercise 6: Fill in the Blanks</h3>
                  <p class="text-xs text-slate-600">Word Bank: <strong>help • permission • return • parent • asking</strong></p>
                </div>
                <div class="space-y-3 text-sm sm:text-base leading-relaxed text-slate-800">
                  <div class="p-3 rounded-2xl bg-slate-50 border border-slate-200">
                    1. Layla took Samir’s pencil and kept it without ${renderSelect('b1')}.
                  </div>
                  <div class="p-3 rounded-2xl bg-slate-50 border border-slate-200">
                    2. Omar couldn’t solve a problem in class. Leila stayed after school to ${renderSelect('b2')} him.
                  </div>
                  <div class="p-3 rounded-2xl bg-slate-50 border border-slate-200">
                    3. Tamer always uses his classmates’ toys without ${renderSelect('b3')} and never ${renderSelect('b4')} them.
                  </div>
                  <div class="p-3 rounded-2xl bg-slate-50 border border-slate-200">
                    4. Noor asked, “May I please use your phone to call my ${renderSelect('b5')}?” before asking.
                  </div>
                </div>
                <button onclick="checkEx6Blanks()" class="w-full sm:w-auto min-h-[52px] px-6 py-3 rounded-2xl bg-emerald-600 hover:bg-emerald-700 text-white font-display font-bold text-sm sm:text-base shadow">
                  <i class="fa-solid fa-check-double mr-1.5"></i> Check My Answers
                </button>
              </div>
            `}
          </div>
        `;
      }

      return `
        <div class="space-y-4">
          <div class="bg-gradient-to-r from-indigo-900 via-mksNavy to-teal-900 text-white rounded-3xl p-5 shadow-md">
            <h2 class="font-display font-bold text-xl sm:text-2xl">Social Studies Learning Arcade</h2>
            <p class="text-xs sm:text-sm text-amber-200 mt-1">Play 4 interactive games based on your worksheet and earn bonus Stars!</p>
          </div>

          <div class="flex gap-2 overflow-x-auto no-scrollbar pb-1">
            ${selectorHTML}
          </div>

          ${gameArea}
        </div>
      `;
    }

    // =========================================================================
    // 7. TAB 3: SELF-CORRECTING TESTS (Exercises 1–11)
    // =========================================================================
    const testUserAnswers = {};
    const testHintsVisible = {};

    function setTestFilter(topic) {
      playTone('click');
      state.activeTestTopic = topic;
      renderCurrentView();
    }

    function answerTestQuestion(qId, optIdx) {
      const q = testQuestions.find(item => item.id === qId);
      if (!q) return;
      const chosen = q.options[optIdx];
      testUserAnswers[qId] = chosen;
      if (chosen === q.answer) {
        playTone('correct');
        const already = !!state.solvedTests[qId];
        addStars(10, qId);
        if (!already) showToast('Correct! +10 Stars earned!', '⭐');
      } else {
        playTone('wrong');
      }
      renderCurrentView();
    }

    function toggleTestHint(qId) {
      playTone('click');
      testHintsVisible[qId] = !testHintsVisible[qId];
      renderCurrentView();
    }

    function renderTestsView() {
      const filters = [
        { id: 'all', label: 'All Exercises (21)' },
        { id: 'disasters', label: 'Disasters & Safety' },
        { id: 'pollution', label: 'Pollution' },
        { id: 'wonders', label: 'World Wonders' },
        { id: 'habits', label: 'Manners & Hygiene' },
        { id: 'leadership', label: 'Robin & Samia / Friends' }
      ];

      const filtered = state.activeTestTopic === 'all'
        ? testQuestions
        : testQuestions.filter(q => q.topic === state.activeTestTopic);

      const solvedCount = filtered.filter(q => state.solvedTests[q.id]).length;

      const filterPills = filters.map(f => {
        const active = state.activeTestTopic === f.id;
        return `
          <button onclick="setTestFilter('${f.id}')" class="shrink-0 min-h-[44px] px-4 py-2 rounded-2xl font-display font-semibold text-xs sm:text-sm transition ${active ? 'bg-mksTeal text-white shadow-sm' : 'bg-white text-slate-700 border border-slate-200 hover:bg-slate-50'}">
            ${f.label}
          </button>
        `;
      }).join('');

      const cards = filtered.map((q, idx) => {
        const chosen = testUserAnswers[q.id];
        const isCorrect = chosen === q.answer;
        const isWrong = chosen && chosen !== q.answer;
        const mastered = !!state.solvedTests[q.id];

        const optsHTML = q.options.map((opt, oIdx) => {
          let cls = 'bg-slate-50 hover:bg-teal-50/70 border-slate-200 text-slate-800';
          let badge = `<span class="w-7 h-7 rounded-lg bg-white border border-slate-300 flex items-center justify-center text-xs font-bold shrink-0">${String.fromCharCode(65 + oIdx)}</span>`;
          if (chosen === opt) {
            if (opt === q.answer) {
              cls = 'bg-emerald-50 border-emerald-500 text-emerald-950 ring-2 ring-emerald-500/20 font-bold';
              badge = `<span class="w-7 h-7 rounded-lg bg-emerald-600 text-white flex items-center justify-center text-xs font-bold shrink-0"><i class="fa-solid fa-check"></i></span>`;
            } else {
              cls = 'bg-rose-50 border-rose-500 text-rose-950 ring-2 ring-rose-500/20';
              badge = `<span class="w-7 h-7 rounded-lg bg-rose-600 text-white flex items-center justify-center text-xs font-bold shrink-0"><i class="fa-solid fa-xmark"></i></span>`;
            }
          } else if (isWrong && opt === q.answer) {
            cls = 'bg-emerald-50/70 border-emerald-400 text-emerald-900';
          }
          return `
            <button onclick="answerTestQuestion('${q.id}', ${oIdx})" class="w-full min-h-[50px] text-left p-3.5 rounded-2xl border-2 transition flex items-center gap-3 text-sm sm:text-base ${cls}">
              ${badge}
              <span>${opt}</span>
            </button>
          `;
        }).join('');

        return `
          <div class="bg-white rounded-3xl p-5 shadow-sm border ${mastered ? 'border-emerald-200' : 'border-slate-200'} space-y-3">
            <div class="flex flex-wrap items-center justify-between gap-2">
              <span class="text-xs font-bold uppercase tracking-wider px-2.5 py-1 rounded-lg bg-slate-100 text-slate-600">Q${idx + 1} • ${q.exLabel}</span>
              <div class="flex items-center gap-2">
                ${mastered ? `<span class="text-xs font-bold text-emerald-700 bg-emerald-100 px-2.5 py-1 rounded-full"><i class="fa-solid fa-star text-amber-500 mr-1"></i>Mastered</span>` : ''}
                <button onclick="toggleTestHint('${q.id}')" class="min-h-[36px] text-xs font-semibold text-indigo-700 bg-indigo-50 px-3 py-1 rounded-lg">
                  <i class="fa-regular fa-lightbulb mr-1"></i>Hint
                </button>
              </div>
            </div>

            <p class="font-semibold text-base sm:text-lg text-mksNavy leading-snug">${q.prompt}</p>
            ${q.svg ? `<div class="py-1">${getIllustrationSVG(q.svg)}</div>` : ''}

            ${testHintsVisible[q.id] ? `
              <div class="p-3 rounded-2xl bg-amber-50 border border-amber-200 text-xs sm:text-sm text-amber-950">
                <strong>💡 Hint:</strong> ${q.hint}
              </div>
            ` : ''}

            <div class="space-y-2.5">${optsHTML}</div>

            ${chosen ? `
              <div class="p-3.5 rounded-2xl ${isCorrect ? 'bg-emerald-50 border border-emerald-200 text-emerald-950' : 'bg-rose-50 border border-rose-200 text-rose-950'} text-xs sm:text-sm animate-pop">
                <div class="font-bold mb-0.5">${isCorrect ? '🎉 Correct! Well done!' : '❌ Not quite — check why:'}</div>
                <p>${q.explanation}</p>
              </div>
            ` : ''}
          </div>
        `;
      }).join('');

      return `
        <div class="space-y-4">
          <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200 flex flex-col sm:flex-row sm:items-center justify-between gap-4">
            <div>
              <h2 class="font-display font-bold text-xl text-mksNavy">Self-Correcting Practice Tests</h2>
              <p class="text-xs sm:text-sm text-slate-600">Covers Exercises 1 to 11 with instant correction, hints, and explanations.</p>
            </div>
            <div class="bg-teal-50 border border-teal-200 px-4 py-2.5 rounded-2xl text-center shrink-0">
              <div class="text-xs font-semibold text-teal-800">Mastered</div>
              <div class="font-display font-bold text-lg text-mksNavy">${solvedCount} / ${filtered.length}</div>
            </div>
          </div>

          <div class="flex gap-2 overflow-x-auto no-scrollbar pb-1">${filterPills}</div>
          <div class="space-y-4">${cards}</div>
        </div>
      `;
    }

    // =========================================================================
    // 8. TAB 4: PAST PAPERS SIMULATOR (Untimed / Timed + Auto-Grading)
    // =========================================================================
    function startPaper(paperId, timed = false) {
      playTone('click');
      const paper = pastPapers[paperId];
      if (!paper) return;
      state.activePaperId = paperId;
      state.paperAnswers = {};
      state.paperSubmitted = false;
      state.paperTimed = timed;
      state.timerSeconds = paper.minutes * 60;

      clearInterval(state.timerInterval);
      if (timed) {
        state.timerInterval = setInterval(() => {
          state.timerSeconds--;
          const disp = document.getElementById('paperTimerDisp');
          if (disp) disp.textContent = formatTime(state.timerSeconds);
          if (state.timerSeconds <= 0) {
            clearInterval(state.timerInterval);
            submitPaper(true);
          }
        }, 1000);
      }
      renderCurrentView();
      window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    function formatTime(sec) {
      const m = Math.floor(Math.max(0, sec) / 60);
      const s = Math.max(0, sec) % 60;
      return `${m}:${s < 10 ? '0' : ''}${s}`;
    }

    function selectPaperChoice(qId, optIdx) {
      if (state.paperSubmitted) return;
      const paper = pastPapers[state.activePaperId];
      const q = paper.questions.find(item => item.id === qId);
      if (!q) return;
      playTone('click');
      state.paperAnswers[qId] = q.options[optIdx];
      renderCurrentView();
    }

    function submitPaper(autoTimeOut = false) {
      const paper = pastPapers[state.activePaperId];
      if (!paper) return;
      const answered = Object.keys(state.paperAnswers).length;
      if (!autoTimeOut && answered < paper.questions.length) {
        showToast(`Please answer all questions first (${paper.questions.length - answered} remaining).`, '📝');
        return;
      }
      clearInterval(state.timerInterval);
      state.paperSubmitted = true;

      let score = 0;
      paper.questions.forEach(q => { if (state.paperAnswers[q.id] === q.answer) score++; });
      const bonus = score * 15;
      addStars(bonus, `ss_paper_${paper.id}_${Date.now()}`);
      playTone('correct');
      showToast(`Exam Marked! Score: ${score}/${paper.questions.length} (+${bonus} Stars!)`, '🏆');
      renderCurrentView();
      window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    function exitPaper() {
      clearInterval(state.timerInterval);
      state.activePaperId = null;
      state.paperSubmitted = false;
      renderCurrentView();
    }

    function renderPapersView() {
      if (!state.activePaperId) {
        return `
          <div class="space-y-5 animate-pop">
            <div class="bg-gradient-to-r from-mksNavy to-indigo-900 text-white rounded-3xl p-5 shadow-md">
              <h2 class="font-display font-bold text-xl sm:text-2xl">Term 1 Past Paper Simulator</h2>
              <p class="text-xs sm:text-sm text-sky-200 mt-1">Take full mock exams on mobile or desktop with automatic grading and topic breakdown.</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
              <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200 flex flex-col justify-between space-y-4">
                <div>
                  <span class="inline-block px-3 py-1 rounded-full bg-amber-100 text-amber-800 text-xs font-bold mb-2">Past Paper 1</span>
                  <h3 class="font-display font-bold text-lg text-mksNavy">${pastPapers.paper1.title}</h3>
                  <p class="text-xs text-slate-600 mt-1">${pastPapers.paper1.subtitle}</p>
                </div>
                <div class="grid grid-cols-2 gap-2.5 pt-2">
                  <button onclick="startPaper('paper1', false)" class="min-h-[50px] py-3 px-3 rounded-2xl bg-mksTeal hover:bg-teal-700 text-white font-display font-bold text-xs sm:text-sm shadow">
                    <i class="fa-solid fa-play mr-1"></i> Untimed Mode
                  </button>
                  <button onclick="startPaper('paper1', true)" class="min-h-[50px] py-3 px-3 rounded-2xl bg-amber-400 hover:bg-amber-500 text-mksNavy font-display font-bold text-xs sm:text-sm shadow">
                    <i class="fa-solid fa-stopwatch mr-1"></i> Timed (25m)
                  </button>
                </div>
              </div>

              <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200 flex flex-col justify-between space-y-4">
                <div>
                  <span class="inline-block px-3 py-1 rounded-full bg-indigo-100 text-indigo-800 text-xs font-bold mb-2">Past Paper 2</span>
                  <h3 class="font-display font-bold text-lg text-mksNavy">${pastPapers.paper2.title}</h3>
                  <p class="text-xs text-slate-600 mt-1">${pastPapers.paper2.subtitle}</p>
                </div>
                <div class="grid grid-cols-2 gap-2.5 pt-2">
                  <button onclick="startPaper('paper2', false)" class="min-h-[50px] py-3 px-3 rounded-2xl bg-mksTeal hover:bg-teal-700 text-white font-display font-bold text-xs sm:text-sm shadow">
                    <i class="fa-solid fa-play mr-1"></i> Untimed Mode
                  </button>
                  <button onclick="startPaper('paper2', true)" class="min-h-[50px] py-3 px-3 rounded-2xl bg-amber-400 hover:bg-amber-500 text-mksNavy font-display font-bold text-xs sm:text-sm shadow">
                    <i class="fa-solid fa-stopwatch mr-1"></i> Timed (20m)
                  </button>
                </div>
              </div>
            </div>
          </div>
        `;
      }

      const paper = pastPapers[state.activePaperId];
      const total = paper.questions.length;
      const answeredCount = Object.keys(state.paperAnswers).length;

      let reportHTML = '';
      if (state.paperSubmitted) {
        let correct = 0;
        const byTopic = {};
        paper.questions.forEach(q => {
          if (!byTopic[q.topic]) byTopic[q.topic] = { total: 0, right: 0 };
          byTopic[q.topic].total++;
          if (state.paperAnswers[q.id] === q.answer) {
            correct++;
            byTopic[q.topic].right++;
          }
        });
        const pct = Math.round((correct / total) * 100);
        const badge = pct >= 85 ? 'Gold Star Scholar! 🌟' : pct >= 65 ? 'Silver Medal Effort! 👍' : 'Keep Reviewing! 💪';

        const bars = Object.entries(byTopic).map(([t, st]) => {
          const tPct = Math.round((st.right / st.total) * 100);
          return `
            <div class="bg-white/10 rounded-2xl p-3">
              <div class="flex justify-between text-xs font-bold mb-1">
                <span>${t}</span>
                <span>${st.right}/${st.total} (${tPct}%)</span>
              </div>
              <div class="w-full h-2 bg-white/20 rounded-full overflow-hidden">
                <div class="h-full bg-amber-400 rounded-full" style="width: ${tPct}%"></div>
              </div>
            </div>
          `;
        }).join('');

        reportHTML = `
          <div class="bg-gradient-to-br from-mksNavy to-teal-950 text-white rounded-3xl p-6 shadow-lg space-y-4 animate-pop">
            <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-4 border-b border-white/15 pb-4">
              <div>
                <span class="text-xs font-bold uppercase tracking-wider text-amber-300">Auto-Graded Exam Report</span>
                <h3 class="font-display font-bold text-2xl mt-0.5">${badge}</h3>
                <p class="text-xs text-teal-200 mt-1">Review your answers vs the official marking scheme below.</p>
              </div>
              <div class="bg-white text-mksNavy rounded-2xl px-5 py-3 text-center shrink-0">
                <div class="font-display font-bold text-3xl text-mksTeal">${correct} / ${total}</div>
                <div class="text-xs font-bold text-slate-500">Score: ${pct}%</div>
              </div>
            </div>
            <div class="grid grid-cols-1 sm:grid-cols-2 gap-2.5">${bars}</div>
            <div class="flex flex-wrap gap-2 pt-1 no-print">
              <button onclick="startPaper('${paper.id}', ${state.paperTimed})" class="min-h-[46px] px-4 py-2 rounded-xl bg-amber-400 text-mksNavy font-display font-bold text-xs sm:text-sm">
                <i class="fa-solid fa-rotate-right mr-1"></i> Retake Paper
              </button>
              <button onclick="window.print()" class="min-h-[46px] px-4 py-2 rounded-xl bg-white/15 hover:bg-white/25 text-white font-display font-semibold text-xs sm:text-sm">
                <i class="fa-solid fa-print mr-1"></i> Print Results
              </button>
              <button onclick="exitPaper()" class="min-h-[46px] px-4 py-2 rounded-xl bg-white/15 hover:bg-white/25 text-white font-display font-semibold text-xs sm:text-sm">
                All Past Papers
              </button>
            </div>
          </div>
        `;
      }

      const qList = paper.questions.map(q => {
        const chosen = state.paperAnswers[q.id];
        const isCorrect = state.paperSubmitted && chosen === q.answer;
        const opts = q.options.map((opt, oIdx) => {
          let cls = 'bg-slate-50 border-slate-200 text-slate-800 hover:bg-slate-100';
          if (!state.paperSubmitted && chosen === opt) {
            cls = 'bg-teal-50 border-mksTeal text-mksNavy ring-2 ring-teal-500/20 font-semibold';
          } else if (state.paperSubmitted) {
            if (opt === q.answer) cls = 'bg-emerald-50 border-emerald-500 text-emerald-950 font-bold';
            else if (chosen === opt && opt !== q.answer) cls = 'bg-rose-50 border-rose-500 text-rose-950 line-through';
          }
          return `
            <button ${state.paperSubmitted ? 'disabled' : ''} onclick="selectPaperChoice('${q.id}', ${oIdx})" class="w-full min-h-[50px] text-left p-3.5 rounded-2xl border-2 transition flex items-center gap-3 text-sm sm:text-base ${cls}">
              <span class="w-7 h-7 rounded-lg bg-white border border-slate-300 flex items-center justify-center text-xs font-bold shrink-0">${String.fromCharCode(65 + oIdx)}</span>
              <span>${opt}</span>
            </button>
          `;
        }).join('');

        return `
          <div class="bg-white rounded-3xl p-5 shadow-sm border ${state.paperSubmitted ? (isCorrect ? 'border-emerald-300' : 'border-rose-300') : 'border-slate-200'} space-y-3">
            <div class="flex items-center justify-between">
              <span class="text-xs font-bold text-slate-500 uppercase">${q.topic}</span>
              ${state.paperSubmitted ? (isCorrect
                ? `<span class="text-xs font-bold text-emerald-700 bg-emerald-100 px-2.5 py-1 rounded-full">✓ Correct (1 mark)</span>`
                : `<span class="text-xs font-bold text-rose-700 bg-rose-100 px-2.5 py-1 rounded-full">✗ Incorrect (0 marks)</span>`
              ) : ''}
            </div>
            <p class="font-semibold text-base sm:text-lg text-mksNavy">${q.prompt}</p>
            ${q.svg ? `<div class="py-1">${getIllustrationSVG(q.svg)}</div>` : ''}
            <div class="space-y-2">${opts}</div>
            ${state.paperSubmitted ? `
              <div class="p-3 rounded-2xl bg-slate-50 border border-slate-200 text-xs sm:text-sm text-slate-700">
                <strong>Marking Scheme:</strong> ${q.explanation}
              </div>
            ` : ''}
          </div>
        `;
      }).join('');

      return `
        <div class="space-y-4">
          <div class="bg-white rounded-2xl p-3.5 shadow-sm border border-slate-200 flex items-center justify-between gap-2 no-print">
            <button onclick="exitPaper()" class="min-h-[44px] text-xs sm:text-sm font-bold text-slate-600 hover:text-mksNavy flex items-center gap-1.5 px-3 py-1.5 rounded-xl bg-slate-100">
              <i class="fa-solid fa-arrow-left"></i> Exit
            </button>
            <div class="text-center">
              <div class="font-display font-bold text-xs sm:text-base text-mksNavy truncate max-w-[170px] sm:max-w-none">${paper.title}</div>
              <div class="text-xs text-slate-500">Answered: <strong>${answeredCount}/${total}</strong></div>
            </div>
            ${state.paperTimed && !state.paperSubmitted ? `
              <div class="px-3 py-1.5 rounded-xl bg-rose-50 border border-rose-200 text-rose-700 font-display font-bold text-sm flex items-center gap-1.5">
                <i class="fa-solid fa-stopwatch"></i>
                <span id="paperTimerDisp">${formatTime(state.timerSeconds)}</span>
              </div>
            ` : `<span class="text-xs font-bold text-teal-700 bg-teal-50 px-2.5 py-1.5 rounded-xl">${state.paperSubmitted ? 'Graded' : 'Untimed'}</span>`}
          </div>

          ${reportHTML}
          <div class="space-y-4">${qList}</div>

          ${!state.paperSubmitted ? `
            <div class="pt-2 pb-4 text-center no-print">
              <button onclick="submitPaper(false)" class="w-full sm:w-auto min-h-[54px] bg-emerald-600 hover:bg-emerald-700 text-white font-display font-bold text-base sm:text-lg px-8 py-3.5 rounded-2xl shadow-lg transition">
                <i class="fa-solid fa-paper-plane mr-2"></i> Submit &amp; Auto-Grade Exam (${answeredCount}/${total})
              </button>
            </div>
          ` : ''}
        </div>
      `;
    }

    // =========================================================================
    // 9. TAB 5: QUICK CHEAT SHEET
    // =========================================================================
    function renderCheatSheetView() {
      return `
        <div class="space-y-4 animate-pop">
          <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200 flex items-center justify-between gap-3">
            <div>
              <h2 class="font-display font-bold text-xl text-mksNavy">Year 3 Social Studies Quick Cheat Sheet</h2>
              <p class="text-xs sm:text-sm text-slate-600">High-contrast summary for last-minute revision or printing.</p>
            </div>
            <button onclick="window.print()" class="no-print shrink-0 min-h-[46px] px-4 py-2 rounded-2xl bg-mksNavy text-white font-display font-semibold text-xs sm:text-sm flex items-center gap-2">
              <i class="fa-solid fa-print"></i> Print
            </button>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-2 gap-4 text-xs sm:text-sm">
            <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200 space-y-2">
              <h3 class="font-display font-bold text-lg text-rose-700">1. Natural Disasters &amp; First-Aid</h3>
              <ul class="space-y-1.5 text-slate-800">
                <li>• <strong>Flood:</strong> Too much water overflowing from a river.</li>
                <li>• <strong>Earthquake:</strong> The ground shakes under us.</li>
                <li>• <strong>Tornado:</strong> Spinning air funnel coming close.</li>
                <li>• <strong>Tsunami:</strong> Very high ocean water waves.</li>
                <li>• <strong>Avalanche:</strong> Snow breaking up down a mountain.</li>
                <li>• <strong>Emergency Kit:</strong> Rubbing alcohol (falls/cuts), Flashlight (lights off), Bandages (burned finger).</li>
              </ul>
            </div>

            <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200 space-y-2">
              <h3 class="font-display font-bold text-lg text-amber-700">2. Pollution &amp; 7 Wonders</h3>
              <ul class="space-y-1.5 text-slate-800">
                <li>• <strong>Air Pollution:</strong> Factory &amp; car smoke.</li>
                <li>• <strong>Water Pollution:</strong> Ships throwing garbage in the sea &amp; dirty pipes.</li>
                <li>• <strong>Land Pollution:</strong> Garbage dumped on land/forests.</li>
                <li>• <strong>Endangered Animal:</strong> Might not exist after a few years.</li>
                <li>• <strong>Countries:</strong> Petra (<strong>Jordan</strong>), Great Wall (<strong>China</strong>), Pyramids of Giza (<strong>Egypt</strong>), Colossus of Rhodes (<strong>Greece</strong>), Hanging Gardens (<strong>Iraq</strong>), Leaning Tower of Pisa (<strong>Italy</strong>).</li>
              </ul>
            </div>

            <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200 space-y-2">
              <h3 class="font-display font-bold text-lg text-sky-700">3. Manners, Hygiene &amp; Health</h3>
              <ul class="space-y-1.5 text-slate-800">
                <li>• <strong>Magic Words:</strong> “Sorry” and “Excuse me!”</li>
                <li>• <strong>Good Manners:</strong> Ask permission before using others’ things and always return them.</li>
                <li>• <strong>Hygiene:</strong> Shower after sports, brush teeth before bed, trim/clean nails, turn off tap &amp; wash hands.</li>
                <li>• <strong>Healthy Body:</strong> Eat healthy foods; practice sports instead of sitting idle with video games; keep play areas clean and neat.</li>
              </ul>
            </div>

            <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200 space-y-2">
              <h3 class="font-display font-bold text-lg text-indigo-700">4. Leaders, Followers &amp; Friends</h3>
              <ul class="space-y-1.5 text-slate-800">
                <li>• <strong>Robin &amp; Samia:</strong> Samia makes decisions (leader); Robin follows her choices and never complains (follower).</li>
                <li>• <strong>Good Leader:</strong> Listens, shares ideas, helps followers, and shares things with them.</li>
                <li>• <strong>Good Friends (Green Star):</strong> Return books on time, share snacks, help carry heavy books, congratulate winners.</li>
                <li>• <strong>Bad Habits (Red Star):</strong> Laughing at mistakes, spreading secrets, ignoring friends, blaming others.</li>
              </ul>
            </div>
          </div>
        </div>
      `;
    }

    // =========================================================================
    // 10. INITIALIZATION
    // =========================================================================
    window.addEventListener('DOMContentLoaded', () => {
      document.getElementById('starCount').textContent = state.stars;
      updateNavStyles();
      renderCurrentView();
    });
  </script>
</body>
</html>
