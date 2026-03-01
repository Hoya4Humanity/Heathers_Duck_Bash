<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Heather's Duck Bash | Interactive Guide</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&family=Inter:wght@400;600;800&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f8fafc;
            color: #0f172a;
        }
        h1, h2, h3, .arcade-font {
            font-family: 'Press Start 2P', cursive;
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 500px;
            margin-left: auto;
            margin-right: auto;
            height: 350px;
            max-height: 350px;
        }
        .weapon-card {
            transition: all 0.2s ease-in-out;
        }
        .weapon-card.active {
            border-color: #eab308;
            background-color: #fefce8;
            transform: scale(1.05);
        }
    </style>
</head>
<body class="antialiased min-h-screen flex flex-col items-center pt-10 pb-20 px-4 sm:px-6 lg:px-8">

<!-- Chosen Palette: Arcade Light (Slate 50 background, Slate 900 text, Yellow 500 & Blue 500 accents) -->
<!-- Application Structure Plan: A centralized, scrollable "Game Manual" dashboard. It uses a hero section for immediate context and CTA, an interactive 'Armory' to explore weapons, a feature grid for quick scanning, and a visual tech stack chart. This structure prioritizes user engagement by breaking dense README text into interactable, bite-sized modules rather than a linear document. -->
<!-- Visualization & Content Choices: 1. Story/Intro -> Text blocks -> Context setting. 2. Progressive Ballistics -> Interactive Card Selector -> Engagement & exploration -> Vanilla JS state switching. 3. Tech Stack -> Doughnut Chart -> Visualizing proportions of the project -> Chart.js. Confirming NO SVG or Mermaid used; only Canvas and Unicode. -->
<!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->

<div class="max-w-5xl w-full bg-white shadow-xl rounded-2xl overflow-hidden border-4 border-slate-800">
    
    <header class="bg-slate-800 text-white p-8 md:p-12 text-center relative border-b-8 border-yellow-500">
        <div class="text-6xl mb-6">⚡🦆🪠</div>
        <h1 class="text-2xl md:text-4xl leading-loose mb-4 text-yellow-400">HEATHER'S DUCK BASH</h1>
        <h2 class="text-lg md:text-xl arcade-font text-blue-300 mb-8">THUNDER EDITION</h2>
        
        <blockquote class="italic text-slate-300 max-w-2xl mx-auto border-l-4 border-yellow-500 pl-4 mb-8 font-serif text-lg">
            "Whosoever holds this plunger, if they be worthy, shall possess the power of... THE BASH." <br>
            <span class="block mt-2 font-bold not-italic text-sm text-yellow-400">— The Thunder Mallard</span>
        </blockquote>

        <a href="https://Hoya4Humanity.github.io/Heathers_Duck_Bash/" target="_blank" class="inline-block bg-yellow-500 hover:bg-yellow-400 text-slate-900 arcade-font py-4 px-8 rounded-full border-4 border-slate-900 shadow-[4px_4px_0_0_rgba(15,23,42,1)] transition-transform active:translate-y-1 active:shadow-none">
            PLAY THE GAME LIVE! 🎮
        </a>
    </header>

    <nav class="bg-slate-100 border-b-2 border-slate-200 sticky top-0 z-10 flex flex-wrap justify-center gap-4 p-4 arcade-font text-[10px] md:text-xs">
        <button class="nav-btn hover:text-blue-600 uppercase tracking-widest text-slate-600" data-target="story">The Lore</button>
        <button class="nav-btn hover:text-blue-600 uppercase tracking-widest text-slate-600" data-target="features">Features</button>
        <button class="nav-btn hover:text-blue-600 uppercase tracking-widest text-slate-600" data-target="armory">Armory</button>
        <button class="nav-btn hover:text-blue-600 uppercase tracking-widest text-slate-600" data-target="tech">Tech Stack</button>
    </nav>

    <main class="p-6 md:p-12 space-y-20">

        <section id="story" class="max-w-3xl mx-auto">
            <h3 class="arcade-font text-xl text-blue-600 mb-6 flex items-center gap-3">
                <span>🌊</span> THE STORY
            </h3>
            <p class="text-lg leading-relaxed text-slate-700 mb-4 font-semibold">
                The Great Porcelain River is flowing with chaos.
            </p>
            <p class="text-lg leading-relaxed text-slate-700">
                Bouncing ducks have taken over the banks, and the legendary <strong class="text-slate-900">Thunder Mallard</strong> (basically Thor, but with more feathers and a Texas drawl) has summoned <strong class="text-slate-900">Heather</strong> to clear the path. Armed only with high-velocity plungers and the raw power of thunder, it's time to bash.
            </p>
        </section>

        <section id="features" class="bg-slate-50 p-8 rounded-xl border-2 border-slate-200">
            <h3 class="arcade-font text-xl text-yellow-600 mb-8 text-center flex items-center justify-center gap-3">
                <span>✨</span> EPIC FEATURES
            </h3>
            <p class="text-center text-slate-600 mb-10 max-w-2xl mx-auto">
                Discover the mechanics that make this vertical shooter a mythological experience. Hover over the cards to learn more.
            </p>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                <div class="bg-white p-6 rounded-lg border-2 border-slate-200 shadow-sm hover:shadow-md hover:border-blue-400 transition-all cursor-default group">
                    <div class="text-4xl mb-4 group-hover:scale-110 transition-transform">🎳</div>
                    <h4 class="font-bold text-lg mb-2 text-slate-900">Bowling Duck AI</h4>
                    <p class="text-slate-600 text-sm">Ducks don't just swim; they bounce off the grassy banks like a chaotic game of bowling. Watch your angles!</p>
                </div>
                <div class="bg-white p-6 rounded-lg border-2 border-slate-200 shadow-sm hover:shadow-md hover:border-yellow-400 transition-all cursor-default group">
                    <div class="text-4xl mb-4 group-hover:scale-110 transition-transform">⛈️</div>
                    <h4 class="font-bold text-lg mb-2 text-slate-900">The Voice of Thunder</h4>
                    <p class="text-slate-600 text-sm">Features Thor-inspired AI Narration. Between levels and before bosses, hear the majestic, booming voice of the Thunder Mallard.</p>
                </div>
                <div class="bg-white p-6 rounded-lg border-2 border-slate-200 shadow-sm hover:shadow-md hover:border-red-400 transition-all cursor-default group">
                    <div class="text-4xl mb-4 group-hover:scale-110 transition-transform">🦖</div>
                    <h4 class="font-bold text-lg mb-2 text-slate-900">AI-Generated Bosses</h4>
                    <p class="text-slate-600 text-sm">Every boss encounter features a unique portrait generated by Imagen 4.0, giving you a look at the "Quack-Tsar" before you fight.</p>
                </div>
                <div class="bg-white p-6 rounded-lg border-2 border-slate-200 shadow-sm hover:shadow-md hover:border-green-400 transition-all cursor-default group">
                    <div class="text-4xl mb-4 group-hover:scale-110 transition-transform">🏆</div>
                    <h4 class="font-bold text-lg mb-2 text-slate-900">Global Leaderboard</h4>
                    <p class="text-slate-600 text-sm">Your scores are saved to the cloud. Compete with friends to see who is truly worthy of the Thunder Plunger.</p>
                </div>
            </div>
        </section>

        <section id="armory" class="max-w-4xl mx-auto">
            <h3 class="arcade-font text-xl text-slate-800 mb-4 text-center">
                PROGRESSIVE BALLISTICS
            </h3>
            <p class="text-center text-slate-600 mb-8">
                Select a weapon below to view its combat specifications.
            </p>
            
            <div class="flex flex-col md:flex-row gap-8 items-center bg-white p-8 rounded-xl border-4 border-slate-800 shadow-lg">
                <div class="flex flex-row md:flex-col gap-4 w-full md:w-1/3">
                    <button class="weapon-btn weapon-card active border-2 border-slate-300 rounded-lg p-4 text-left flex items-center gap-4 bg-slate-50" data-weapon="plunger">
                        <span class="text-3xl">🪠</span>
                        <span class="font-bold hidden sm:block">Plunger</span>
                    </button>
                    <button class="weapon-btn weapon-card border-2 border-slate-300 rounded-lg p-4 text-left flex items-center gap-4 bg-slate-50" data-weapon="tp">
                        <span class="text-3xl">🧻</span>
                        <span class="font-bold hidden sm:block">Toilet Paper</span>
                    </button>
                    <button class="weapon-btn weapon-card border-2 border-slate-300 rounded-lg p-4 text-left flex items-center gap-4 bg-slate-50" data-weapon="turd">
                        <span class="text-3xl">💩</span>
                        <span class="font-bold hidden sm:block">Turd-nado</span>
                    </button>
                </div>

                <div class="w-full md:w-2/3 bg-slate-900 text-white p-8 rounded-lg border-4 border-yellow-500 min-h-[250px] flex flex-col justify-center relative overflow-hidden">
                    <div class="absolute -right-10 -bottom-10 text-9xl opacity-10" id="display-icon">🪠</div>
                    <div class="relative z-10">
                        <div class="text-yellow-400 arcade-font text-[10px] tracking-widest mb-2" id="display-level">UNLOCKS: LEVEL 1</div>
                        <h4 class="text-2xl arcade-font mb-4 text-white leading-loose" id="display-title">THE TRUSTY PLUMBER</h4>
                        <p class="text-slate-300 text-lg leading-relaxed" id="display-desc">
                            Your standard issue high-velocity bash tool. Reliable, aerodynamic, and thoroughly sanitized.
                        </p>
                    </div>
                </div>
            </div>
        </section>

        <section id="tech" class="bg-slate-50 p-8 rounded-xl border-2 border-slate-200">
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                <div>
                    <h3 class="arcade-font text-xl text-blue-600 mb-6 flex items-center gap-3">
                        <span>🛠️</span> TECH STACK
                    </h3>
                    <p class="text-slate-700 mb-6">
                        Heather's Duck Bash operates on a modern, single-file architecture powered heavily by AI integrations for dynamic gameplay and content generation.
                    </p>
                    <ul class="space-y-4">
                        <li class="flex items-start gap-3">
                            <span class="text-xl">🌐</span>
                            <div>
                                <strong class="block text-slate-900">Frontend Core</strong>
                                <span class="text-sm text-slate-600">HTML5, Vanilla JavaScript, Tailwind CSS</span>
                            </div>
                        </li>
                        <li class="flex items-start gap-3">
                            <span class="text-xl">🧠</span>
                            <div>
                                <strong class="block text-slate-900">AI Engine</strong>
                                <span class="text-sm text-slate-600">Gemini 2.5 Flash (Narration Logic)</span>
                            </div>
                        </li>
                        <li class="flex items-start gap-3">
                            <span class="text-xl">🔊</span>
                            <div>
                                <strong class="block text-slate-900">Audio & Visuals</strong>
                                <span class="text-sm text-slate-600">Gemini TTS (Thor Voice) & Imagen 4.0</span>
                            </div>
                        </li>
                        <li class="flex items-start gap-3">
                            <span class="text-xl">💾</span>
                            <div>
                                <strong class="block text-slate-900">Backend System</strong>
                                <span class="text-sm text-slate-600">Firebase Firestore (Global Leaderboard)</span>
                            </div>
                        </li>
                    </ul>
                </div>
                
                <div class="bg-white p-6 rounded-xl border-2 border-slate-200 shadow-sm flex flex-col items-center">
                    <h4 class="font-bold text-center mb-4 text-slate-800">Architecture Distribution</h4>
                    <div class="chart-container">
                        <canvas id="techChart"></canvas>
                    </div>
                </div>
            </div>
        </section>

        <section class="max-w-2xl mx-auto text-center border-t-4 border-slate-200 pt-12">
            <h3 class="arcade-font text-lg text-slate-800 mb-4">DEPLOYMENT & CONTRIBUTIONS</h3>
            <p class="text-slate-600 mb-6 text-sm">
                This project is built as a Single-File Application. Clone the repo, open `index.html` in any browser, or host it easily using GitHub Pages.
            </p>
            <p class="text-slate-600 text-sm mb-6">
                Have a cooler weapon idea? Want to add a "Golden Goose" boss? Pull requests are welcome! Remember: Stay worthy, keep your plungers dry, and watch out for the river banks.
            </p>
            <div class="inline-block bg-slate-800 text-white px-6 py-2 rounded-full text-xs tracking-widest">
                CREATED FOR HEATHER ⚡🦆
            </div>
        </section>

    </main>

</div>

<script>
    const weaponData = {
        plunger: {
            title: "THE TRUSTY PLUNGER",
            level: "UNLOCKS: LEVEL 1",
            desc: "Your standard issue high-velocity bash tool. Reliable, aerodynamic, and thoroughly sanitized.",
            icon: "🪠"
        },
        tp: {
            title: "RAPID-FIRE T.P.",
            level: "UNLOCKS: LEVEL 2",
            desc: "Three streams of pure wiping power. Fires a spread shot to cover maximum river width.",
            icon: "🧻"
        },
        turd: {
            title: "THE TURD-NADO",
            level: "UNLOCKS: LEVEL 4",
            desc: "Heavy splash damage for clearing the pond. A mythological mass of pure destruction.",
            icon: "💩"
        }
    };

    const weaponBtns = document.querySelectorAll('.weapon-btn');
    const displayTitle = document.getElementById('display-title');
    const displayLevel = document.getElementById('display-level');
    const displayDesc = document.getElementById('display-desc');
    const displayIcon = document.getElementById('display-icon');

    weaponBtns.forEach(btn => {
        btn.addEventListener('click', () => {
            weaponBtns.forEach(b => b.classList.remove('active'));
            btn.classList.add('active');
            
            const wId = btn.getAttribute('data-weapon');
            const data = weaponData[wId];
            
            displayTitle.innerText = data.title;
            displayLevel.innerText = data.level;
            displayDesc.innerText = data.desc;
            displayIcon.innerText = data.icon;
        });
    });

    const navBtns = document.querySelectorAll('.nav-btn');
    navBtns.forEach(btn => {
        btn.addEventListener('click', () => {
            const targetId = btn.getAttribute('data-target');
            document.getElementById(targetId).scrollIntoView({ behavior: 'smooth' });
        });
    });

    const ctx = document.getElementById('techChart').getContext('2d');
    new Chart(ctx, {
        type: 'doughnut',
        data: {
            labels: ['Frontend Core (HTML/JS/CSS)', 'AI Engine (Gemini)', 'Audio/Art (TTS/Imagen)', 'Database (Firestore)'],
            datasets: [{
                data: [40, 30, 20, 10],
                backgroundColor: [
                    '#3b82f6',
                    '#eab308',
                    '#ef4444',
                    '#22c55e'
                ],
                borderWidth: 0,
                hoverOffset: 10
            }]
        },
        options: {
            responsive: true,
            maintainAspectRatio: false,
            plugins: {
                legend: {
                    position: 'bottom',
                    labels: {
                        color: '#475569',
                        padding: 20,
                        font: {
                            family: "'Inter', sans-serif",
                            size: 12
                        }
                    }
                },
                tooltip: {
                    backgroundColor: '#0f172a',
                    titleFont: { family: "'Press Start 2P', cursive", size: 9 },
                    bodyFont: { family: "'Inter', sans-serif", size: 13 },
                    padding: 12,
                    cornerRadius: 8,
                    callbacks: {
                        label: function(context) {
                            let label = context.label || '';
                            if (label) {
                                label = label.length > 16 ? label.substring(0, 16) + '...' + ': ' : label + ': ';
                            }
                            if (context.parsed !== null) {
                                label += context.parsed + '%';
                            }
                            return label;
                        }
                    }
                }
            },
            cutout: '65%'
        }
    });
</script>
</body>
</html>
