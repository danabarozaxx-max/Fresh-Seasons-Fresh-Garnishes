<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fresh Seasons, Fresh Garnishes: Culinary Artistry Master Guide</title>
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Google Fonts (Playfair Display & Plus Jakarta Sans) -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400..900;1,400..900&family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        parchment: '#fcfaf6',
                        'parchment-dark': '#f3ede2',
                        forest: '#1b3b2b',
                        sage: '#6b8a74',
                        terracotta: '#bc5a45',
                        gold: '#d4af37',
                        'gold-hover': '#b89428',
                        charcoal: '#222524'
                    },
                    fontFamily: {
                        serif: ['Playfair Display', 'serif'],
                        sans: ['Plus Jakarta Sans', 'sans-serif'],
                    }
                }
            }
        }
    </script>

    <style>
        body {
            background-color: #fcfaf6;
            color: #222524;
            font-family: 'Plus Jakarta Sans', sans-serif;
            transition: background-color 0.5s ease, color 0.5s ease;
        }

        /* Seasonal dynamic themes */
        body.theme-spring {
            --accent-primary: #2d6a4f;
            --accent-secondary: #e8a598;
            --accent-bg: #f2f7f4;
            --hero-gradient: linear-gradient(135deg, #143623 0%, #2a573d 100%);
        }
        body.theme-summer {
            --accent-primary: #d97706;
            --accent-secondary: #059669;
            --accent-bg: #fffbeb;
            --hero-gradient: linear-gradient(135deg, #6b2d07 0%, #a14708 100%);
        }
        body.theme-autumn {
            --accent-primary: #bc5a45;
            --accent-secondary: #d97706;
            --accent-bg: #fdf6f0;
            --hero-gradient: linear-gradient(135deg, #3b1207 0%, #6e2410 100%);
        }
        body.theme-winter {
            --accent-primary: #2563eb;
            --accent-secondary: #475569;
            --accent-bg: #f0f9ff;
            --hero-gradient: linear-gradient(135deg, #0b1329 0%, #17254a 100%);
        }

        .hero-banner {
            background: var(--hero-gradient);
            transition: background 0.7s ease;
        }

        /* Custom scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #f3ede2;
        }
        ::-webkit-scrollbar-thumb {
            background: #6b8a74;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #1b3b2b;
        }

        .active-dish {
            border-color: #d4af37 !important;
            background-color: #fefce8 !important;
        }

        /* Print Styling for Chef's Kitchen Sheet */
        @media print {
            header, footer, nav, #simulators, #dish-builder, #heritage, #tools, #hydro-timer, .no-print {
                display: none !important;
            }
            .print-only {
                display: block !important;
            }
            body {
                background: white !important;
                color: black !important;
            }
            #notebook-modal {
                position: static !important;
                background: white !important;
                display: block !important;
                box-shadow: none !important;
                padding: 0 !important;
            }
            #notebook-modal > div {
                max-width: 100% !important;
                box-shadow: none !important;
                border: none !important;
            }
        }
    </style>
</head>
<body class="theme-spring min-h-screen flex flex-col antialiased selection:bg-gold selection:text-white">

    <!-- Top Navigation Bar -->
    <header class="sticky top-0 z-40 bg-parchment/90 backdrop-blur-md border-b border-stone-200/80 transition-all duration-300">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between">
            <div class="flex items-center space-x-3">
                <div class="w-10 h-10 rounded-full bg-forest text-gold flex items-center justify-center font-serif text-xl font-bold shadow-md">
                    <i class="fa-solid fa-leaf"></i>
                </div>
                <div>
                    <span class="font-serif text-xl sm:text-2xl font-bold tracking-tight text-forest block leading-none">Fresh Seasons</span>
                    <span class="text-[10px] uppercase tracking-widest text-stone-500 font-semibold">Master Culinary Garnishing Repository</span>
                </div>
            </div>

            <!-- Desktop Navigation Links -->
            <nav class="hidden lg:flex items-center space-x-6 text-sm font-medium text-stone-700">
                <a href="#heritage" class="hover:text-terracotta transition-colors">Filipino & SE Asian Arts</a>
                <a href="#library" class="hover:text-terracotta transition-colors">Master Library (24+)</a>
                <a href="#visualizer" class="hover:text-terracotta transition-colors">Blade Angle Visualizer</a>
                <a href="#simulators" class="hover:text-terracotta transition-colors">Cut & Curl Simulator</a>
                <a href="#dish-builder" class="hover:text-terracotta transition-colors">Pairing Engine</a>
                <a href="#hydro-timer" class="hover:text-terracotta transition-colors">Ice Bath Science</a>
            </nav>

            <!-- Notebook Bookmark Button -->
            <button onclick="toggleNotebookModal()" class="relative inline-flex items-center px-4 py-2 rounded-full border border-gold/40 bg-parchment-dark text-forest hover:bg-gold hover:text-white transition-all text-sm font-semibold shadow-sm">
                <i class="fa-solid fa-bookmark mr-2 text-gold hover:text-white"></i>
                <span>Prep Sheet</span>
                <span id="notebook-badge" class="ml-2 bg-terracotta text-white text-xs px-2 py-0.5 rounded-full font-bold">0</span>
            </button>
        </div>
    </header>

    <main class="flex-grow">
        <!-- Hero Section -->
        <section class="hero-banner text-white py-16 md:py-24 px-4 sm:px-6 lg:px-8 relative overflow-hidden">
            <div class="absolute -right-10 -bottom-10 opacity-10 pointer-events-none text-white text-[250px]">
                <i class="fa-solid fa-seedling"></i>
            </div>
            
            <div class="max-w-5xl mx-auto text-center relative z-10">
                <span class="inline-block px-4 py-1.5 rounded-full bg-white/10 backdrop-blur-md text-gold text-xs uppercase tracking-widest font-semibold mb-4 border border-white/20">
                    Exhaustive Culinary Knife Arts & Botanical Presentation
                </span>
                <h1 class="font-serif text-4xl sm:text-6xl md:text-7xl font-bold tracking-tight leading-tight mb-6">
                    Fresh Seasons, <br class="hidden sm:inline"/>
                    <span class="italic font-normal text-gold">Creative Vegetable Garnishing</span>
                </h1>
                <p class="text-stone-200 text-lg sm:text-xl max-w-3xl mx-auto font-light leading-relaxed mb-10">
                    Explore an exhaustive repository of 24+ global and Philippine heritage cuts—from Atchara papaya rosettes and calamansi crowns to precision ice-water curling physics.
                </p>

                <!-- Seasonal & Origin Selector Toolbar -->
                <div class="bg-black/30 backdrop-blur-lg p-3 rounded-2xl max-w-4xl mx-auto border border-white/15 shadow-2xl">
                    <p class="text-xs text-stone-300 font-semibold uppercase tracking-wider mb-2">Select Season Palette</p>
                    <div class="grid grid-cols-2 sm:grid-cols-5 gap-2">
                        <button onclick="setSeason('spring')" id="btn-spring" class="season-btn flex items-center justify-center space-x-2 py-2.5 px-3 rounded-xl font-medium text-xs transition-all bg-white/20 text-white shadow font-bold">
                            <i class="fa-solid fa-seedling text-emerald-300"></i>
                            <span>Spring</span>
                        </button>
                        <button onclick="setSeason('summer')" id="btn-summer" class="season-btn flex items-center justify-center space-x-2 py-2.5 px-3 rounded-xl font-medium text-xs transition-all hover:bg-white/10 text-stone-300">
                            <i class="fa-solid fa-sun text-amber-300"></i>
                            <span>Summer</span>
                        </button>
                        <button onclick="setSeason('autumn')" id="btn-autumn" class="season-btn flex items-center justify-center space-x-2 py-2.5 px-3 rounded-xl font-medium text-xs transition-all hover:bg-white/10 text-stone-300">
                            <i class="fa-solid fa-wheat-awn text-orange-400"></i>
                            <span>Autumn</span>
                        </button>
                        <button onclick="setSeason('winter')" id="btn-winter" class="season-btn flex items-center justify-center space-x-2 py-2.5 px-3 rounded-xl font-medium text-xs transition-all hover:bg-white/10 text-stone-300">
                            <i class="fa-regular fa-snowflake text-sky-300"></i>
                            <span>Winter</span>
                        </button>
                        <button onclick="filterPHGarnishesOnly()" id="btn-ph-only" class="season-btn flex items-center justify-center space-x-2 py-2.5 px-3 rounded-xl font-medium text-xs transition-all border border-amber-400/50 hover:bg-amber-500/20 text-amber-300 col-span-2 sm:col-span-1">
                            <i class="fa-solid fa-sun text-amber-300"></i>
                            <span>🇵🇭 Filipino Arts</span>
                        </button>
                    </div>
                </div>
            </div>
        </section>

        <!-- Philippine & SE Asian Culinary Heritage Spotlight -->
        <section id="heritage" class="bg-parchment-dark py-16 border-b border-stone-200">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="flex flex-col md:flex-row md:items-end justify-between mb-12">
                    <div>
                        <span class="text-terracotta text-sm uppercase font-bold tracking-widest block mb-1">Southeast Asian Heritage</span>
                        <h2 class="font-serif text-3xl sm:text-4xl font-bold text-forest">Philippine Fiesta & Sawsawan Artistry</h2>
                    </div>
                    <p class="text-stone-600 text-sm max-w-md mt-2 md:mt-0">
                        In Philippine gastronomy, garnishes act as sensory activators—balancing rich fatty profiles (*Lechon*, *Crispy Pata*) with acid, heat, and floral beauty.
                    </p>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-4 gap-6">
                    <!-- Feature 1 -->
                    <div class="bg-white p-6 rounded-2xl border border-stone-200/80 shadow-sm">
                        <div class="w-10 h-10 rounded-xl bg-amber-100 text-amber-800 flex items-center justify-center text-lg font-bold mb-4">
                            <i class="fa-solid fa-spa"></i>
                        </div>
                        <h3 class="font-serif text-lg font-bold text-forest mb-2">Atchara Edible Sculptures</h3>
                        <p class="text-stone-600 text-xs leading-relaxed">
                            Hand-carved green papaya, jicama (*singkamas*), and carrots soaked in spiced palm vinegar brine provide crucial visual contrast and digestive acid.
                        </p>
                    </div>

                    <!-- Feature 2 -->
                    <div class="bg-white p-6 rounded-2xl border border-stone-200/80 shadow-sm">
                        <div class="w-10 h-10 rounded-xl bg-emerald-100 text-emerald-800 flex items-center justify-center text-lg font-bold mb-4">
                            <i class="fa-solid fa-lemon"></i>
                        </div>
                        <h3 class="font-serif text-lg font-bold text-forest mb-2">Sawsawan Dual Activation</h3>
                        <p class="text-stone-600 text-xs leading-relaxed">
                            Calamansi star cuts and siling labuyo fire fans are designed to be squeezed or muddled directly into soy-vinegar dipping ramekins.
                        </p>
                    </div>

                    <!-- Feature 3 -->
                    <div class="bg-white p-6 rounded-2xl border border-stone-200/80 shadow-sm">
                        <div class="w-10 h-10 rounded-xl bg-emerald-900 text-emerald-200 flex items-center justify-center text-lg font-bold mb-4">
                            <i class="fa-solid fa-leaf"></i>
                        </div>
                        <h3 class="font-serif text-lg font-bold text-forest mb-2">Dahon ng Saging Lining</h3>
                        <p class="text-stone-600 text-xs leading-relaxed">
                            Warmed banana leaf shapes release aromatic oils while serving as eco-conscious, vibrant green plating foundations for kamayan feasts.
                        </p>
                    </div>

                    <!-- Feature 4 -->
                    <div class="bg-white p-6 rounded-2xl border border-stone-200/80 shadow-sm">
                        <div class="w-10 h-10 rounded-xl bg-amber-900 text-amber-200 flex items-center justify-center text-lg font-bold mb-4">
                            <i class="fa-solid fa-crown"></i>
                        </div>
                        <h3 class="font-serif text-lg font-bold text-forest mb-2">Fiesta Centerpieces</h3>
                        <p class="text-stone-600 text-xs leading-relaxed">
                            Singkamas lotus stars and ampalaya lattices turn humble garden roots into banquet centerpieces for festive celebrations.
                        </p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Master Technique Library (24+ Garnishes) -->
        <section id="library" class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
            <div class="flex flex-col md:flex-row md:items-end justify-between mb-10">
                <div>
                    <span class="text-terracotta text-sm uppercase font-bold tracking-widest block mb-1">Complete Master Collection</span>
                    <h2 class="font-serif text-3xl sm:text-4xl font-bold text-forest">Garnishing Technique Library (24 Cuts)</h2>
                </div>
                <p class="text-stone-600 text-sm max-w-md mt-2 md:mt-0">
                    Comprehensive catalog of vegetable and herb cuts. Filter by origin, technique, season, tool, or difficulty.
                </p>
            </div>

            <!-- Filter Controls Panel -->
            <div class="bg-parchment-dark p-6 rounded-2xl border border-stone-200/80 mb-10 space-y-4 shadow-sm">
                <!-- Search bar & Clear -->
                <div class="flex flex-col sm:flex-row gap-4">
                    <div class="relative flex-1">
                        <i class="fa-solid fa-magnifying-glass absolute left-4 top-1/2 -translate-y-1/2 text-stone-400"></i>
                        <input type="text" id="search-input" onkeyup="filterGarnishes()" placeholder="Search techniques, vegetables, or cuts (e.g., Atchara, Calamansi, Radish, Beetroot)..." class="w-full pl-11 pr-4 py-3 bg-white border border-stone-300 rounded-xl focus:outline-none focus:ring-2 focus:ring-forest text-sm">
                    </div>
                    <button onclick="resetFilters()" class="px-5 py-3 text-stone-600 border border-stone-300 rounded-xl bg-white hover:bg-stone-50 text-sm font-semibold transition-all flex items-center justify-center">
                        <i class="fa-solid fa-rotate-left mr-2 text-xs"></i> Reset Filters
                    </button>
                </div>

                <!-- Tag Filters Dropdowns -->
                <div class="grid grid-cols-2 sm:grid-cols-4 lg:grid-cols-5 gap-3 pt-2">
                    <div>
                        <label class="block text-[11px] uppercase font-bold text-stone-500 mb-1">Cuisine Origin</label>
                        <select id="filter-origin" onchange="filterGarnishes()" class="w-full bg-white border border-stone-300 rounded-lg p-2 text-xs text-stone-700">
                            <option value="all">All Styles</option>
                            <option value="Philippine">Philippine Heritage</option>
                            <option value="East Asian">East Asian</option>
                            <option value="Western">Western Classic</option>
                        </select>
                    </div>

                    <div>
                        <label class="block text-[11px] uppercase font-bold text-stone-500 mb-1">Cutting Technique</label>
                        <select id="filter-tech" onchange="filterGarnishes()" class="w-full bg-white border border-stone-300 rounded-lg p-2 text-xs text-stone-700">
                            <option value="all">All Techniques</option>
                            <option value="Carving">Knife Carving</option>
                            <option value="Ice Curl">Ice Curling</option>
                            <option value="Crisp Fry">Crisp Frying</option>
                            <option value="Pickled">Pickled / Atchara</option>
                            <option value="Leaf Fold">Banana Leaf Folding</option>
                        </select>
                    </div>

                    <div>
                        <label class="block text-[11px] uppercase font-bold text-stone-500 mb-1">Skill Level</label>
                        <select id="filter-skill" onchange="filterGarnishes()" class="w-full bg-white border border-stone-300 rounded-lg p-2 text-xs text-stone-700">
                            <option value="all">All Levels</option>
                            <option value="Beginner">Beginner</option>
                            <option value="Intermediate">Intermediate</option>
                            <option value="Master Carver">Master Carver</option>
                        </select>
                    </div>

                    <div>
                        <label class="block text-[11px] uppercase font-bold text-stone-500 mb-1">Key Knife / Tool</label>
                        <select id="filter-tool" onchange="filterGarnishes()" class="w-full bg-white border border-stone-300 rounded-lg p-2 text-xs text-stone-700">
                            <option value="all">All Tools</option>
                            <option value="Paring Knife">Paring Knife</option>
                            <option value="Thai Knife">Thai Carving Knife</option>
                            <option value="Mandoline">Mandoline / Y-Peeler</option>
                            <option value="Channel Knife">Channel Knife</option>
                        </select>
                    </div>

                    <div class="col-span-2 sm:col-span-1">
                        <label class="block text-[11px] uppercase font-bold text-stone-500 mb-1">Season</label>
                        <select id="filter-season" onchange="filterGarnishes()" class="w-full bg-white border border-stone-300 rounded-lg p-2 text-xs text-stone-700">
                            <option value="all">All Seasons</option>
                            <option value="spring">Spring</option>
                            <option value="summer">Summer</option>
                            <option value="autumn">Autumn</option>
                            <option value="winter">Winter</option>
                        </select>
                    </div>
                </div>
            </div>

            <!-- Garnishes Master Grid (24 Cards) -->
            <div id="garnish-grid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Dynamically Populated by JS -->
            </div>
            
            <div id="no-results" class="hidden text-center py-16 bg-stone-50 rounded-2xl border border-dashed border-stone-300">
                <i class="fa-solid fa-lemon text-4xl text-stone-300 mb-3"></i>
                <h3 class="font-serif text-xl text-stone-700 font-bold">No Cuts Match Your Filter Selection</h3>
                <p class="text-stone-500 text-sm mt-1">Try resetting search parameters or selecting another cuisine origin.</p>
            </div>
        </section>

        <!-- Interactive Blade Angle & Cut Visualizer -->
        <section id="visualizer" class="bg-parchment-dark py-16 border-t border-stone-200">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center max-w-2xl mx-auto mb-12">
                    <span class="text-terracotta text-sm uppercase font-bold tracking-widest block mb-1">Precision Geometry</span>
                    <h2 class="font-serif text-3xl sm:text-4xl font-bold text-forest">Blade Cutting Angle Visualizer</h2>
                    <p class="text-stone-600 text-sm mt-2">
                        Knife entry angle determines vegetable light reflection, surface juice release, and curling elasticity.
                    </p>
                </div>

                <div class="bg-white rounded-2xl shadow-lg border border-stone-200 p-6 sm:p-8">
                    <div class="grid grid-cols-1 lg:grid-cols-3 gap-8 items-center">
                        <div class="space-y-3">
                            <label class="block text-xs uppercase font-bold text-stone-500">Select Blade Entry Geometry</label>
                            
                            <button onclick="setCutAngle('45bias')" id="angle-btn-45bias" class="angle-btn w-full text-left p-3.5 rounded-xl border border-stone-200 hover:border-gold transition-all flex items-center justify-between active-dish">
                                <div>
                                    <div class="font-bold text-sm text-forest">45° Diagonal Bias Cut</div>
                                    <div class="text-xs text-stone-500">Scallion brushes & ginger straws</div>
                                </div>
                                <span class="text-xs font-mono font-bold text-gold">45°</span>
                            </button>

                            <button onclick="setCutAngle('90straight')" id="angle-btn-90straight" class="angle-btn w-full text-left p-3.5 rounded-xl border border-stone-200 hover:border-gold transition-all flex items-center justify-between">
                                <div>
                                    <div class="font-bold text-sm text-forest">90° Perpendicular Round</div>
                                    <div class="text-xs text-stone-500">Radish wheels & citrus stars</div>
                                </div>
                                <span class="text-xs font-mono font-bold text-stone-400">90°</span>
                            </button>

                            <button onclick="setCutAngle('vchisel')" id="angle-btn-vchisel" class="angle-btn w-full text-left p-3.5 rounded-xl border border-stone-200 hover:border-gold transition-all flex items-center justify-between">
                                <div>
                                    <div class="font-bold text-sm text-forest">60° V-Chisel Crown Notch</div>
                                    <div class="text-xs text-stone-500">Calamansi crowns & tomato lotus</div>
                                </div>
                                <span class="text-xs font-mono font-bold text-stone-400">60° V</span>
                            </button>

                            <button onclick="setCutAngle('flute')" id="angle-btn-flute" class="angle-btn w-full text-left p-3.5 rounded-xl border border-stone-200 hover:border-gold transition-all flex items-center justify-between">
                                <div>
                                    <div class="font-bold text-sm text-forest">Channel Fluting Grooves</div>
                                    <div class="text-xs text-stone-500">Cucumber wheels & carrot stars</div>
                                </div>
                                <span class="text-xs font-mono font-bold text-stone-400">Channel</span>
                            </button>
                        </div>

                        <!-- Vector Geometry Visualizer Canvas -->
                        <div class="lg:col-span-2 bg-stone-900 rounded-2xl h-72 p-6 flex flex-col justify-between relative overflow-hidden border border-stone-800">
                            <div class="flex items-center justify-between text-xs text-stone-400 font-mono">
                                <span>KNIFE VECTOR SIMULATOR</span>
                                <span id="angle-degree-label" class="text-gold font-bold">ENTRY: 45° BIAS</span>
                            </div>

                            <div class="flex-grow flex items-center justify-center">
                                <svg id="angle-svg" viewBox="0 0 400 160" class="w-full h-full max-h-48">
                                    <!-- Dynamic SVG Content rendered by JS -->
                                </svg>
                            </div>

                            <div class="bg-white/10 backdrop-blur-md p-3 rounded-xl border border-white/10 text-xs text-stone-200">
                                <strong class="text-gold block mb-0.5" id="angle-physics-title">Physics Impact: Surface Area Expansion</strong>
                                <p id="angle-physics-desc" class="text-stone-300 font-light">Diagonal cuts expose 40% more vascular surface area, accelerating water absorption during ice-bath curling.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Interactive Cutting & Curling Simulator -->
        <section id="simulators" class="py-16 border-t border-stone-200">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center max-w-2xl mx-auto mb-12">
                    <span class="text-terracotta text-sm uppercase font-bold tracking-widest block mb-1">Cellular Physics</span>
                    <h2 class="font-serif text-3xl sm:text-4xl font-bold text-forest">Interactive Cut & Curl Simulator</h2>
                    <p class="text-stone-600 text-sm mt-2">
                        Simulate how slice thickness and water soak duration physically curl scallions, chili fans, and radish blossoms.
                    </p>
                </div>

                <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
                    <!-- Simulator 1 -->
                    <div class="bg-white p-6 sm:p-8 rounded-2xl shadow-md border border-stone-200 flex flex-col justify-between">
                        <div>
                            <div class="flex items-center justify-between mb-4">
                                <h3 class="font-serif text-xl font-bold text-forest">Ribbon Elasticity (Scallion & Labuyo)</h3>
                                <span class="bg-emerald-100 text-emerald-800 text-xs px-2.5 py-1 rounded-full font-bold">Curling Physics</span>
                            </div>
                            <p class="text-stone-600 text-xs mb-6">Adjust slice thickness to observe how cut depth impacts spiral tension in sub-zero water.</p>
                            
                            <div class="bg-stone-900 rounded-xl h-48 relative overflow-hidden flex items-center justify-center p-4">
                                <svg id="scallion-svg" class="w-full h-full" viewBox="0 0 300 150">
                                    <path id="scallion-path" d="M 30,75 Q 100,75 150,75 T 270,75" fill="none" stroke="#4ade80" stroke-width="6" stroke-linecap="round"/>
                                    <path id="scallion-path-inner" d="M 30,75 Q 100,75 150,75 T 270,75" fill="none" stroke="#86efac" stroke-width="2" stroke-linecap="round"/>
                                </svg>
                                <div class="absolute bottom-3 left-4 text-xs font-mono text-stone-400">
                                    Simulated Cut: <span id="cut-value-label" class="text-gold font-bold">0.5 mm</span>
                                </div>
                            </div>
                        </div>

                        <div class="mt-6 space-y-4">
                            <div>
                                <div class="flex justify-between text-xs font-semibold text-stone-700 mb-2">
                                    <span>Slice Thickness (mm)</span>
                                    <span id="thickness-val">0.5 mm (Micro Thin)</span>
                                </div>
                                <input type="range" id="thickness-range" min="0.1" max="2.0" step="0.1" value="0.5" oninput="updateScallionSim()" class="w-full accent-forest cursor-pointer">
                            </div>
                        </div>
                    </div>

                    <!-- Simulator 2 -->
                    <div class="bg-white p-6 sm:p-8 rounded-2xl shadow-md border border-stone-200 flex flex-col justify-between">
                        <div>
                            <div class="flex items-center justify-between mb-4">
                                <h3 class="font-serif text-xl font-bold text-forest">Radish & Singkamas Lotus Bloom</h3>
                                <span class="bg-amber-100 text-amber-800 text-xs px-2.5 py-1 rounded-full font-bold">Hydration Expansion</span>
                            </div>
                            <p class="text-stone-600 text-xs mb-6">Simulate soak time to watch scored vegetable layers unfurl into full floral centerpieces.</p>
                            
                            <div class="bg-stone-900 rounded-xl h-48 relative overflow-hidden flex items-center justify-center p-4">
                                <svg id="radish-svg" class="w-44 h-44" viewBox="-100 -100 200 200">
                                    <circle cx="0" cy="0" r="18" fill="#f87171" />
                                    <g id="radish-petals"></g>
                                </svg>
                                <div class="absolute bottom-3 left-4 text-xs font-mono text-stone-400">
                                    Expansion Bloom: <span id="bloom-percent" class="text-gold font-bold">0%</span>
                                </div>
                            </div>
                        </div>

                        <div class="mt-6 space-y-4">
                            <div>
                                <div class="flex justify-between text-xs font-semibold text-stone-700 mb-2">
                                    <span>Ice Bath Immersion Time</span>
                                    <span id="time-val">0 Minutes</span>
                                </div>
                                <input type="range" id="bloom-range" min="0" max="30" step="1" value="0" oninput="updateRadishSim()" class="w-full accent-terracotta cursor-pointer">
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Dish & Sawsawan Pairing Calculator (12 Dishes) -->
        <section id="dish-builder" class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
            <div class="text-center max-w-2xl mx-auto mb-12">
                <span class="text-terracotta text-sm uppercase font-bold tracking-widest block mb-1">Plating Architecture</span>
                <h2 class="font-serif text-3xl sm:text-4xl font-bold text-forest">Filipino & Global Dish Pairing Calculator</h2>
                <p class="text-stone-600 text-sm mt-2">
                    Select an iconic dish to unlock ideal garnishing textures, sawsawan pairing logic, and color contrast scoring.
                </p>
            </div>

            <div class="bg-white rounded-2xl shadow-lg border border-stone-200/80 overflow-hidden">
                <div class="grid grid-cols-1 lg:grid-cols-3 divide-y lg:divide-y-0 lg:divide-x divide-stone-200">
                    <!-- Dish Selector (12 Dishes) -->
                    <div class="p-6 bg-stone-50/70 max-h-[600px] overflow-y-auto">
                        <span class="text-[10px] font-bold text-gold uppercase tracking-wider block mb-2">Select Culinary Canvas (12 Options)</span>
                        <div class="space-y-2" id="dish-selector-group">
                            <button onclick="selectDish('lechon')" class="dish-opt active-dish w-full text-left p-3 rounded-xl border border-stone-200 bg-white hover:border-gold transition-all flex items-center space-x-3">
                                <div class="w-8 h-8 rounded-full bg-amber-100 text-amber-700 flex items-center justify-center shrink-0 text-xs">
                                    <i class="fa-solid fa-drumstick-bite"></i>
                                </div>
                                <div class="text-xs font-semibold text-stone-800">Lechon & Pork Liempo</div>
                            </button>

                            <button onclick="selectDish('sinigang')" class="dish-opt w-full text-left p-3 rounded-xl border border-stone-200 bg-white hover:border-gold transition-all flex items-center space-x-3">
                                <div class="w-8 h-8 rounded-full bg-orange-100 text-orange-600 flex items-center justify-center shrink-0 text-xs">
                                    <i class="fa-solid fa-bowl-food"></i>
                                </div>
                                <div class="text-xs font-semibold text-stone-800">Sinigang na Baboy / Salmon</div>
                            </button>

                            <button onclick="selectDish('palabok')" class="dish-opt w-full text-left p-3 rounded-xl border border-stone-200 bg-white hover:border-gold transition-all flex items-center space-x-3">
                                <div class="w-8 h-8 rounded-full bg-yellow-100 text-yellow-700 flex items-center justify-center shrink-0 text-xs">
                                    <i class="fa-solid fa-utensils"></i>
                                </div>
                                <div class="text-xs font-semibold text-stone-800">Pancit Palabok / Bihon</div>
                            </button>

                            <button onclick="selectDish('karekare')" class="dish-opt w-full text-left p-3 rounded-xl border border-stone-200 bg-white hover:border-gold transition-all flex items-center space-x-3">
                                <div class="w-8 h-8 rounded-full bg-amber-200 text-amber-900 flex items-center justify-center shrink-0 text-xs">
                                    <i class="fa-solid fa-layer-group"></i>
                                </div>
                                <div class="text-xs font-semibold text-stone-800">Kare-Kare Peanut Stew</div>
                            </button>

                            <button onclick="selectDish('kinilaw')" class="dish-opt w-full text-left p-3 rounded-xl border border-stone-200 bg-white hover:border-gold transition-all flex items-center space-x-3">
                                <div class="w-8 h-8 rounded-full bg-sky-100 text-sky-700 flex items-center justify-center shrink-0 text-xs">
                                    <i class="fa-solid fa-fish"></i>
                                </div>
                                <div class="text-xs font-semibold text-stone-800">Kinilaw na Tanigue / Tuna</div>
                            </button>

                            <button onclick="selectDish('inasal')" class="dish-opt w-full text-left p-3 rounded-xl border border-stone-200 bg-white hover:border-gold transition-all flex items-center space-x-3">
                                <div class="w-8 h-8 rounded-full bg-red-100 text-red-600 flex items-center justify-center shrink-0 text-xs">
                                    <i class="fa-solid fa-fire"></i>
                                </div>
                                <div class="text-xs font-semibold text-stone-800">Chicken Inasal</div>
                            </button>

                            <button onclick="selectDish('pata')" class="dish-opt w-full text-left p-3 rounded-xl border border-stone-200 bg-white hover:border-gold transition-all flex items-center space-x-3">
                                <div class="w-8 h-8 rounded-full bg-stone-200 text-stone-700 flex items-center justify-center shrink-0 text-xs">
                                    <i class="fa-solid fa-bone"></i>
                                </div>
                                <div class="text-xs font-semibold text-stone-800">Crispy Pata</div>
                            </button>

                            <button onclick="selectDish('arrozcaldo')" class="dish-opt w-full text-left p-3 rounded-xl border border-stone-200 bg-white hover:border-gold transition-all flex items-center space-x-3">
                                <div class="w-8 h-8 rounded-full bg-yellow-100 text-yellow-800 flex items-center justify-center shrink-0 text-xs">
                                    <i class="fa-solid fa-mug-hot"></i>
                                </div>
                                <div class="text-xs font-semibold text-stone-800">Arroz Caldo Porridge</div>
                            </button>

                            <button onclick="selectDish('lumpia')" class="dish-opt w-full text-left p-3 rounded-xl border border-stone-200 bg-white hover:border-gold transition-all flex items-center space-x-3">
                                <div class="w-8 h-8 rounded-full bg-emerald-100 text-emerald-800 flex items-center justify-center shrink-0 text-xs">
                                    <i class="fa-solid fa-scroll"></i>
                                </div>
                                <div class="text-xs font-semibold text-stone-800">Lumpia Shanghai</div>
                            </button>

                            <button onclick="selectDish('sisig')" class="dish-opt w-full text-left p-3 rounded-xl border border-stone-200 bg-white hover:border-gold transition-all flex items-center space-x-3">
                                <div class="w-8 h-8 rounded-full bg-red-200 text-red-900 flex items-center justify-center shrink-0 text-xs">
                                    <i class="fa-solid fa-pepper-hot"></i>
                                </div>
                                <div class="text-xs font-semibold text-stone-800">Sizzling Pork Sisig</div>
                            </button>

                            <button onclick="selectDish('bistek')" class="dish-opt w-full text-left p-3 rounded-xl border border-stone-200 bg-white hover:border-gold transition-all flex items-center space-x-3">
                                <div class="w-8 h-8 rounded-full bg-purple-100 text-purple-800 flex items-center justify-center shrink-0 text-xs">
                                    <i class="fa-solid fa-ring"></i>
                                </div>
                                <div class="text-xs font-semibold text-stone-800">Bistek Tagalog</div>
                            </button>

                            <button onclick="selectDish('bulalo')" class="dish-opt w-full text-left p-3 rounded-xl border border-stone-200 bg-white hover:border-gold transition-all flex items-center space-x-3">
                                <div class="w-8 h-8 rounded-full bg-stone-300 text-stone-900 flex items-center justify-center shrink-0 text-xs">
                                    <i class="fa-solid fa-cloud-meatball"></i>
                                </div>
                                <div class="text-xs font-semibold text-stone-800">Beef Bulalo Soup</div>
                            </button>
                        </div>
                    </div>

                    <!-- Pairing Details Display -->
                    <div class="lg:col-span-2 p-6 sm:p-8 flex flex-col justify-between">
                        <div>
                            <div class="flex items-center justify-between pb-4 border-b border-stone-200 mb-6">
                                <div>
                                    <span class="text-[10px] font-bold text-gold uppercase tracking-wider block">Recommended Plating Setup</span>
                                    <h3 id="recommendation-title" class="font-serif text-2xl font-bold text-forest">Garnishes for Lechon & Pork Liempo</h3>
                                </div>
                                <span id="current-season-badge" class="px-3 py-1 bg-forest/10 text-forest text-xs rounded-full font-bold uppercase tracking-wider">SPRING PALETTE</span>
                            </div>

                            <div id="recommendations-container" class="space-y-4">
                                <!-- Populated dynamically by JS -->
                            </div>
                        </div>

                        <div class="mt-8 pt-4 border-t border-stone-200 flex flex-col sm:flex-row items-start sm:items-center justify-between text-xs text-stone-500 gap-2">
                            <span><i class="fa-solid fa-lightbulb text-gold mr-1"></i> Balance rule: Rich Filipino proteins demand active acid relief & vibrant crunchy relief.</span>
                            <span class="font-bold text-terracotta">Plating Score: 98/100 Perfect Pair</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Ice Bath Science Timer -->
        <section id="hydro-timer" class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
            <div class="bg-forest text-white rounded-3xl p-8 sm:p-12 relative overflow-hidden shadow-2xl">
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-10 items-center relative z-10">
                    <div>
                        <span class="text-gold text-xs uppercase tracking-widest font-bold block mb-2">Hydro-Cellular Physics</span>
                        <h2 class="font-serif text-3xl sm:text-5xl font-bold leading-tight mb-4">
                            The Ice Water Transformation
                        </h2>
                        <p class="text-stone-300 text-sm leading-relaxed mb-6 font-light">
                            Submerging sliced plant tissues in 0°C ice water forces water into damaged cell vacuoles via rapid osmosis. Epidermal skin layer contracts while inner vascular tubes swell, inducing natural architectural curling.
                        </p>
                    </div>

                    <div class="bg-white text-stone-800 p-6 sm:p-8 rounded-2xl shadow-xl">
                        <div class="flex items-center justify-between mb-4">
                            <h3 class="font-serif text-xl font-bold text-forest">Crisping & Curling Hydro-Timer</h3>
                            <i class="fa-solid fa-stopwatch text-terracotta text-2xl"></i>
                        </div>

                        <div class="mb-4">
                            <label class="block text-xs uppercase font-bold text-stone-500 mb-1">Select Cut Cuticle Type</label>
                            <select id="timer-veg-select" onchange="updateTimerPreset()" class="w-full border border-stone-300 rounded-lg p-2.5 text-sm">
                                <option value="10">Scallion Curls & Brushes (10 mins)</option>
                                <option value="12">Siling Labuyo Fire Crowns (12 mins)</option>
                                <option value="15">Radish & Tomato Blooms (15 mins)</option>
                                <option value="18">Kinudkod Green Mango Strips (18 mins)</option>
                                <option value="20">Singkamas Lotus Stars (20 mins)</option>
                                <option value="25">Carrot Lotus Wheels (25 mins)</option>
                            </select>
                        </div>

                        <div class="bg-stone-900 text-gold font-mono rounded-xl p-6 text-center text-4xl sm:text-5xl font-bold tracking-widest mb-6 shadow-inner">
                            <span id="timer-display">10:00</span>
                        </div>

                        <div class="grid grid-cols-2 gap-3">
                            <button id="timer-start-btn" onclick="toggleTimer()" class="w-full bg-forest text-white py-3 rounded-xl font-semibold hover:bg-forest/90 transition-all text-sm flex items-center justify-center">
                                <i class="fa-solid fa-play mr-2"></i> <span id="start-btn-text">Start Ice Bath</span>
                            </button>
                            <button onclick="resetTimer()" class="w-full bg-stone-200 text-stone-700 py-3 rounded-xl font-semibold hover:bg-stone-300 transition-all text-sm flex items-center justify-center">
                                <i class="fa-solid fa-rotate-right mr-2"></i> Reset
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Technique Detail Modal -->
    <div id="detail-modal" class="fixed inset-0 bg-black/60 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4 overflow-y-auto">
        <div class="bg-white rounded-3xl max-w-3xl w-full max-h-[90vh] overflow-y-auto shadow-2xl border border-gold/20 relative">
            <div class="sticky top-0 bg-white border-b border-stone-200 px-6 py-4 flex items-center justify-between z-10">
                <div class="flex items-center space-x-2">
                    <span id="modal-skill-badge" class="px-3 py-0.5 rounded-full text-xs font-bold bg-emerald-100 text-emerald-800">Intermediate</span>
                    <span id="modal-veg-type" class="text-xs uppercase font-bold text-stone-400">Green Papaya Cut</span>
                    <span id="modal-origin-badge" class="text-xs font-bold px-2 py-0.5 rounded bg-amber-100 text-amber-800">Philippine Heritage</span>
                </div>
                <button onclick="closeModal()" class="w-8 h-8 rounded-full bg-stone-100 hover:bg-stone-200 flex items-center justify-center text-stone-600 transition-colors">
                    <i class="fa-solid fa-xmark"></i>
                </button>
            </div>

            <div class="p-6 sm:p-8 space-y-6">
                <div>
                    <h2 id="modal-title" class="font-serif text-3xl font-bold text-forest mb-2">Papaya Atchara Rosette</h2>
                    <p id="modal-desc" class="text-stone-600 text-sm leading-relaxed">Carved green papaya petals quick-pickled to create a crisp, ornate flower centerpiece.</p>
                </div>

                <div id="modal-svg-container" class="w-full h-48 bg-stone-900 rounded-2xl flex items-center justify-center p-4 overflow-hidden border border-stone-800">
                    <!-- Dynamic SVG inserted here -->
                </div>

                <div>
                    <h3 class="font-serif text-xl font-bold text-forest mb-3">Step-by-Step Knife Instructions</h3>
                    <ol id="modal-steps-list" class="space-y-2 text-sm text-stone-700 list-decimal list-inside">
                        <!-- Populated by JS -->
                    </ol>
                </div>

                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 pt-4 border-t border-stone-100">
                    <div class="bg-amber-50/70 p-4 rounded-xl border border-amber-200/60">
                        <strong class="text-xs uppercase tracking-wider text-amber-800 font-bold block mb-1"><i class="fa-solid fa-utensils mr-1"></i> Plating & Dish Pairings</strong>
                        <p id="modal-pairing" class="text-xs text-stone-700 leading-relaxed"></p>
                    </div>

                    <div class="bg-emerald-50/70 p-4 rounded-xl border border-emerald-200/60">
                        <strong class="text-xs uppercase tracking-wider text-emerald-800 font-bold block mb-1"><i class="fa-solid fa-lightbulb mr-1"></i> Executive Chef Science Tip</strong>
                        <p id="modal-tip" class="text-xs text-stone-700 leading-relaxed"></p>
                    </div>
                </div>
            </div>

            <div class="bg-stone-50 px-6 py-4 border-t border-stone-200 flex items-center justify-between">
                <button id="modal-bookmark-btn" onclick="" class="px-4 py-2 rounded-xl bg-forest text-white hover:bg-forest/90 text-sm font-semibold transition-all flex items-center">
                    <i class="fa-solid fa-bookmark mr-2"></i> Save to Prep Sheet
                </button>
                <button onclick="closeModal()" class="px-4 py-2 rounded-xl border border-stone-300 text-stone-600 hover:bg-stone-100 text-sm font-semibold">Close</button>
            </div>
        </div>
    </div>

    <!-- Culinary Notebook & Printable Chef Cheat Sheet -->
    <div id="notebook-modal" class="fixed inset-0 bg-black/60 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">
        <div class="bg-white rounded-3xl max-w-2xl w-full max-h-[85vh] flex flex-col shadow-2xl border border-gold/20 overflow-hidden">
            <div class="bg-parchment-dark px-6 py-5 border-b border-stone-200 flex items-center justify-between">
                <div class="flex items-center space-x-2">
                    <i class="fa-solid fa-book-open text-terracotta text-xl"></i>
                    <h2 class="font-serif text-2xl font-bold text-forest">Chef's Kitchen Prep Sheet</h2>
                </div>
                <button onclick="toggleNotebookModal()" class="w-8 h-8 rounded-full bg-stone-200 flex items-center justify-center text-stone-600 no-print">
                    <i class="fa-solid fa-xmark"></i>
                </button>
            </div>

            <div class="p-6 overflow-y-auto flex-grow space-y-4">
                <p class="text-xs text-stone-500">Bookmarked garnishing cuts compiled into a printable reference sheet for line cooks and chefs.</p>
                <div id="notebook-items-container" class="space-y-3">
                    <!-- Populated dynamically -->
                </div>
            </div>

            <div class="bg-stone-50 p-4 border-t border-stone-200 flex justify-between items-center no-print">
                <button onclick="clearNotebook()" class="text-xs text-red-600 font-semibold hover:underline">Clear List</button>
                <button onclick="window.print()" class="px-5 py-2.5 bg-gold text-white rounded-xl text-sm font-bold shadow hover:bg-gold-hover transition-all flex items-center">
                    <i class="fa-solid fa-print mr-2"></i> Print Chef's Cheat Sheet
                </button>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer class="bg-forest text-stone-300 py-12 border-t border-stone-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col sm:flex-row items-center justify-between gap-4">
            <div class="flex items-center space-x-3">
                <div class="w-8 h-8 rounded-full bg-gold text-forest flex items-center justify-center font-serif font-bold">
                    <i class="fa-solid fa-leaf"></i>
                </div>
                <span class="font-serif text-lg font-bold text-white">Fresh Seasons Master Repository</span>
            </div>
            <p class="text-xs text-stone-400">© 2026 Executive Culinary Arts & Southeast Asian Heritage Repository.</p>
        </div>
    </footer>

    <script>
        // MASTER COLLECTION OF 24+ GARNISHES
        const garnishesData = [
            // PHILIPPINE & SE ASIAN HERITAGE (12 CUTS)
            {
                id: 'atchara-rosette',
                title: 'Papaya Atchara Ribbon Rosette',
                season: 'spring',
                origin: 'Philippine',
                tech: 'Pickled',
                skill: 'Master Carver',
                tool: 'Thai Knife',
                veg: 'Green Papaya',
                desc: 'Green papaya hand-carved into concentric petal layers and pickled in sweet palm vinegar brine.',
                steps: [
                    'Peel firm raw green papaya and carve a 2-inch cylindrical center cylinder.',
                    'Using a flexible Thai knife, slice shallow overlapping outer petal grooves.',
                    'Step inward 3mm and carve alternating inner rosette petals.',
                    'Salt for 10 mins, wring out excess water, and steep in warm Atchara vinegar brine.'
                ],
                pairing: 'Lechon Kawali, Grilled Pork Liempo, Chicken Inasal.',
                tip: 'Salting raw papaya draws out water so the petals lock in crisp transparency after pickling.',
                svg: `<svg viewBox="-50 -50 100 100" class="w-28 h-28"><circle cx="0" cy="0" r="42" fill="#84cc16"/><circle cx="0" cy="0" r="32" fill="#a3e635"/><circle cx="0" cy="0" r="22" fill="#bef264"/><circle cx="0" cy="0" r="12" fill="#fef08a"/></svg>`
            },
            {
                id: 'calamansi-crown',
                title: 'Calamansi Crown & Star Cut',
                season: 'summer',
                origin: 'Philippine',
                tech: 'Carving',
                skill: 'Beginner',
                tool: 'Paring Knife',
                veg: 'Calamansi',
                desc: 'Equatorial V-notch saw-cut native Calamansi, enabling dual presentation and easy squeezing over dipping sauce.',
                steps: [
                    'Select firm dark green Calamansi citrus fruit.',
                    'Insert paring knife tip at a 45° angle directly into the equator center line.',
                    'Make alternating 60° V-cuts around the entire circumference.',
                    'Gently pull apart twin serrated Calamansi crowns.'
                ],
                pairing: 'Pancit Palabok, Bistek Tagalog, Grilled Tuna Belly, Sawsawan.',
                tip: 'Slice straight through the equatorial line so seeds pop free automatically.',
                svg: `<svg viewBox="0 0 100 100" class="w-28 h-28"><circle cx="50" cy="50" r="38" fill="#15803d"/><polygon points="50,15 58,35 78,35 62,48 68,68 50,55 32,68 38,48 22,35 42,35" fill="#facc15"/></svg>`
            },
            {
                id: 'siling-labuyo-crown',
                title: 'Siling Labuyo Dragon Fire Crown',
                season: 'summer',
                origin: 'Philippine',
                tech: 'Ice Curl',
                skill: 'Intermediate',
                tool: 'Paring Knife',
                veg: 'Siling Labuyo',
                desc: 'Native bird’s eye chili sliced into fine longitudinal tentacles that flare out into a dragon crown in sub-zero water.',
                steps: [
                    'Keep green stem attached on red Siling Labuyo pepper.',
                    'Make 6 to 10 fine longitudinal slit cuts up toward stem base.',
                    'Scrape out internal seeds using a toothpick.',
                    'Submerge in ice bath for 12 mins until tentacles curl outward.'
                ],
                pairing: 'Sinigang na Baboy, Bicol Express, Kinilaw, Sizzling Sisig.',
                tip: 'Ice water tames explosive surface oil heat while locking tentacles in a flared posture.',
                svg: `<svg viewBox="0 0 100 100" class="w-28 h-28"><path d="M50,10 L50,90 M25,85 L50,10 L75,85 M10,65 L50,10 L90,65" stroke="#ef4444" stroke-width="5" stroke-linecap="round"/></svg>`
            },
            {
                id: 'kinudkod-mango-blossom',
                title: 'Kinudkod Green Mango Blossom',
                season: 'summer',
                origin: 'Philippine',
                tech: 'Carving',
                skill: 'Intermediate',
                tool: 'Mandoline',
                veg: 'Green Mango',
                desc: 'Paper-thin ribbons of tart green mango rolled into a tart, refreshing floral rosette.',
                steps: [
                    'Peel tart green mango and shave 1mm translucent ribbons.',
                    'Soak ribbons in light saltwater for 5 minutes for flexibility.',
                    'Roll first ribbon into a tight core, then layer outer ribbons into a blossom.',
                    'Anchor with toothpick or rest inside sawsawan dish.'
                ],
                pairing: 'Bagoong Alamang dip, Crispy Pata, Fried Tilapia.',
                tip: 'Light salting makes stiff mango fibers pliable enough to coil without snapping.',
                svg: `<svg viewBox="0 0 100 100" class="w-28 h-28"><ellipse cx="50" cy="50" rx="35" ry="25" fill="#bef264" transform="rotate(-20 50 50)"/><ellipse cx="50" cy="50" rx="25" ry="15" fill="#a3e635" transform="rotate(20 50 50)"/></svg>`
            },
            {
                id: 'sibuyas-star',
                title: 'Sibuyas Tagalog Ribbon Star',
                season: 'autumn',
                origin: 'Philippine',
                tech: 'Ice Curl',
                skill: 'Beginner',
                tool: 'Paring Knife',
                veg: 'Red Onion',
                desc: 'Concentric native red onion rings cut into crisp star gears, adding sharp color to savory braises.',
                steps: [
                    'Peel outer paper skin of small red onion or shallot.',
                    'Slice crosswise into 4mm thick solid rings.',
                    'Separate individual rings gently.',
                    'Soak in cold ice-vinegar water for 10 mins to remove raw pungency and pop violet color.'
                ],
                pairing: 'Bistek Tagalog, Tokwa’t Baboy, Ensaladang Talong.',
                tip: 'Cold vinegar bath transforms dull onion purple into bright magenta.',
                svg: `<svg viewBox="0 0 100 100" class="w-28 h-28"><circle cx="50" cy="50" r="35" fill="none" stroke="#7e22ce" stroke-width="6"/><circle cx="50" cy="50" r="22" fill="none" stroke="#a855f7" stroke-width="4"/><circle cx="50" cy="50" r="10" fill="#e9d5ff"/></svg>`
            },
            {
                id: 'garlic-flake-crown',
                title: 'Crispy Garlic Flake Golden Crown',
                season: 'winter',
                origin: 'Philippine',
                tech: 'Crisp Fry',
                skill: 'Beginner',
                tool: 'Mandoline',
                veg: 'Garlic',
                desc: 'Mandoline-sliced garlic cloves fried into golden translucent chips arranged into a crown.',
                steps: [
                    'Slice garlic cloves uniformly to 1mm thickness.',
                    'Rinse in cold water for 3 mins to wash off sticky sugars.',
                    'Fry gently in warm oil (150°C) until light golden straw.',
                    'Drain on paper towels and build a golden crown over porridge or rice.'
                ],
                pairing: 'Pancit Palabok, Arroz Caldo, Sinangag Garlic Rice, Beef Pares.',
                tip: 'Pull garlic out of oil 5 seconds early as residual heat completes browning.',
                svg: `<svg viewBox="0 0 100 100" class="w-28 h-28"><circle cx="50" cy="50" r="30" fill="#d97706"/><circle cx="50" cy="50" r="20" fill="#f59e0b"/><circle cx="50" cy="50" r="10" fill="#fef3c7"/></svg>`
            },
            {
                id: 'ampalaya-lattice',
                title: 'Ampalaya Emerald Lattice Ribbons',
                season: 'spring',
                origin: 'Philippine',
                tech: 'Carving',
                skill: 'Master Carver',
                tool: 'Thai Knife',
                veg: 'Bitter Gourd',
                desc: 'Deseeded bitter melon sliced into delicate translucent mesh lattices that offer textural crunch.',
                steps: [
                    'Halve bitter melon lengthwise and scoop out white inner pith completely.',
                    'Slice 1mm diagonal ribbons down the length.',
                    'Blanch in boiling salt water for 8 seconds, then shock in ice water.',
                    'Arrange into emerald lattice waves across roasted meats.'
                ],
                pairing: 'Ginisang Ampalaya with Egg, Crispy Pork Barbecue, Fried Fish.',
                tip: 'Scooping out all white pith and quick blanching removes harsh bitterness while locking in emerald green color.',
                svg: `<svg viewBox="0 0 100 100" class="w-28 h-28"><rect x="15" y="25" width="70" height="50" rx="10" fill="none" stroke="#15803d" stroke-width="4"/><line x1="25" y1="25" x2="75" y2="75" stroke="#22c55e" stroke-width="3"/><line x1="75" y1="25" x2="25" y2="75" stroke="#22c55e" stroke-width="3"/></svg>`
            },
            {
                id: 'singkamas-lotus',
                title: 'Singkamas Snowflake Lotus Star',
                season: 'winter',
                origin: 'Philippine',
                tech: 'Carving',
                skill: 'Intermediate',
                tool: 'Paring Knife',
                veg: 'Jicama',
                desc: 'Crisp white jicama root hand-carved into an intricate snowflake lotus star centerpiece.',
                steps: [
                    'Peel jicama and slice a 1/2-inch thick round wheel.',
                    'Carve 6 symmetrical V-notch wedge cuts around outer rim.',
                    'Feather internal petal grooves using tip of paring knife.',
                    'Chill in ice water bath for 20 mins until starch firms into porcelain white posture.'
                ],
                pairing: 'Fresh Lumpia Ubos, Kinilaw na Tanigue, Fruit Platters.',
                tip: 'Jicama retains crisp structural geometry for over 24 hours when kept refrigerated in water.',
                svg: `<svg viewBox="0 0 100 100" class="w-28 h-28"><polygon points="50,10 62,35 88,35 68,52 75,78 50,62 25,78 32,52 12,35 38,35" fill="#f8fafc" stroke="#cbd5e1" stroke-width="2"/></svg>`
            },
            {
                id: 'kamatis-rose',
                title: 'Kamatis Rose Peel & Lotus Bloom',
                season: 'summer',
                origin: 'Philippine',
                tech: 'Carving',
                skill: 'Intermediate',
                tool: 'Paring Knife',
                veg: 'Tomato',
                desc: 'Continuous unbroken tomato skin peel coiled tightly into a glossy red floral rose.',
                steps: [
                    'Peel tomato skin in one continuous 1/2-inch wide strip from stem to base.',
                    'Lay skin peel skin-side down on cutting board.',
                    'Roll tightly from stem end to tail end into a spiral cylinder.',
                    'Flip upright and open outer skin folds to form a rose bloom.'
                ],
                pairing: 'Ensaladang Mangga’t Kamatis, Salted Egg platters, Fried Tilapia.',
                tip: 'Use a razor-sharp serrated or paring knife so tomato skin does not tear.',
                svg: `<svg viewBox="0 0 100 100" class="w-28 h-28"><circle cx="50" cy="50" r="35" fill="#dc2626"/><path d="M50,15 A35,35 0 0,1 85,50 A25,25 0 0,1 60,75 A15,15 0 0,1 45,60" fill="none" stroke="#fca5a5" stroke-width="4"/></svg>`
            },
            {
                id: 'banana-leaf-boat',
                title: 'Banana Leaf Origami Base & Ring',
                season: 'spring',
                origin: 'Philippine',
                tech: 'Leaf Fold',
                skill: 'Beginner',
                tool: 'Paring Knife',
                veg: 'Banana Leaf',
                desc: 'Flame-warmed banana leaf folded into an origami serving boat or round platter lining.',
                steps: [
                    'Pass fresh banana leaf over open flame for 3 seconds to make it supple.',
                    'Cut 6-inch round circles or rectangular strips.',
                    'Pinch corners and pin with toothpick to form an organic plate base.',
                    'Lightly wipe with coconut oil for glossy tropical sheen.'
                ],
                pairing: 'Kamayan feasts, Lechon platters, Inasal, Rice bowls.',
                tip: 'Warming over open flame melts natural leaf wax, releasing herbal scent and preventing tearing.',
                svg: `<svg viewBox="0 0 100 100" class="w-28 h-28"><path d="M10,50 Q50,10 90,50 Q50,90 10,50 Z" fill="#15803d" stroke="#86efac" stroke-width="2"/></svg>`
            },
            {
                id: 'keso-egg-crown',
                title: 'Kesong Puti & Salted Egg Crumble Crown',
                season: 'autumn',
                origin: 'Philippine',
                tech: 'Carving',
                skill: 'Beginner',
                tool: 'Paring Knife',
                veg: 'Carabao Cheese',
                desc: 'Diced native carabao cheese paired with salted duck egg yolk crumbles for contrast atop vegetables.',
                steps: [
                    'Cube fresh Kesong Puti into neat 4mm micro cubes.',
                    'Crumble cured salted egg yolk into golden granules.',
                    'Ring outer edge with chopped scallions and tomato dices.',
                    'Mound neatly over hot grilled eggplant or rice.'
                ],
                pairing: 'Ensaladang Talong, Bibingka, Pancit Malabon, Lugaw.',
                tip: 'Chill carabao cheese before dicing to maintain clean geometric edges.',
                svg: `<svg viewBox="0 0 100 100" class="w-28 h-28"><rect x="25" y="25" width="22" height="22" fill="#fef08a"/><rect x="53" y="25" width="22" height="22" fill="#ea580c"/><rect x="25" y="53" width="22" height="22" fill="#ea580c"/><rect x="53" y="53" width="22" height="22" fill="#fef08a"/></svg>`
            },
            {
                id: 'lemongrass-fan',
                title: 'Lemongrass Stalk Fan & Herb Spear',
                season: 'summer',
                origin: 'Philippine',
                tech: 'Carving',
                skill: 'Beginner',
                tool: 'Paring Knife',
                veg: 'Lemongrass',
                desc: 'Bruised lemongrass root split into fine skewers that infuse broths while serving as a aromatic stirrer.',
                steps: [
                    'Trim outer tough woody leaves from lemongrass base stalk.',
                    'Lightly bruise bulb end with knife spine to release citrus oils.',
                    'Slice top stalk into fine longitudinal fan slits.',
                    'Insert into roasted fowl cavity or place across soup bowl.'
                ],
                pairing: 'Chicken Tinola, Lechon Fowl filling, Seafood Sinigang.',
                tip: 'Bruising cell walls before splitting releases citrusy citral essential oils.',
                svg: `<svg viewBox="0 0 100 100" class="w-28 h-28"><path d="M50,90 L50,30 M50,30 L20,10 M50,30 L35,10 M50,30 L50,5 M50,30 L65,10 M50,30 L80,10" stroke="#a3e635" stroke-width="4" stroke-linecap="round"/></svg>`
            },

            // GLOBAL & SEASONAL CLASSICS (12 CUTS)
            {
                id: 'radish-rose',
                title: 'Radish Rosette Blossom',
                season: 'spring',
                origin: 'Western',
                tech: 'Ice Curl',
                skill: 'Intermediate',
                tool: 'Paring Knife',
                veg: 'Radish',
                desc: 'Globe radish scored into overlapping petal layers that bloom in ice water.',
                steps: [
                    'Trim stem cap and root tip flat from globe radish.',
                    'Slice 4-5 shallow tangential cuts around outer perimeter.',
                    'Step inward and make a staggered inner layer of cuts.',
                    'Plunge in ice water bath for 15 mins to open petals.'
                ],
                pairing: 'Charcuterie boards, chilled garden salads, roast meats.',
                tip: 'Keep base root intact by 1/4 inch so petals remain anchored.',
                svg: `<svg viewBox="-50 -50 100 100" class="w-28 h-28"><circle cx="0" cy="0" r="40" fill="#ef4444"/><circle cx="0" cy="0" r="32" fill="#fca5a5"/><circle cx="0" cy="0" r="22" fill="#f87171"/><circle cx="0" cy="0" r="12" fill="#fef2f2"/></svg>`
            },
            {
                id: 'scallion-curl',
                title: 'Ice-Curled Scallion Brushes',
                season: 'spring',
                origin: 'East Asian',
                tech: 'Ice Curl',
                skill: 'Beginner',
                tool: 'Paring Knife',
                veg: 'Scallion',
                desc: 'Micro-thin green onion strips that curl into spring coils in icy water.',
                steps: [
                    'Cut 3-inch scallion stalk sections.',
                    'Slice open lengthwise and lay flat.',
                    'Julienne into micro-thin strips (<0.5mm).',
                    'Drop into sub-zero ice bath for 10 mins.'
                ],
                pairing: 'Ramen bowls, steamed fish, stir-fry noodles, Arroz Caldo.',
                tip: 'Ultra thin cuts dislocate cell structure, generating maximum spiral force.',
                svg: `<svg viewBox="0 0 100 100" class="w-28 h-28"><path d="M10,50 Q30,10 50,50 T90,50" fill="none" stroke="#22c55e" stroke-width="4"/><path d="M10,30 Q30,80 50,30 T90,30" fill="none" stroke="#4ade80" stroke-width="3"/></svg>`
            },
            {
                id: 'cucumber-accordion',
                title: 'Cucumber Ribbon Accordion',
                season: 'summer',
                origin: 'East Asian',
                tech: 'Carving',
                skill: 'Intermediate',
                tool: 'Mandoline',
                veg: 'Cucumber',
                desc: 'Precision accordion-scored cucumber fan ribbon that stretches like a slinky.',
                steps: [
                    'Place chopsticks on both sides of cucumber as knife stoppers.',
                    'Make vertical cuts 2mm apart along full length.',
                    'Flip cucumber over and make diagonal 45° cuts 2mm apart.',
                    'Gently stretch out accordion ribbon for plating.'
                ],
                pairing: 'Sushi platters, chilled salmon tartare, cold gazpacho.',
                tip: 'Chopsticks prevent knife blade from cutting completely through.',
                svg: `<svg viewBox="0 0 100 100" class="w-28 h-28"><rect x="10" y="30" width="80" height="40" rx="5" fill="#15803d"/><line x1="25" y1="30" x2="25" y2="70" stroke="#86efac" stroke-width="2"/><line x1="40" y1="30" x2="40" y2="70" stroke="#86efac" stroke-width="2"/><line x1="55" y1="30" x2="55" y2="70" stroke="#86efac" stroke-width="2"/></svg>`
            },
            {
                id: 'carrot-lotus',
                title: 'Carrot Lotus & Zig-zag Wheels',
                season: 'autumn',
                origin: 'Western',
                tech: 'Carving',
                skill: 'Intermediate',
                tool: 'Channel Knife',
                veg: 'Carrot',
                desc: 'Channel-cut carrot cylinder sliced crosswise into star-shaped flower wheels.',
                steps: [
                    'Peel large thick carrot.',
                    'Use channel knife to cut 5 lengthwise V-grooves down carrot.',
                    'Slice carrot crosswise into 3mm flower wheels.',
                    'Blanch in salted boiling water for 30 seconds to brighten color.'
                ],
                pairing: 'Beef stew, holiday roasts, vegetable sautés.',
                tip: 'Channel cuts turn plain vegetable rounds into botanical wheels instantly.',
                svg: `<svg viewBox="0 0 100 100" class="w-28 h-28"><path d="M50,15 L58,35 L78,35 L62,48 L68,68 L50,55 L32,68 L38,48 L22,35 L42,35 Z" fill="#ea580c"/></svg>`
            },
            {
                id: 'bellpepper-tulip',
                title: 'Bell Pepper Tulip & Ribbons',
                season: 'autumn',
                origin: 'Western',
                tech: 'Carving',
                skill: 'Beginner',
                tool: 'Paring Knife',
                veg: 'Bell Pepper',
                desc: 'Vibrant red or yellow bell pepper cut into pointed tulip cups or fine ribbon curls.',
                steps: [
                    'Trim top and bottom off bell pepper.',
                    'Make 5 triangular V-cuts around middle section.',
                    'Pull halves apart into tulip blossom cups.',
                    'Fill center with microgreens or dips.'
                ],
                pairing: 'Crudité platters, roasted meats, rice bowls.',
                tip: 'Remove white inner ribs completely for clean vivid color contrast.',
                svg: `<svg viewBox="0 0 100 100" class="w-28 h-28"><polygon points="20,80 35,30 50,60 65,30 80,80" fill="#dc2626"/></svg>`
            },
            {
                id: 'beetroot-spheres',
                title: 'Beetroot Ruby Spheres & Wafer Crisp',
                season: 'winter',
                origin: 'Western',
                tech: 'Crisp Fry',
                skill: 'Intermediate',
                tool: 'Mandoline',
                veg: 'Beetroot',
                desc: 'Deep ruby beetroot mandoline-sliced into paper wafer crisps or scooped into jewel spheres.',
                steps: [
                    'Peel raw red beetroot.',
                    'Use melon baller to scoop spheres or mandoline for 1mm wafers.',
                    'Bake or fry wafers at 140°C until crisp.',
                    'Dust with sea salt and scatter over goat cheese or salad.'
                ],
                pairing: 'Goat cheese salads, steaks, roasted root vegetables.',
                tip: 'Low temperature frying preserves deep crimson pigments without charring black.',
                svg: `<svg viewBox="0 0 100 100" class="w-28 h-28"><circle cx="50" cy="50" r="35" fill="#831843"/><circle cx="50" cy="50" r="25" fill="#9d174d"/></svg>`
            },
            {
                id: 'leek-bow',
                title: 'Chive Lattice & Tied Leek Bows',
                season: 'winter',
                origin: 'Western',
                tech: 'Leaf Fold',
                skill: 'Intermediate',
                tool: 'Paring Knife',
                veg: 'Leek',
                desc: 'Blanched leek green ribbons tied into decorative bowknots around herb bundles.',
                steps: [
                    'Blanch long leek green ribbons in boiling water for 5 seconds.',
                    'Shock in ice bath and dry flat.',
                    'Wrap around asparagus or green bean bundles.',
                    'Tie neatly into a double loop bow ribbon.'
                ],
                pairing: 'Roasted asparagus, wrapped meat tenderloins, soup tureens.',
                tip: 'Quick blanching makes leek fibers elastic like culinary string.',
                svg: `<svg viewBox="0 0 100 100" class="w-28 h-28"><ellipse cx="35" cy="50" rx="18" ry="10" fill="#15803d"/><ellipse cx="65" cy="50" rx="18" ry="10" fill="#15803d"/><circle cx="50" cy="50" r="6" fill="#166534"/></svg>`
            },
            {
                id: 'zucchini-crown',
                title: 'Zucchini Blossom Crown',
                season: 'summer',
                origin: 'Western',
                tech: 'Carving',
                skill: 'Intermediate',
                tool: 'Paring Knife',
                veg: 'Zucchini',
                desc: 'Edible zucchini flower petals fan-carved into a golden botanical crown.',
                steps: [
                    'Select fresh yellow zucchini blossoms with tiny zucchini attached.',
                    'Gentle open flower petals and remove central stamen.',
                    'Stuff with whipped ricotta or kesong puti.',
                    'Twist petal tips closed to lock in filling before baking.'
                ],
                pairing: 'Pasta dishes, risotto, roasted fish.',
                tip: 'Handle delicate zucchini flowers gently with wet fingertips to avoid tearing.',
                svg: `<svg viewBox="0 0 100 100" class="w-28 h-28"><polygon points="50,15 65,45 85,30 70,65 90,85 50,75 10,85 30,65 15,30 35,45" fill="#eab308"/></svg>`
            },
            {
                id: 'red-cabbage-shred',
                title: 'Red Cabbage Crisp Fine Shred',
                season: 'autumn',
                origin: 'Western',
                tech: 'Ice Curl',
                skill: 'Beginner',
                tool: 'Mandoline',
                veg: 'Red Cabbage',
                desc: 'Micro-shredded purple cabbage ribbons shocked in ice water for vibrant violet crunch.',
                steps: [
                    'Cut red cabbage head into quarters.',
                    'Shred micro-thin using mandoline (<1mm).',
                    'Plunge into ice water bath with lemon juice for 10 mins.',
                    'Drain well and nest atop tacos or fried platters.'
                ],
                pairing: 'Tacos, Sisig, Lumpia, Pulled pork.',
                tip: 'Acidic lemon water turns cabbage anthocyanin pigments bright electric purple.',
                svg: `<svg viewBox="0 0 100 100" class="w-28 h-28"><path d="M20,50 Q50,20 80,50 Q50,80 20,50 Z" fill="#581c87" stroke="#c084fc" stroke-width="2"/></svg>`
            },
            {
                id: 'citrus-twist',
                title: 'Citrus Twist Wheel & Star Cut',
                season: 'winter',
                origin: 'Global',
                tech: 'Carving',
                skill: 'Beginner',
                tool: 'Paring Knife',
                veg: 'Lemon',
                desc: 'Lemon or orange slices cut to the center and twisted into a 3D spiral wheel.',
                steps: [
                    'Slice lemon into thin 3mm wheels.',
                    'Make one radial cut from edge to center axis.',
                    'Gently twist the two slit ends in opposite directions.',
                    'Stand upright on rim of cocktail or fish plate.'
                ],
                pairing: 'Seafood dishes, grilled salmon, cocktails, iced tea.',
                tip: 'Slice thin enough so citrus rind flexes without tearing.',
                svg: `<svg viewBox="0 0 100 100" class="w-28 h-28"><circle cx="50" cy="50" r="35" fill="#facc15"/><line x1="50" y1="50" x2="85" y2="50" stroke="#ca8a04" stroke-width="4"/></svg>`
            },
            {
                id: 'ginger-straws',
                title: 'Crisp Ginger Straws & Matchsticks',
                season: 'autumn',
                origin: 'East Asian',
                tech: 'Crisp Fry',
                skill: 'Intermediate',
                tool: 'Mandoline',
                veg: 'Ginger',
                desc: 'Paper-thin ginger matchsticks fried until golden and crisp, offering warm spice.',
                steps: [
                    'Peel ginger root with edge of spoon.',
                    'Slice into 1mm thin planks, then julienne into matchsticks.',
                    'Flash fry in hot oil (170°C) for 15 seconds.',
                    'Drain on paper towels and sprinkle over steamed fish or porridge.'
                ],
                pairing: 'Steamed Fish, Arroz Caldo, Pork Humba, Stir-fry.',
                tip: 'Flash frying removes sharp raw burn while intensifying aromatic warmth.',
                svg: `<svg viewBox="0 0 100 100" class="w-28 h-28"><line x1="20" y1="20" x2="80" y2="80" stroke="#d97706" stroke-width="4"/><line x1="30" y1="10" x2="90" y2="70" stroke="#b45309" stroke-width="3"/></svg>`
            },
            {
                id: 'turnip-fan',
                title: 'Turnip Lattice Fan & Flower',
                season: 'spring',
                origin: 'East Asian',
                tech: 'Carving',
                skill: 'Master Carver',
                tool: 'Thai Knife',
                veg: 'Turnip',
                desc: 'White turnip carved into delicate see-through lattice fans soaked in sweet plum vinegar.',
                steps: [
                    'Peel white turnip and slice a 1/2-inch thick rectangular block.',
                    'Make rapid parallel vertical slits stopping 5mm from bottom base.',
                    'Soak in light vinegar brine for 15 mins until pliable.',
                    'Fan out into an oriental folding fan shape.'
                ],
                pairing: 'Pork belly, duck breast, Asian roasts.',
                tip: 'Vinegar brine softens tough pectin walls, allowing tight fan expansion without breakage.',
                svg: `<svg viewBox="0 0 100 100" class="w-28 h-28"><polygon points="10,90 30,10 70,10 90,90" fill="#f1f5f9" stroke="#94a3b8" stroke-width="2"/></svg>`
            }
        ];

        // App State
        let currentSeason = 'spring';
        let notebook = [];
        let timerInterval = null;
        let timerSeconds = 600;

        window.onload = function() {
            renderGarnishes();
            updateDishRecommendations();
            updateScallionSim();
            updateRadishSim();
            setCutAngle('45bias');
        }

        function filterPHGarnishesOnly() {
            document.querySelectorAll('.season-btn').forEach(btn => btn.classList.remove('bg-white/20', 'font-bold'));
            document.getElementById('btn-ph-only').classList.add('bg-white/20', 'font-bold');
            document.getElementById('filter-origin').value = 'Philippine';
            filterGarnishes();
        }

        function setSeason(season) {
            currentSeason = season;
            document.body.className = `theme-${season} min-h-screen flex flex-col antialiased selection:bg-gold selection:text-white`;

            document.querySelectorAll('.season-btn').forEach(btn => {
                btn.className = 'season-btn flex items-center justify-center space-x-2 py-2.5 px-3 rounded-xl font-medium text-xs transition-all hover:bg-white/10 text-stone-300';
            });
            const activeBtn = document.getElementById(`btn-${season}`);
            if (activeBtn) {
                activeBtn.className = 'season-btn flex items-center justify-center space-x-2 py-2.5 px-3 rounded-xl font-medium text-xs transition-all bg-white/20 text-white shadow font-bold';
            }

            document.getElementById('current-season-badge').innerText = `${season.toUpperCase()} PALETTE`;
            document.getElementById('filter-season').value = season;
            updateDishRecommendations();
            filterGarnishes();
        }

        function renderGarnishes(data = garnishesData) {
            const grid = document.getElementById('garnish-grid');
            const noResults = document.getElementById('no-results');
            grid.innerHTML = '';

            if (data.length === 0) {
                noResults.classList.remove('hidden');
                return;
            } else {
                noResults.classList.add('hidden');
            }

            data.forEach(item => {
                const isBookmarked = notebook.some(n => n.id === item.id);
                const card = document.createElement('div');
                card.className = "bg-white rounded-2xl border border-stone-200/80 shadow-sm hover:shadow-xl transition-all duration-300 overflow-hidden flex flex-col justify-between group";

                card.innerHTML = `
                    <div>
                        <div class="bg-stone-900 p-6 flex items-center justify-center relative overflow-hidden group-hover:scale-105 transition-transform duration-500 h-44">
                            <div class="opacity-80 group-hover:opacity-100 transition-opacity">
                                ${item.svg}
                            </div>
                            <span class="absolute top-3 left-3 bg-white/20 backdrop-blur-md text-white text-[10px] uppercase tracking-wider font-bold px-2.5 py-1 rounded-full border border-white/20">
                                ${item.origin === 'Philippine' ? '🇵🇭 Filipino' : item.origin}
                            </span>
                            <button onclick="toggleBookmark('${item.id}', event)" class="absolute top-3 right-3 w-8 h-8 rounded-full bg-white/20 backdrop-blur-md flex items-center justify-center text-white hover:bg-gold transition-colors">
                                <i class="${isBookmarked ? 'fa-solid text-gold' : 'fa-regular'} fa-bookmark"></i>
                            </button>
                        </div>
                        <div class="p-5">
                            <div class="flex items-center space-x-2 mb-1.5">
                                <span class="text-xs font-bold text-terracotta uppercase">${item.veg}</span>
                                <span class="text-stone-300">•</span>
                                <span class="text-xs text-stone-500">${item.tech}</span>
                            </div>
                            <h3 class="font-serif text-lg font-bold text-forest mb-1.5 group-hover:text-terracotta transition-colors">${item.title}</h3>
                            <p class="text-stone-600 text-xs leading-relaxed line-clamp-2">${item.desc}</p>
                        </div>
                    </div>
                    <div class="px-5 pb-5 pt-0 flex items-center justify-between border-t border-stone-100 mt-3 pt-3">
                        <span class="text-[11px] font-semibold px-2 py-0.5 rounded-full ${getSkillBadgeClass(item.skill)}">${item.skill}</span>
                        <button onclick="openModal('${item.id}')" class="text-xs font-bold text-forest hover:text-gold transition-colors flex items-center">
                            Master Cut <i class="fa-solid fa-arrow-right ml-1"></i>
                        </button>
                    </div>
                `;
                grid.appendChild(card);
            });
        }

        function getSkillBadgeClass(skill) {
            switch(skill) {
                case 'Beginner': return 'bg-emerald-100 text-emerald-800';
                case 'Intermediate': return 'bg-amber-100 text-amber-800';
                case 'Master Carver': return 'bg-purple-100 text-purple-800';
                default: return 'bg-stone-100 text-stone-800';
            }
        }

        function filterGarnishes() {
            const query = document.getElementById('search-input').value.toLowerCase();
            const origin = document.getElementById('filter-origin').value;
            const tech = document.getElementById('filter-tech').value;
            const skill = document.getElementById('filter-skill').value;
            const tool = document.getElementById('filter-tool').value;
            const season = document.getElementById('filter-season').value;

            const filtered = garnishesData.filter(g => {
                const matchesSearch = g.title.toLowerCase().includes(query) || g.veg.toLowerCase().includes(query) || g.desc.toLowerCase().includes(query);
                const matchesOrigin = origin === 'all' || g.origin === origin;
                const matchesTech = tech === 'all' || g.tech === tech;
                const matchesSkill = skill === 'all' || g.skill === skill;
                const matchesTool = tool === 'all' || g.tool === tool;
                const matchesSeason = season === 'all' || g.season === season;

                return matchesSearch && matchesOrigin && matchesTech && matchesSkill && matchesTool && matchesSeason;
            });

            renderGarnishes(filtered);
        }

        function resetFilters() {
            document.getElementById('search-input').value = '';
            document.getElementById('filter-origin').value = 'all';
            document.getElementById('filter-tech').value = 'all';
            document.getElementById('filter-skill').value = 'all';
            document.getElementById('filter-tool').value = 'all';
            document.getElementById('filter-season').value = 'all';
            renderGarnishes(garnishesData);
        }

        // Blade Entry Visualizer
        function setCutAngle(angleType) {
            document.querySelectorAll('.angle-btn').forEach(btn => btn.classList.remove('active-dish'));
            const activeBtn = document.getElementById(`angle-btn-${angleType}`);
            if (activeBtn) activeBtn.classList.add('active-dish');

            const svg = document.getElementById('angle-svg');
            const label = document.getElementById('angle-degree-label');
            const title = document.getElementById('angle-physics-title');
            const desc = document.getElementById('angle-physics-desc');

            if (angleType === '45bias') {
                label.innerText = 'ENTRY: 45° DIAGONAL BIAS';
                title.innerText = 'Physics Impact: Surface Area Expansion (+40%)';
                desc.innerText = 'Diagonal cuts sever longitudinal fibers at an angle, exposing 40% more capillary channels for rapid water uptake during curling.';
                svg.innerHTML = `
                    <rect x="50" y="70" width="300" height="40" fill="#22c55e" rx="4"/>
                    <line x1="120" y1="30" x2="200" y2="120" stroke="#facc15" stroke-width="4" stroke-dasharray="6,4"/>
                    <polygon points="195,120 205,125 200,110" fill="#facc15"/>
                    <text x="210" y="60" fill="#facc15" font-family="monospace" font-size="14" font-weight="bold">45° Blade Entry</text>
                `;
            } else if (angleType === '90straight') {
                label.innerText = 'ENTRY: 90° PERPENDICULAR';
                title.innerText = 'Physics Impact: Structural Radial Symmetry';
                desc.innerText = 'A 90° straight cross-cut leaves cell walls intact around the perimeter, ideal for rigid star wheels and citrus coins.';
                svg.innerHTML = `
                    <rect x="50" y="70" width="300" height="40" fill="#ef4444" rx="4"/>
                    <line x1="200" y1="20" x2="200" y2="120" stroke="#facc15" stroke-width="4"/>
                    <text x="215" y="50" fill="#facc15" font-family="monospace" font-size="14" font-weight="bold">90° Straight Cut</text>
                `;
            } else if (angleType === 'vchisel') {
                label.innerText = 'ENTRY: 60° V-CHISEL CROWN';
                title.innerText = 'Physics Impact: Dual-Wedge Tension Release';
                desc.innerText = 'Intersecting V-cuts release outer dermal tension, causing crown points to spring open like flower petals.';
                svg.innerHTML = `
                    <circle cx="200" cy="80" r="45" fill="#15803d"/>
                    <path d="M170,50 L200,80 L230,50" fill="none" stroke="#facc15" stroke-width="4"/>
                    <text x="240" y="60" fill="#facc15" font-family="monospace" font-size="14" font-weight="bold">60° V-Notch</text>
                `;
            } else if (angleType === 'flute') {
                label.innerText = 'ENTRY: CONTINUOUS V-GROOVE CHANNEL';
                title.innerText = 'Physics Impact: Rind Fluting Architecture';
                desc.innerText = 'Channel knife gouges remove outer skin strips, creating high-contrast scalloped flower wheels when sliced crosswise.';
                svg.innerHTML = `
                    <rect x="80" y="60" width="240" height="50" fill="#047857" rx="8"/>
                    <path d="M80,70 L320,70 M80,85 L320,85 M80,100 L320,100" stroke="#fef08a" stroke-width="3" stroke-dasharray="8,4"/>
                    <text x="120" y="45" fill="#facc15" font-family="monospace" font-size="14" font-weight="bold">Channel Knife Groove</text>
                `;
            }
        }

        function updateScallionSim() {
            const val = parseFloat(document.getElementById('thickness-range').value);
            document.getElementById('thickness-val').innerText = `${val.toFixed(1)} mm (${val < 0.5 ? 'Micro Thin' : val < 1.2 ? 'Medium Ribbon' : 'Thick Slice'})`;
            document.getElementById('cut-value-label').innerText = `${val.toFixed(1)} mm Cut`;

            const path = document.getElementById('scallion-path');
            const pathInner = document.getElementById('scallion-path-inner');
            const tightness = (2.1 - val) * 25;
            const d = `M 30,75 Q ${100 - tightness},${75 - tightness} ${150},75 T ${270 - tightness/2},75`;
            
            path.setAttribute('d', d);
            pathInner.setAttribute('d', d);
            path.setAttribute('stroke-width', Math.max(2, val * 4));
        }

        function updateRadishSim() {
            const time = parseInt(document.getElementById('bloom-range').value);
            document.getElementById('time-val').innerText = `${time} Minutes`;
            const bloomPct = Math.min(100, Math.round((time / 30) * 100));
            document.getElementById('bloom-percent').innerText = `${bloomPct}% Expanded`;

            const container = document.getElementById('radish-petals');
            container.innerHTML = '';
            const numPetals = 8;
            const spreadRadius = 25 + (bloomPct * 0.45);

            for (let i = 0; i < numPetals; i++) {
                const angle = (i * (360 / numPetals)) * (Math.PI / 180);
                const x = Math.cos(angle) * spreadRadius;
                const y = Math.sin(angle) * spreadRadius;

                const petal = document.createElementNS("http://www.w3.org/2000/svg", "circle");
                petal.setAttribute("cx", x);
                petal.setAttribute("cy", y);
                petal.setAttribute("r", 14 + (bloomPct * 0.08));
                petal.setAttribute("fill", "#ef4444");
                petal.setAttribute("opacity", "0.85");
                container.appendChild(petal);
            }
        }

        let selectedDishType = 'lechon';

        function selectDish(dish) {
            selectedDishType = dish;
            document.querySelectorAll('.dish-opt').forEach(btn => btn.classList.remove('active-dish'));
            event.currentTarget.classList.add('active-dish');
            updateDishRecommendations();
        }

        function updateDishRecommendations() {
            const container = document.getElementById('recommendations-container');
            
            const pairings = {
                lechon: {
                    title: "Garnishes for Lechon & Pork Liempo",
                    items: [
                        { name: "Papaya Atchara Ribbon Rosette", texture: "Sweet-Sour Crispness", note: "Cuts through heavy pig skin fat while acting as a stunning floral centerpiece." },
                        { name: "Calamansi Crown & Star Cut", texture: "Bright Citrus Burst", note: "Diners squeeze acidic citrus juice directly over golden crackling pork skin." }
                    ]
                },
                sinigang: {
                    title: "Garnishes for Sinigang Tamarind Broth",
                    items: [
                        { name: "Siling Labuyo Dragon Fire Crown", texture: "Aromatic Heat Flare", note: "Releases controlled capsicum heat oils into hot sour tamarind broth." },
                        { name: "Kinudkod Green Mango Blossom", texture: "Tangy Fruit Snap", note: "Adds raw green mango tartness atop tender pork or salmon collar." }
                    ]
                },
                palabok: {
                    title: "Garnishes for Pancit Palabok & Bihon Noodles",
                    items: [
                        { name: "Crispy Garlic Flake Golden Crown", texture: "Savory Crunch", note: "Elevates creamy annatto shrimp sauce with rich toasted garlic aroma." },
                        { name: "Ice-Curled Scallion Brushes", texture: "Fresh Herbal Lift", note: "Provides vivid green contrast against crushed chicharon and hardboiled egg." }
                    ]
                },
                karekare: {
                    title: "Garnishes for Kare-Kare Peanut Stew",
                    items: [
                        { name: "Ampalaya Emerald Lattice Ribbons", texture: "Crisp Bitter Contrast", note: "Cuts through rich ground peanut sauce richness." },
                        { name: "Siling Labuyo Dragon Fire Crown", texture: "Spicy Accent", note: "Pairs with salty bagoong alamang dip for heat balance." }
                    ]
                },
                kinilaw: {
                    title: "Garnishes for Kinilaw na Tanigue / Tuna",
                    items: [
                        { name: "Sibuyas Tagalog Ribbon Star", texture: "Piquant Snap", note: "Soaks in coconut vinegar while preserving crisp violet rings." },
                        { name: "Crisp Ginger Straws", texture: "Zesty Heat", note: "Cleanses raw fish palate with warm gingery crunch." }
                    ]
                },
                inasal: {
                    title: "Garnishes for Chicken Inasal",
                    items: [
                        { name: "Calamansi Crown & Star Cut", texture: "Citrus Activation", note: "Essential for mixing with annatto oil and soy sauce at the table." },
                        { name: "Banana Leaf Origami Base", texture: "Aromatic Plating", note: "Warmed leaf releases herbal perfume beneath hot grilled chicken." }
                    ]
                },
                pata: {
                    title: "Garnishes for Crispy Pata",
                    items: [
                        { name: "Papaya Atchara Ribbon Rosette", texture: "Vinegar Acid Cut", note: "Provides essential digestive acid against deep-fried pork knuckle." },
                        { name: "Red Cabbage Crisp Fine Shred", texture: "Purple Crunch", note: "Adds vivid color and crisp texture around dish edges." }
                    ]
                },
                arrozcaldo: {
                    title: "Garnishes for Arroz Caldo Chicken Porridge",
                    items: [
                        { name: "Crispy Garlic Flake Golden Crown", texture: "Toasted Crunch", note: "Classic savory topper for rich ginger chicken rice porridge." },
                        { name: "Ice-Curled Scallion Brushes", texture: "Fresh Green Ribbon", note: "Lifts savory chicken broth with fresh onion brightness." }
                    ]
                },
                lumpia: {
                    title: "Garnishes for Lumpia Shanghai",
                    items: [
                        { name: "Singkamas Snowflake Lotus Star", texture: "Juicy Refreshing Crunch", note: "Cooled jicama lotus clears palate between crispy fried spring rolls." },
                        { name: "Kamatis Rose Peel & Lotus Bloom", texture: "Glossy Red Accent", note: "Provides bright color contrast on party platters." }
                    ]
                },
                sisig: {
                    title: "Garnishes for Sizzling Pork Sisig",
                    items: [
                        { name: "Calamansi Crown & Star Cut", texture: "Acid Brightness", note: "Squeezed over sizzling iron plate to cut rich pork mask and liver." },
                        { name: "Siling Labuyo Dragon Fire Crown", texture: "Fiery Heat", note: "Chopped directly into sizzling fat for heat lovers." }
                    ]
                },
                bistek: {
                    title: "Garnishes for Bistek Tagalog",
                    items: [
                        { name: "Sibuyas Tagalog Ribbon Star", texture: "Sweet Onion Rings", note: "Raw rings wilt slightly in hot citrus-soy marinade." },
                        { name: "Calamansi Crown & Star Cut", texture: "Tart Balance", note: "Balances salty soy marinade notes." }
                    ]
                },
                bulalo: {
                    title: "Garnishes for Beef Bulalo Soup",
                    items: [
                        { name: "Ice-Curled Scallion Brushes", texture: "Herbal Lift", note: "Floats atop rich beef marrow broth for fresh aroma." },
                        { name: "Crisp Ginger Straws", texture: "Warm Spice", note: "Cuts through heavy beef fat marrow." }
                    ]
                }
            };

            const data = pairings[selectedDishType];
            document.getElementById('recommendation-title').innerText = data.title;

            container.innerHTML = data.items.map(item => `
                <div class="p-4 rounded-xl bg-parchment-dark border border-stone-200 flex flex-col sm:flex-row justify-between items-start sm:items-center gap-2">
                    <div>
                        <h4 class="font-serif font-bold text-forest text-base">${item.name}</h4>
                        <p class="text-stone-600 text-xs mt-0.5">${item.note}</p>
                    </div>
                    <span class="px-3 py-1 bg-white text-terracotta border border-terracotta/30 text-xs font-bold rounded-full shrink-0">
                        ${item.texture}
                    </span>
                </div>
            `).join('');
        }

        function updateTimerPreset() {
            const minutes = parseInt(document.getElementById('timer-veg-select').value);
            timerSeconds = minutes * 60;
            displayTimer();
            if (timerInterval) resetTimer();
        }

        function displayTimer() {
            const mins = Math.floor(timerSeconds / 60);
            const secs = timerSeconds % 60;
            document.getElementById('timer-display').innerText = `${mins.toString().padStart(2, '0')}:${secs.toString().padStart(2, '0')}`;
        }

        function toggleTimer() {
            if (timerInterval) {
                clearInterval(timerInterval);
                timerInterval = null;
                document.getElementById('start-btn-text').innerText = 'Resume Bath';
            } else {
                document.getElementById('start-btn-text').innerText = 'Pause Bath';
                timerInterval = setInterval(() => {
                    if (timerSeconds > 0) {
                        timerSeconds--;
                        displayTimer();
                    } else {
                        clearInterval(timerInterval);
                        timerInterval = null;
                        document.getElementById('start-btn-text').innerText = 'Bath Complete!';
                    }
                }, 1000);
            }
        }

        function resetTimer() {
            if (timerInterval) {
                clearInterval(timerInterval);
                timerInterval = null;
            }
            updateTimerPreset();
            document.getElementById('start-btn-text').innerText = 'Start Ice Bath';
        }

        let activeModalId = null;

        function openModal(id) {
            const item = garnishesData.find(g => g.id === id);
            if (!item) return;

            activeModalId = id;
            document.getElementById('modal-title').innerText = item.title;
            document.getElementById('modal-desc').innerText = item.desc;
            document.getElementById('modal-skill-badge').innerText = item.skill;
            document.getElementById('modal-skill-badge').className = `px-3 py-0.5 rounded-full text-xs font-bold ${getSkillBadgeClass(item.skill)}`;
            document.getElementById('modal-veg-type').innerText = `${item.veg} Cut`;
            document.getElementById('modal-origin-badge').innerText = item.origin === 'Philippine' ? '🇵🇭 Philippine Heritage' : `${item.origin} Classic`;
            document.getElementById('modal-pairing').innerText = item.pairing;
            document.getElementById('modal-tip').innerText = item.tip;
            document.getElementById('modal-svg-container').innerHTML = item.svg;

            const stepsList = document.getElementById('modal-steps-list');
            stepsList.innerHTML = item.steps.map(step => `<li class="leading-relaxed mb-1">${step}</li>`).join('');

            const isBookmarked = notebook.some(n => n.id === item.id);
            const btn = document.getElementById('modal-bookmark-btn');
            btn.setAttribute('onclick', `toggleBookmark('${item.id}')`);
            btn.innerHTML = `<i class="${isBookmarked ? 'fa-solid' : 'fa-regular'} fa-bookmark mr-2"></i> ${isBookmarked ? 'Saved in Prep Sheet' : 'Save to Prep Sheet'}`;

            document.getElementById('detail-modal').classList.remove('hidden');
        }

        function closeModal() {
            document.getElementById('detail-modal').classList.add('hidden');
        }

        function toggleBookmark(id, e) {
            if (e) e.stopPropagation();
            const item = garnishesData.find(g => g.id === id);
            
            const index = notebook.findIndex(n => n.id === id);
            if (index > -1) {
                notebook.splice(index, 1);
            } else {
                notebook.push(item);
            }

            document.getElementById('notebook-badge').innerText = notebook.length;
            renderGarnishes();
            renderNotebook();

            if (activeModalId === id) {
                const isBookmarked = notebook.some(n => n.id === id);
                const btn = document.getElementById('modal-bookmark-btn');
                btn.innerHTML = `<i class="${isBookmarked ? 'fa-solid' : 'fa-regular'} fa-bookmark mr-2"></i> ${isBookmarked ? 'Saved in Prep Sheet' : 'Save to Prep Sheet'}`;
            }
        }

        function toggleNotebookModal() {
            document.getElementById('notebook-modal').classList.toggle('hidden');
        }

        function renderNotebook() {
            const container = document.getElementById('notebook-items-container');
            if (notebook.length === 0) {
                container.innerHTML = `<p class="text-center text-stone-400 py-8 text-sm italic">No garnishing cuts bookmarked yet. Click the bookmark icon on any cut card to compile your prep cheat sheet.</p>`;
                return;
            }

            container.innerHTML = notebook.map(item => `
                <div class="p-4 bg-stone-50 rounded-xl border border-stone-200 flex items-center justify-between">
                    <div>
                        <h4 class="font-serif font-bold text-forest text-sm">${item.title}</h4>
                        <p class="text-xs text-stone-500">${item.veg} • ${item.tool} (${item.origin})</p>
                    </div>
                    <button onclick="toggleBookmark('${item.id}')" class="text-red-500 hover:text-red-700 text-xs font-semibold no-print">
                        <i class="fa-solid fa-trash-can mr-1"></i> Remove
                    </button>
                </div>
            `).join('');
        }

        function clearNotebook() {
            notebook = [];
            document.getElementById('notebook-badge').innerText = '0';
            renderGarnishes();
            renderNotebook();
        }
    </script>
</body>
</html>
