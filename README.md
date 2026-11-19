<!DOCTYPE html>
<html lang="en" class="dark">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
  <title>REAL LIFE LEVELING SYSTEM</title>
  <meta name="theme-color" content="#05080f" />
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Orbitron:wght@500;600;700;800;900&family=Rajdhani:wght@500;600;700&display=swap" rel="stylesheet">
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    tailwind.config = {
      darkMode: 'class',
      theme: {
        extend: {
          colors: {
            void: '#05080f',
            navy: '#0a101d',
            panel: 'rgba(13, 21, 38, 0.85)',
            cyan: {
              electric: '#00f0ff',
              icy: '#70d6ff',
            }
          },
          fontFamily: {
            display: ['Orbitron', 'sans-serif'],
            tech: ['Rajdhani', 'sans-serif'],
            sans: ['Inter', 'sans-serif'],
          }
        }
      }
    }
  </script>
  <style>
    :root {
      --bg-void: #05080f;
      --bg-navy: #0a101d;
      --panel-bg: rgba(13, 21, 38, 0.85);
      --cyan-primary: #00f0ff;
      --cyan-secondary: #70d6ff;
      --border-glow: rgba(0, 240, 255, 0.25);
    }

    * {
      box-sizing: border-box;
      -webkit-tap-highlight-color: transparent;
    }

    body {
      background-color: var(--bg-void);
      background-image:
        radial-gradient(circle at 50% 0%, rgba(0, 240, 255, 0.08) 0%, transparent 55%),
        linear-gradient(180deg, #05080f 0%, #0a101d 100%);
      color: #f8fafc;
      font-family: 'Inter', sans-serif;
      overflow-x: hidden;
      min-height: 100vh;
    }

    /* Futuristic Cyber Grid & Scanline Overlay */
    .cyber-grid {
      background-size: 32px 32px;
      background-image:
        linear-gradient(to right, rgba(0, 240, 255, 0.04) 1px, transparent 1px),
        linear-gradient(to bottom, rgba(0, 240, 255, 0.04) 1px, transparent 1px);
    }

    .scanlines::after {
      content: "";
      position: fixed;
      inset: 0;
      pointer-events: none;
      background: linear-gradient(rgba(18, 16, 16, 0) 50%, rgba(0, 240, 255, 0.025) 50%);
      background-size: 100% 4px;
      z-index: 40;
    }

    body.reduced-motion .scanlines::after,
    body.reduced-motion .animate-pulse,
    body.reduced-motion .animate-ping,
    body.reduced-motion .animate-bounce,
    body.reduced-motion .xp-float,
    body.reduced-motion .holo-scan {
      animation: none !important;
    }

    body.reduced-motion * {
      transition-duration: 0.05s !important;
    }

    /* Holographic System Panels */
    .holo-panel {
      background: var(--panel-bg);
      backdrop-filter: blur(12px);
      -webkit-backdrop-filter: blur(12px);
      border: 1px solid rgba(0, 240, 255, 0.25);
      box-shadow: 0 4px 24px rgba(0, 0, 0, 0.5), inset 0 0 18px rgba(0, 240, 255, 0.04);
      position: relative;
    }

    .holo-panel-bright {
      background: rgba(15, 26, 48, 0.92);
      border: 1px solid rgba(0, 240, 255, 0.5);
      box-shadow: 0 0 24px rgba(0, 240, 255, 0.14), inset 0 0 20px rgba(0, 240, 255, 0.07);
      position: relative;
    }

    /* Corner Brackets */
    .bracket-corners::before,
    .bracket-corners::after {
      content: "";
      position: absolute;
      width: 10px;
      height: 10px;
      border-color: #00f0ff;
      pointer-events: none;
    }
    .bracket-corners::before {
      top: -1px;
      left: -1px;
      border-top: 2px solid #00f0ff;
      border-left: 2px solid #00f0ff;
    }
    .bracket-corners::after {
      bottom: -1px;
      right: -1px;
      border-bottom: 2px solid #00f0ff;
      border-right: 2px solid #00f0ff;
    }

    /* XP Progress Bar */
    .xp-bar-fill {
      background: linear-gradient(90deg, #0284c7 0%, #00f0ff 60%, #a5f3fc 100%);
      box-shadow: 0 0 12px rgba(0, 240, 255, 0.6);
      transition: width 0.65s cubic-bezier(0.22, 1, 0.36, 1);
    }

    /* Animations */
    @keyframes floatXp {
      0% { opacity: 0; transform: translateY(14px) scale(0.85); }
      20% { opacity: 1; transform: translateY(0) scale(1.08); }
      80% { opacity: 1; transform: translateY(-22px) scale(1); }
      100% { opacity: 0; transform: translateY(-38px) scale(0.95); }
    }
    .xp-float {
      animation: floatXp 1.75s cubic-bezier(0.16, 1, 0.3, 1) forwards;
    }

    @keyframes holoSweep {
      0% { transform: translateY(-100%); }
      100% { transform: translateY(250%); }
    }
    .holo-scan {
      position: absolute;
      left: 0;
      right: 0;
      height: 36px;
      background: linear-gradient(180deg, transparent, rgba(0, 240, 255, 0.12), transparent);
      animation: holoSweep 4.5s linear infinite;
      pointer-events: none;
    }

    /* Custom Scrollbar */
    ::-webkit-scrollbar {
      width: 4px;
      height: 4px;
    }
    ::-webkit-scrollbar-track {
      background: #05080f;
    }
    ::-webkit-scrollbar-thumb {
      background: rgba(0, 240, 255, 0.3);
      border-radius: 9999px;
    }

    /* Range Slider Styling */
    input[type="range"] {
      -webkit-appearance: none;
      background: rgba(148, 163, 184, 0.2);
      height: 6px;
      border-radius: 999px;
    }
    input[type="range"]::-webkit-slider-thumb {
      -webkit-appearance: none;
      width: 18px;
      height: 18px;
      border-radius: 50%;
      background: #00f0ff;
      box-shadow: 0 0 10px #00f0ff;
      cursor: pointer;
    }
  </style>
</head>
<body class="cyber-grid scanlines selection:bg-cyan-500/30 selection:text-cyan-200">

  <!-- App Root Container -->
  <div id="app" class="max-w-lg mx-auto min-h-screen flex flex-col relative pb-24"></div>

  <!-- Floating System Toast & XP Burst Layer -->
  <div id="toast-layer" class="fixed top-4 left-1/2 -translate-x-1/2 z-50 w-full max-w-md px-4 pointer-events-none flex flex-col items-center gap-2"></div>
  <div id="xp-burst-layer" class="fixed inset-0 pointer-events-none z-50 flex items-center justify-center"></div>

  <!-- Modal Layer -->
  <div id="modal-layer" class="fixed inset-0 z-50 hidden items-center justify-center bg-black/80 backdrop-blur-sm p-4 overflow-y-auto"></div>

  <script>
    /**
     * ============================================================================
     * REAL LIFE LEVELING SYSTEM — MODULAR CORE ENGINE
     * ============================================================================
     * Modules:
     * 1. AudioEngine (Web Audio API futuristic chimes, respects sound toggle)
     * 2. DateUtils (Local calendar dates, ISO week keys for exploit prevention)
     * 3. XPLevelEngine (Dynamic scaling, cumulative levels, multi-level up, ranks)
     * 4. ExerciseLibraryDB (Comprehensive safe teen-friendly exercise database + SVG diagrams)
     * 5. NutritionEngine (Balanced Indian family meal system)
     * 6. AchievementCatalog (Safe participation & skill achievements)
     * 7. StorageDB (localStorage + IndexedDB for private local photos)
     * 8. WorkoutGenerator (Adaptive daily mission generator)
     * 9. UIRenderer & Controllers (Onboarding, 5 Tabs, Active Workout, Skill Tree, Hunter Card)
     */

    // ============================================================================
    // 1. AUDIO ENGINE (SYNTHESIZED FUTURISTIC SYSTEM SFX)
    // ============================================================================
    const AudioEngine = {
      ctx: null,
      init() {
        if (!this.ctx && (window.AudioContext || window.webkitAudioContext)) {
          this.ctx = new (window.AudioContext || window.webkitAudioContext)();
        }
      },
      play(type) {
        if (!AppState?.settings?.soundEnabled) return;
        try {
          this.init();
          if (!this.ctx) return;
          if (this.ctx.state === 'suspended') this.ctx.resume();

          const now = this.ctx.currentTime;
          const osc = this.ctx.createOscillator();
          const gain = this.ctx.createGain();
          osc.connect(gain);
          gain.connect(this.ctx.destination);

          if (type === 'click') {
            osc.type = 'sine';
            osc.frequency.setValueAtTime(720, now);
            osc.frequency.exponentialRampToValueAtTime(1080, now + 0.06);
            gain.gain.setValueAtTime(0.06, now);
            gain.gain.exponentialRampToValueAtTime(0.001, now + 0.07);
            osc.start(now);
            osc.stop(now + 0.07);
          } else if (type === 'quest') {
            osc.type = 'triangle';
            osc.frequency.setValueAtTime(523.25, now); // C5
            osc.frequency.setValueAtTime(659.25, now + 0.08); // E5
            osc.frequency.setValueAtTime(783.99, now + 0.16); // G5
            osc.frequency.setValueAtTime(1046.5, now + 0.24); // C6
            gain.gain.setValueAtTime(0.11, now);
            gain.gain.exponentialRampToValueAtTime(0.001, now + 0.45);
            osc.start(now);
            osc.stop(now + 0.45);
          } else if (type === 'levelup') {
            const notes = [440, 554.37, 659.25, 880, 1108.73];
            notes.forEach((freq, idx) => {
              const o = this.ctx.createOscillator();
              const g = this.ctx.createGain();
              o.type = 'sawtooth';
              o.connect(g);
              g.connect(this.ctx.destination);
              o.frequency.setValueAtTime(freq, now + idx * 0.09);
              g.gain.setValueAtTime(0.07, now + idx * 0.09);
              g.gain.exponentialRampToValueAtTime(0.001, now + idx * 0.09 + 0.35);
              o.start(now + idx * 0.09);
              o.stop(now + idx * 0.09 + 0.35);
            });
          } else if (type === 'timer') {
            osc.type = 'sine';
            osc.frequency.setValueAtTime(880, now);
            osc.frequency.setValueAtTime(1174.66, now + 0.12);
            gain.gain.setValueAtTime(0.1, now);
            gain.gain.exponentialRampToValueAtTime(0.001, now + 0.3);
            osc.start(now);
            osc.stop(now + 0.3);
          }
        } catch (e) {
          // Audio blocked or unsupported
        }
      }
    };

    // ============================================================================
    // 2. DATE & CALENDAR UTILITIES
    // ============================================================================
    const DateUtils = {
      todayKey(dateObj = new Date()) {
        const y = dateObj.getFullYear();
        const m = String(dateObj.getMonth() + 1).padStart(2, '0');
        const d = String(dateObj.getDate()).padStart(2, '0');
        return `${y}-${m}-${d}`;
      },
      dayOfWeekShort(dateObj = new Date()) {
        return ['Sun', 'Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat'][dateObj.getDay()];
      },
      isMonday(dateObj = new Date()) {
        return dateObj.getDay() === 1;
      },
      // ISO Week identifier YYYY-Www to prevent duplicate weekly evaluation XP
      isoWeekKey(dateObj = new Date()) {
        const d = new Date(Date.UTC(dateObj.getFullYear(), dateObj.getMonth(), dateObj.getDate()));
        const dayNum = d.getUTCDay() || 7;
        d.setUTCDate(d.getUTCDate() + 4 - dayNum);
        const yearStart = new Date(Date.UTC(d.getUTCFullYear(), 0, 1));
        const weekNo = Math.ceil((((d - yearStart) / 86400000) + 1) / 7);
        return `${d.getUTCFullYear()}-W${String(weekNo).padStart(2, '0')}`;
      },
      formatDisplay(dateStr) {
        if (!dateStr) return '';
        const [y, m, d] = dateStr.split('-').map(Number);
        const dt = new Date(y, m - 1, d);
        return dt.toLocaleDateString('en-IN', { weekday: 'short', day: 'numeric', month: 'short', year: 'numeric' });
      }
    };

    // ============================================================================
    // 3. DYNAMIC XP, LEVELING & RANK ENGINE
    // ============================================================================
    const XPLevelEngine = {
      BASE_QUEST_XP: {
        Minor: 25,
        Normal: 50,
        Challenging: 80,
        Major: 120,
        WeeklyEvaluation: 150
      },
      // XP required to advance from level L to L+1
      xpRequiredForLevel(level) {
        return 250 + 100 * (Math.max(1, level) - 1);
      },
      // Cumulative XP needed to reach `targetLevel` (Level 1 = 0, Level 2 = 250, Level 3 = 600, Level 4 = 1050...)
      cumulativeXpForLevel(targetLevel) {
        let total = 0;
        for (let l = 1; l < targetLevel; l++) {
          total += this.xpRequiredForLevel(l);
        }
        return total;
      },
      // Compute level & progress breakdown from total lifetime XP
      calculateProgress(totalXP) {
        let level = 1;
        let remaining = Math.max(0, totalXP);
        while (remaining >= this.xpRequiredForLevel(level)) {
          remaining -= this.xpRequiredForLevel(level);
          level++;
        }
        const xpForNext = this.xpRequiredForLevel(level);
        const currentLevelFloor = this.cumulativeXpForLevel(level);
        const nextLevelCeiling = currentLevelFloor + xpForNext;
        const pct = Math.min(100, Math.round((remaining / xpForNext) * 100));
        return {
          level,
          totalXP,
          xpIntoLevel: remaining,
          xpForNext,
          currentLevelFloor,
          nextLevelCeiling,
          pct
        };
      },
      // Multiplier: 1 + 0.05 * (PlayerLevel - 1)
      getLevelMultiplier(level) {
        return 1 + 0.05 * (Math.max(1, level) - 1);
      },
      // Rounded to nearest 5 XP
      calculateQuestReward(baseXP, level) {
        const mult = this.getLevelMultiplier(level);
        const raw = baseXP * mult;
        const finalXP = Math.round(raw / 5) * 5;
        const bonusXP = Math.max(0, finalXP - baseXP);
        return {
          baseXP,
          multiplier: mult,
          bonusXP,
          finalXP
        };
      },
      // Rank earned through sustained participation, skill development & milestones (never weight/body metrics)
      calculateRank(state) {
        const prog = this.calculateProgress(state.xp.totalXP);
        const lvl = prog.level;
        const sessions = state.history.sessions.length;
        const unlockedAch = Object.keys(state.achievements.unlocked).length;
        const totalSkillLevels = Object.values(state.skills).reduce((acc, s) => acc + s.level, 0);

        if (lvl >= 25 && sessions >= 60 && totalSkillLevels >= 35 && unlockedAch >= 10) return 'Elite';
        if (lvl >= 18 && sessions >= 40 && totalSkillLevels >= 26 && unlockedAch >= 8) return 'S';
        if (lvl >= 13 && sessions >= 26 && totalSkillLevels >= 20 && unlockedAch >= 7) return 'A';
        if (lvl >= 9 && sessions >= 16 && totalSkillLevels >= 15 && unlockedAch >= 5) return 'B';
        if (lvl >= 6 && sessions >= 9 && totalSkillLevels >= 11 && unlockedAch >= 4) return 'C';
        if (lvl >= 3 && sessions >= 4 && totalSkillLevels >= 8 && unlockedAch >= 2) return 'D';
        if (lvl >= 2 || sessions >= 1) return 'E';
        return 'Novice';
      },
      getRankMeta(rank) {
        const map = {
          Novice: { color: '#94a3b8', border: 'border-slate-500/40', bg: 'bg-slate-800/60', desc: 'Newly awakened System Initiate' },
          E: { color: '#38bdf8', border: 'border-sky-400/40', bg: 'bg-sky-950/60', desc: 'Active Field Trainee' },
          D: { color: '#00f0ff', border: 'border-cyan-400/50', bg: 'bg-cyan-950/60', desc: 'Consistent Disciplined Hunter' },
          C: { color: '#34d399', border: 'border-emerald-400/50', bg: 'bg-emerald-950/60', desc: 'Adaptable Tactical Athlete' },
          B: { color: '#a78bfa', border: 'border-violet-400/50', bg: 'bg-violet-950/60', desc: 'Vanguard Movement Specialist' },
          A: { color: '#f59e0b', border: 'border-amber-400/50', bg: 'bg-amber-950/60', desc: 'Master of Physical Discipline' },
          S: { color: '#f43f5e', border: 'border-rose-400/60', bg: 'bg-rose-950/60', desc: 'Apex Sovereign Performer' },
          Elite: { color: '#00f0ff', border: 'border-cyan-300', bg: 'bg-cyan-900/70', desc: 'Transcendent System Legend' }
        };
        return map[rank] || map.Novice;
      }
    };

    // ============================================================================
    // 4. EXERCISE LIBRARY & CUSTOM SVG DIAGRAMS
    // ============================================================================
    const ExerciseLibraryDB = [
      // WARM-UP & MOBILITY
      {
        id: 'ex_arm_circles',
        name: 'Dynamic Arm & Shoulder Circles',
        category: 'Warm-up & Mobility',
        skill: 'Mobility',
        equipment: ['No Equipment'],
        difficulty: 'Minor',
        pattern: 'Joint Mobilization',
        defaultPrescription: '2 sets × 30 sec each direction',
        isTimed: true,
        durationSec: 30,
        restSec: 20,
        instructions: [
          'Stand tall with feet shoulder-width apart and core lightly braced.',
          'Extend both arms straight out to the sides at shoulder height.',
          'Make controlled small circles forward for 15 seconds, gradually widening.',
          'Reverse direction smoothly without shrugging your shoulders up.'
        ],
        mistakes: ['Rushing with uncontrolled momentum', 'Shrugging shoulders toward ears'],
        safety: 'Keep movements pain-free within your comfortable shoulder range.',
        alternativeId: 'ex_cat_cow',
        diagramType: 'mobility'
      },
      {
        id: 'ex_cat_cow',
        name: 'Thoracic Cat-Cow Mobility Flow',
        category: 'Warm-up & Mobility',
        skill: 'Mobility',
        equipment: ['No Equipment', 'Exercise Mat'],
        difficulty: 'Minor',
        pattern: 'Spinal Mobility',
        defaultPrescription: '2 sets × 8 slow breaths',
        isTimed: false,
        restSec: 30,
        instructions: [
          'Start on hands and knees with wrists under shoulders and knees under hips.',
          'Inhale gently, dropping your belly slightly and lifting your chest forward.',
          'Exhale slowly, pressing the floor away and rounding your upper back.',
          'Move segment by segment through your spine.'
        ],
        mistakes: ['Holding breath', 'Forcing extreme lower-back arch'],
        safety: 'Use a folded towel or exercise mat under knees for cushioning.',
        alternativeId: 'ex_arm_circles',
        diagramType: 'mobility'
      },
      {
        id: 'ex_world_greatest',
        name: 'World’s Greatest Hip & Spine Stretch',
        category: 'Warm-up & Mobility',
        skill: 'Mobility',
        equipment: ['No Equipment', 'Exercise Mat'],
        difficulty: 'Normal',
        pattern: 'Hip & Thoracic Opener',
        defaultPrescription: '2 sets × 5 reps per side',
        isTimed: false,
        restSec: 30,
        instructions: [
          'Step your right foot forward into a long, comfortable lunge.',
          'Place your left hand flat on the floor inside your front foot.',
          'Rotate your right arm up toward the ceiling, following your hand with your eyes.',
          'Return hand down, step back, and alternate sides.'
        ],
        mistakes: ['Twisting too fast', 'Letting front knee collapse inward'],
        safety: 'Lower your back knee to the mat if holding a high lunge feels unstable.',
        alternativeId: 'ex_cat_cow',
        diagramType: 'lunge'
      },
      {
        id: 'ex_inchworm',
        name: 'Inchworm Walkout',
        category: 'Warm-up & Mobility',
        skill: 'Mobility',
        equipment: ['No Equipment', 'Exercise Mat'],
        difficulty: 'Normal',
        pattern: 'Posterior Chain & Core Prep',
        defaultPrescription: '2 sets × 6 reps',
        isTimed: false,
        restSec: 40,
        instructions: [
          'Stand tall, hinge at your hips, and place hands on the floor (bend knees as needed).',
          'Walk your hands forward until you reach a strong high-plank position.',
 
