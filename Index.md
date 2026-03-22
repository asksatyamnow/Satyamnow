<!DOCTYPE html>
<html lang="en" class="light">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Satyamnow.in | Clear Biblical Answers</title>
    <meta name="description" content="A modern, clear platform providing biblical answers to your questions about God, Jesus, and the Bible.">
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        primary: '#4f46e5',   // Indigo 600
                        primaryHover: '#4338ca', // Indigo 700
                        accent: '#9333ea',    // Purple 600
                        darkBg: '#0f172a',    // Slate 900
                        darkCard: '#1e293b',  // Slate 800
                        lightBg: '#f8fafc',   // Slate 50
                    },
                    fontFamily: {
                        sans: ['Inter', 'system-ui', 'sans-serif'],
                        serif: ['Merriweather', 'serif'],
                    }
                }
            }
        }
    </script>
    
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Merriweather:ital,wght@0,400;0,700;1,400&display=swap');
        
        html { scroll-behavior: smooth; }
        body { transition: background-color 0.3s ease, color 0.3s ease; }
        
        .view-section { display: none; }
        .view-section.active { display: block; animation: fadeUp 0.4s ease-out forwards; }
        
        @keyframes fadeUp {
            from { opacity: 0; transform: translateY(15px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar { width: 8px; }
        ::-webkit-scrollbar-track { background: transparent; }
        ::-webkit-scrollbar-thumb { background: #cbd5e1; border-radius: 4px; }
        .dark ::-webkit-scrollbar-thumb { background: #475569; }
        
        /* Glassmorphism */
        .glass { background: rgba(255, 255, 255, 0.8); backdrop-filter: blur(16px); -webkit-backdrop-filter: blur(16px); }
        .dark .glass { background: rgba(15, 23, 42, 0.8); border-bottom: 1px solid rgba(255,255,255,0.05); }

        .article-content p { margin-bottom: 1.5rem; line-height: 1.8; }
        
        .tab-active { border-bottom: 2px solid #4f46e5; color: #4f46e5; }
        .dark .tab-active { border-bottom: 2px solid #818cf8; color: #818cf8; }
    </style>
</head>
<body class="bg-lightBg dark:bg-darkBg text-slate-800 dark:text-slate-200 font-sans min-h-screen flex flex-col">

    <!-- NAVIGATION HEADER -->
    <header class="glass fixed w-full top-0 z-50 border-b border-slate-200/50 dark:border-slate-800">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-16">
                <!-- Logo -->
                <div class="flex-shrink-0 flex items-center cursor-pointer group" onclick="navigateTo('home')">
                    <div class="bg-gradient-to-br from-primary to-accent text-white p-1.5 rounded-lg mr-2 shadow-md group-hover:rotate-3 transition">
                        <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.747 0 3.332.477 4.5 1.253v13C19.832 18.477 18.247 18 16.5 18c-1.746 0-3.332.477-4.5 1.253" />
                        </svg>
                    </div>
                    <span class="font-bold text-2xl tracking-tight text-slate-900 dark:text-white">Satyam<span class="text-primary dark:text-indigo-400">now</span></span>
                </div>
                
                <!-- Desktop Nav -->
                <nav class="hidden md:flex items-center space-x-1">
                    <button onclick="navigateTo('home')" class="nav-link px-4 py-2 text-slate-600 dark:text-slate-300 hover:text-primary dark:hover:text-indigo-400 font-medium transition rounded-lg">Home</button>
                    <button onclick="navigateTo('questions')" class="nav-link px-4 py-2 text-slate-600 dark:text-slate-300 hover:text-primary dark:hover:text-indigo-400 font-medium transition rounded-lg">Library</button>
                    <button onclick="navigateTo('about')" class="nav-link px-4 py-2 text-slate-600 dark:text-slate-300 hover:text-primary dark:hover:text-indigo-400 font-medium transition rounded-lg">About</button>
                    <button onclick="navigateTo('ask')" class="ml-4 bg-slate-900 dark:bg-white text-white dark:text-slate-900 px-6 py-2 rounded-full font-semibold hover:scale-105 transition shadow-lg active:scale-95">Ask Us</button>
                    
                    <button onclick="toggleTheme()" class="ml-4 p-2 rounded-full bg-slate-100 dark:bg-slate-800 text-slate-600 dark:text-slate-300 hover:bg-slate-200 transition">
                        <svg id="sun-icon" class="w-5 h-5 hidden dark:block" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M10 2a1 1 0 011 1v1a1 1 0 11-2 0V3a1 1 0 011-1zm4.22 2.32a1 1 0 011.415 0l.707.707a1 1 0 01-1.414 1.415l-.707-.708a1 1 0 010-1.414zm3.78 5.68a1 1 0 01-1 1h-1a1 1 0 110-2h1a1 1 0 011 1zM14.22 15.46a1 1 0 010 1.415l-.707.707a1 1 0 01-1.415-1.414l.707-.707a1 1 0 011.415 0zM10 16a1 1 0 011 1v1a1 1 0 11-2 0v-1a1 1 0 011-1zm-4.22-2.32a1 1 0 01-1.415 0l-.707-.707a1 1 0 011.414-1.415l.707.708a1 1 0 010 1.414zM2 10a1 1 0 011-1h1a1 1 0 110 2H3a1 1 0 01-1-1zm2.32-4.22a1 1 0 010-1.415l.707-.707a1 1 0 011.415 1.414l-.707.707a1 1 0 01-1.415 0zM10 5a5 5 0 100 10 5 5 0 000-10z" clip-rule="evenodd"></path></svg>
                        <svg id="moon-icon" class="w-5 h-5 block dark:hidden" fill="currentColor" viewBox="0 0 20 20"><path d="M17.293 13.293A8 8 0 016.707 2.707a8.001 8.001 0 1010.586 10.586z"></path></svg>
                    </button>
                </nav>

                <!-- Mobile Menu Button -->
                <div class="md:hidden flex items-center gap-4">
                    <button onclick="toggleTheme()" class="p-2 rounded-lg bg-slate-100 dark:bg-slate-800">
                        <svg class="w-5 h-5 dark:hidden" fill="currentColor" viewBox="0 0 20 20"><path d="M17.293 13.293A8 8 0 016.707 2.707a8.001 8.001 0 1010.586 10.586z"></path></svg>
                        <svg class="w-5 h-5 hidden dark:block" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M10 2a1 1 0 011 1v1a1 1 0 11-2 0V3a1 1 0 011-1zm4.22 2.32a1 1 0 011.415 0l.707.707a1 1 0 01-1.414 1.415l-.707-.708a1 1 0 010-1.414zm3.78 5.68a1 1 0 01-1 1h-1a1 1 0 110-2h1a1 1 0 011 1zM14.22 15.46a1 1 0 010 1.415l-.707.707a1 1 0 01-1.415-1.414l.707-.707a1 1 0 011.415 0zM10 16a1 1 0 011 1v1a1 1 0 11-2 0v-1a1 1 0 011-1zm-4.22-2.32a1 1 0 01-1.415 0l-.707-.707a1 1 0 011.414-1.415l.707.708a1 1 0 010 1.414zM2 10a1 1 0 011-1h1a1 1 0 110 2H3a1 1 0 01-1-1zm2.32-4.22a1 1 0 010-1.415l.707-.707a1 1 0 011.415 1.414l-.707.707a1 1 0 01-1.415 0zM10 5a5 5 0 100 10 5 5 0 000-10z" clip-rule="evenodd"></path></svg>
                    </button>
                    <button id="mobile-menu-btn" class="text-slate-600 dark:text-slate-300">
                        <svg class="h-8 w-8" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/></svg>
                    </button>
                </div>
            </div>
        </div>

        <!-- Mobile Menu -->
        <div id="mobile-menu" class="hidden md:hidden bg-white dark:bg-slate-900 border-t border-slate-200 dark:border-slate-800 shadow-2xl absolute w-full left-0 p-6 space-y-4">
            <button onclick="navigateTo('home')" class="block w-full text-left py-3 text-lg font-bold border-b dark:border-slate-800">Home</button>
            <button onclick="navigateTo('questions')" class="block w-full text-left py-3 text-lg font-bold border-b dark:border-slate-800">Library</button>
            <button onclick="navigateTo('about')" class="block w-full text-left py-3 text-lg font-bold border-b dark:border-slate-800">About</button>
            <button onclick="navigateTo('ask')" class="block w-full bg-primary text-white py-4 rounded-xl text-center font-bold">Ask Us</button>
        </div>
    </header>

    <!-- CONTENT SPACER -->
    <div class="h-16"></div>

    <main class="flex-grow">
        
        <!-- ================= HOME ================= -->
        <section id="home" class="view-section active">
            <!-- Hero -->
            <div class="max-w-6xl mx-auto px-4 py-12 md:py-24">
                <div class="grid md:grid-cols-2 gap-12 items-center">
                    <div>
                        <span class="inline-block py-1.5 px-4 rounded-full bg-indigo-100 dark:bg-indigo-900/40 text-primary dark:text-indigo-300 text-sm font-bold uppercase tracking-widest mb-6">Truth that matters</span>
                        <h1 class="text-5xl md:text-6xl font-extrabold text-slate-900 dark:text-white mb-6 leading-[1.1]">The Bible, <br><span class="text-primary italic">Simplified.</span></h1>
                        <p class="text-xl text-slate-600 dark:text-slate-400 mb-10 leading-relaxed max-w-lg">Get clear, concise, and faithful answers to life's biggest spiritual questions. Start your journey into the Word of God today.</p>
                        
                        <div class="relative max-w-md group mb-8">
                            <input type="text" id="home-search" onkeyup="handleHomeSearch(event)" placeholder="Search for a topic..." class="w-full pl-12 pr-4 py-4 rounded-2xl bg-white dark:bg-slate-800 border-2 border-transparent focus:border-primary shadow-xl outline-none transition-all dark:text-white">
                            <svg class="absolute left-4 top-4 h-6 w-6 text-slate-400" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" /></svg>
                        </div>

                        <div class="flex flex-wrap gap-4 text-sm font-semibold text-slate-500">
                            <span>Popular:</span>
                            <button onclick="searchTag('Salvation')" class="hover:text-primary underline">Salvation</button>
                            <button onclick="searchTag('Jesus')" class="hover:text-primary underline">Jesus</button>
                            <button onclick="searchTag('Heaven')" class="hover:text-primary underline">Heaven</button>
                        </div>
                    </div>
                    
                    <div class="relative hidden md:block">
                        <div class="absolute -inset-4 bg-gradient-to-r from-primary to-accent rounded-[3rem] blur-2xl opacity-20"></div>
                        <div class="relative bg-white dark:bg-slate-800 p-8 rounded-[2.5rem] shadow-2xl border border-slate-100 dark:border-slate-700">
                            <div class="flex items-center gap-4 mb-6">
                                <div class="w-12 h-12 bg-primary/10 rounded-full flex items-center justify-center text-primary font-bold">Q</div>
                                <div class="font-bold text-lg dark:text-white">How do I know God exists?</div>
                            </div>
                            <div class="space-y-4">
                                <div class="h-4 bg-slate-100 dark:bg-slate-700 rounded-full w-full"></div>
                                <div class="h-4 bg-slate-100 dark:bg-slate-700 rounded-full w-[90%]"></div>
                                <div class="h-4 bg-slate-100 dark:bg-slate-700 rounded-full w-[95%]"></div>
                                <div class="h-4 bg-slate-100 dark:bg-slate-700 rounded-full w-[40%]"></div>
                            </div>
                            <div class="mt-8 pt-6 border-t dark:border-slate-700 flex justify-between items-center">
                                <span class="text-sm font-bold text-primary uppercase">Daily Truth</span>
                                <span class="text-xs text-slate-400">Satyamnow.in</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Featured Cards -->
            <div class="bg-white dark:bg-slate-900/50 py-20">
                <div class="max-w-6xl mx-auto px-4">
                    <div class="flex justify-between items-end mb-12">
                        <div>
                            <h2 class="text-3xl font-bold dark:text-white">Start Here</h2>
                            <p class="text-slate-500 mt-2">Foundational truths for every seeker.</p>
                        </div>
                        <button onclick="navigateTo('questions')" class="text-primary font-bold hover:underline">See Library →</button>
                    </div>
                    <div id="featured-cards" class="grid grid-cols-1 md:grid-cols-3 gap-8">
                        <!-- JS Injection -->
                    </div>
                </div>
            </div>
        </section>

        <!-- ================= LIBRARY ================= -->
        <section id="questions" class="view-section">
            <div class="max-w-6xl mx-auto px-4 py-12">
                <h1 class="text-4xl font-extrabold mb-8 dark:text-white">Article Library</h1>
                
                <div class="flex flex-col md:flex-row gap-8 items-start">
                    <!-- Sidebar Filters -->
                    <aside class="w-full md:w-64 space-y-8 flex-shrink-0">
                        <div>
                            <h3 class="text-xs font-bold uppercase tracking-widest text-slate-400 mb-4">Categories</h3>
                            <div id="category-list" class="space-y-1">
                                <!-- JS Injection -->
                            </div>
                        </div>
                        
                        <div class="bg-indigo-50 dark:bg-indigo-900/20 p-6 rounded-2xl">
                            <h4 class="font-bold mb-2 dark:text-indigo-300">New Articles weekly</h4>
                            <p class="text-sm text-slate-600 dark:text-slate-400 mb-4">Subscribe to our newsletter for latest updates.</p>
                            <input type="email" placeholder="Email" class="w-full px-4 py-2 rounded-lg mb-2 text-sm border dark:bg-slate-800 dark:border-slate-700">
                            <button class="w-full bg-primary text-white text-xs font-bold py-2 rounded-lg">Join Now</button>
                        </div>
                    </aside>

                    <!-- Main List -->
                    <div class="flex-grow space-y-6">
                        <div class="relative">
                            <input type="text" id="page-search" oninput="handleFilter()" placeholder="Filter by title or keywords..." class="w-full px-5 py-4 rounded-xl border border-slate-200 dark:border-slate-700 dark:bg-slate-800 dark:text-white outline-none focus:ring-2 focus:ring-primary shadow-sm">
                        </div>

                        <div id="all-questions-list" class="grid gap-4">
                            <!-- JS Injection -->
                        </div>
                        
                        <div id="no-results" class="hidden text-center py-20 bg-slate-50 dark:bg-slate-800/50 rounded-3xl">
                            <p class="text-xl font-bold dark:text-white">No results found.</p>
                            <p class="text-slate-500 mt-2">Try a different keyword or category.</p>
                        </div>

                        <!-- Pagination -->
                        <div id="pagination-controls" class="flex justify-center gap-2 pt-8"></div>
                    </div>
                </div>
            </div>
        </section>

        <!-- ================= ARTICLE VIEW ================= -->
        <section id="article" class="view-section">
            <div class="max-w-4xl mx-auto px-4 py-12">
                <div class="flex items-center gap-4 mb-10">
                    <button onclick="navigateTo('questions')" class="p-2 rounded-full bg-slate-100 dark:bg-slate-800 hover:bg-slate-200 transition">
                        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 19l-7-7m0 0l7-7m-7 7h18" /></svg>
                    </button>
                    <span id="article-path" class="text-sm font-medium text-slate-400">Library / Category</span>
                </div>

                <div class="bg-white dark:bg-slate-800 p-8 md:p-16 rounded-[2.5rem] shadow-xl border border-slate-100 dark:border-slate-700">
                    <div class="flex flex-col md:flex-row md:items-center justify-between gap-6 mb-12">
                        <span id="article-category" class="inline-block px-3 py-1 bg-primary/10 text-primary dark:text-indigo-300 text-xs font-bold rounded-full uppercase tracking-tighter">Category</span>
                        <div class="flex items-center gap-3">
                            <button onclick="copyArticleLink()" class="flex items-center gap-2 text-xs font-bold text-slate-500 hover:text-primary transition uppercase tracking-widest">
                                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8.684 13.342C8.886 12.938 9 12.482 9 12c0-.482-.114-.938-.316-1.342m0 2.684a3 3 0 110-2.684m0 2.684l6.632 3.316m-6.632-6l6.632-3.316m0 0a3 3 0 105.367-2.684 3 3 0 00-5.367 2.684zm0 9.316a3 3 0 105.368 2.684 3 3 0 00-5.368-2.684z" /></svg>
                                Share
                            </button>
                        </div>
                    </div>

                    <h1 id="article-title" class="text-4xl md:text-5xl font-black text-slate-900 dark:text-white mb-10 leading-tight">Article Title</h1>
                    
                    <div id="article-explanation" class="article-content text-lg text-slate-700 dark:text-slate-300 mb-12 leading-relaxed font-sans">
                        <!-- Content -->
                    </div>

                    <div class="relative p-8 md:p-12 bg-slate-50 dark:bg-slate-900/50 rounded-3xl border-l-8 border-primary my-16">
                        <svg class="absolute top-4 right-4 w-12 h-12 text-slate-200 dark:text-slate-700" fill="currentColor" viewBox="0 0 24 24"><path d="M14.017 21v-7.391c0-5.704 3.731-9.57 8.983-10.609l.995 2.151c-2.432.917-3.995 3.638-3.995 5.849h4v10h-9.983zm-14.017 0v-7.391c0-5.704 3.748-9.57 9-10.609l.996 2.151c-2.433.917-3.996 3.638-3.996 5.849h3.983v10h-9.983z" /></svg>
                        <h3 class="text-xs font-black text-slate-400 uppercase tracking-[0.3em] mb-8">Biblical Evidence</h3>
                        <div id="article-verses" class="space-y-10 relative z-10">
                            <!-- Verses -->
                        </div>
                    </div>

                    <div id="article-conclusion-box" class="p-8 bg-primary/5 dark:bg-primary/10 rounded-3xl border border-primary/20">
                        <h4 class="font-bold text-slate-900 dark:text-white mb-4 flex items-center gap-2">
                            <svg class="w-5 h-5 text-primary" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M18 10a8 8 0 11-16 0 8 8 0 0116 0zm-7-4a1 1 0 11-2 0 1 1 0 012 0zM9 9a1 1 0 000 2v3a1 1 0 001 1h1a1 1 0 100-2v-3a1 1 0 00-1-1H9z" clip-rule="evenodd"></path></svg>
                            Key Takeaway
                        </h4>
                        <p id="article-conclusion" class="text-slate-700 dark:text-slate-300 leading-relaxed"></p>
                    </div>
                </div>

                <!-- Related Articles -->
                <div class="mt-20">
                    <h3 class="text-2xl font-bold dark:text-white mb-8">Related Articles</h3>
                    <div id="related-articles" class="grid grid-cols-1 md:grid-cols-2 gap-6"></div>
                </div>
            </div>
        </section>

        <!-- ================= ABOUT ================= -->
        <section id="about" class="view-section">
            <div class="max-w-4xl mx-auto px-4 py-16">
                <div class="bg-white dark:bg-slate-800 p-10 md:p-16 rounded-[3rem] shadow-xl">
                    <h1 class="text-4xl font-extrabold mb-8 dark:text-white">Our Mission</h1>
                    <div class="prose prose-lg dark:prose-invert max-w-none text-slate-600 dark:text-slate-400 space-y-6">
                        <p>At <strong class="text-slate-900 dark:text-white underline decoration-primary decoration-4">Satyamnow.in</strong>, we believe that the most important questions in life have clear answers in the Bible.</p>
                        <p>Our platform was born out of a desire to provide seekers with a reliable, simple, and aesthetically pleasing place to study the Word of God. We focus on clarity, avoiding complex theological jargon, to make the Gospel accessible to everyone.</p>
                        
                        <div class="grid md:grid-cols-2 gap-8 mt-12">
                            <div class="p-6 bg-slate-50 dark:bg-slate-900/50 rounded-2xl">
                                <h3 class="font-bold text-slate-900 dark:text-white mb-2">Simplified</h3>
                                <p class="text-sm">We break down complex topics into easy-to-digest articles for beginners.</p>
                            </div>
                            <div class="p-6 bg-slate-50 dark:bg-slate-900/50 rounded-2xl">
                                <h3 class="font-bold text-slate-900 dark:text-white mb-2">Faithful</h3>
                                <p class="text-sm">Every answer is rooted deeply in the scriptures (NKJV translation).</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- ================= ASK US ================= -->
        <section id="ask" class="view-section">
            <div class="max-w-3xl mx-auto px-4 py-16">
                <div class="text-center mb-12">
                    <h1 class="text-4xl font-extrabold dark:text-white mb-4">Have a Question?</h1>
                    <p class="text-slate-500">If you couldn't find an answer in our library, ask us directly.</p>
                </div>

                <div class="bg-white dark:bg-slate-800 p-8 md:p-12 rounded-[2.5rem] shadow-2xl">
                    <form onsubmit="handleFormSubmit(event)" id="ask-form" class="space-y-6">
                        <div id="form-feedback" class="hidden p-4 rounded-xl text-center font-bold"></div>
                        
                        <div class="grid md:grid-cols-2 gap-6">
                            <div class="space-y-2">
                                <label class="text-sm font-bold uppercase tracking-wider text-slate-400 ml-1">Name</label>
                                <input type="text" placeholder="John Doe" class="w-full px-5 py-3 rounded-xl border dark:bg-slate-900 dark:border-slate-700 dark:text-white outline-none focus:ring-2 focus:ring-primary">
                            </div>
                            <div class="space-y-2">
                                <label class="text-sm font-bold uppercase tracking-wider text-slate-400 ml-1">Email</label>
                                <input type="email" placeholder="john@example.com" class="w-full px-5 py-3 rounded-xl border dark:bg-slate-900 dark:border-slate-700 dark:text-white outline-none focus:ring-2 focus:ring-primary">
                            </div>
                        </div>
                        <div class="space-y-2">
                            <label class="text-sm font-bold uppercase tracking-wider text-slate-400 ml-1">Your Question</label>
                            <textarea rows="5" required placeholder="What does the Bible say about..." class="w-full px-5 py-3 rounded-xl border dark:bg-slate-900 dark:border-slate-700 dark:text-white outline-none focus:ring-2 focus:ring-primary"></textarea>
                        </div>
                        <button type="submit" class="w-full bg-slate-900 dark:bg-primary text-white font-bold py-5 rounded-xl hover:shadow-2xl transition-all">Submit My Question</button>
                    </form>
                </div>
            </div>
        </section>
    </main>

    <!-- FOOTER -->
    <footer class="bg-white dark:bg-slate-900 border-t dark:border-slate-800 py-16 mt-auto">
        <div class="max-w-6xl mx-auto px-4 flex flex-col items-center">
            <span class="text-2xl font-black mb-8 dark:text-white">Satyam<span class="text-primary">now</span></span>
            <div class="flex flex-wrap justify-center gap-8 mb-12">
                <button onclick="navigateTo('home')" class="text-slate-400 hover:text-primary transition font-bold uppercase text-xs tracking-widest">Home</button>
                <button onclick="navigateTo('questions')" class="text-slate-400 hover:text-primary transition font-bold uppercase text-xs tracking-widest">Library</button>
                <button onclick="navigateTo('about')" class="text-slate-400 hover:text-primary transition font-bold uppercase text-xs tracking-widest">Mission</button>
                <a href="mailto:asksatyamnow@gmail.com" class="text-slate-400 hover:text-primary transition font-bold uppercase text-xs tracking-widest">Email</a>
            </div>
            <p class="text-slate-500 text-xs text-center leading-loose max-w-sm">
                &copy; 2024 Satyamnow.in. Dedicated to the glory of God. Scripture taken from the NKJV®. Copyright © 1982 by Thomas Nelson.
            </p>
        </div>
    </footer>

    <!-- MESSAGE TOAST -->
    <div id="toast" class="fixed bottom-8 left-1/2 -translate-x-1/2 bg-slate-900 text-white px-6 py-3 rounded-full text-sm font-bold shadow-2xl opacity-0 translate-y-10 transition-all pointer-events-none z-[100]">
        Copied to clipboard
    </div>

    <!-- SCRIPTS -->
    <script>
        const articles = [
            {
                id: "salvation-meaning", category: "Salvation", title: "What is salvation?",
                summary: "Discover God's free gift of rescue from the penalty of sin.",
                explanation: "<p>Salvation is the central message of the Bible. In its simplest form, it means being rescued from the righteous judgment of God against sin. Because God is holy and just, He cannot ignore wrongdoing. However, because He is also loving and merciful, He provided a way for us to be forgiven.</p><p>Salvation isn't something we earn through good deeds, religious rituals, or being a 'good person.' It is a gift that must be received through faith.</p>",
                verses: [
                    { text: "For by grace you have been saved through faith, and that not of yourselves; it is the gift of God, not of works, lest anyone should boast.", ref: "Ephesians 2:8-9" },
                    { text: "For the wages of sin is death, but the gift of God is eternal life in Christ Jesus our Lord.", ref: "Romans 6:23" }
                ],
                conclusion: "Salvation is a free gift from God, purchased by Jesus Christ on the cross and offered to everyone who trusts in Him."
            },
            {
                id: "who-is-jesus", category: "Jesus", title: "Who is Jesus Christ?",
                summary: "Unpack the identity of the most influential figure in history.",
                explanation: "<p>Jesus Christ is not just a great teacher or a prophet from the past. The Bible reveals Him as the Son of God—God in human flesh. He came to earth with a specific mission: to reveal God's character to us and to pay the debt for our sins.</p><p>He lived a perfect, sinless life, demonstrating total obedience to God the Father. By doing so, He became the only one qualified to be our substitute.</p>",
                verses: [
                    { text: "Jesus said to him, 'I am the way, the truth, and the life. No one comes to the Father except through Me.'", ref: "John 14:6" },
                    { text: "And we have seen and testify that the Father has sent the Son as Savior of the world.", ref: "1 John 4:14" }
                ],
                conclusion: "Jesus is both fully God and fully man, the only Mediator between God and humanity."
            },
            {
                id: "what-is-sin", category: "Sin", title: "What exactly is sin?",
                summary: "Understand the barrier that separates us from a holy God.",
                explanation: "<p>Many people think of sin only as 'big crimes,' but the Bible defines sin as any failure to meet God's perfect standard of holiness. It literally means 'to miss the mark.'</p><p>Sin includes not just the things we do (actions), but the things we say and the thoughts we harbor in our hearts. Because God is perfectly light, even a small 'darkness' cannot exist in His presence.</p>",
                verses: [
                    { text: "for all have sinned and fall short of the glory of God,", ref: "Romans 3:23" },
                    { text: "Everyone who sins breaks the law; in fact, sin is lawlessness.", ref: "1 John 3:4" }
                ],
                conclusion: "Sin is a universal problem that affects every human being, creating a spiritual debt that only God can pay."
            },
            {
                id: "does-god-exist", category: "God", title: "Does God really exist?",
                summary: "Exploring the evidence for an intelligent Creator.",
                explanation: "<p>The question of God's existence is the starting point of faith. The Bible doesn't try to 'prove' God exists; it starts with the fact that He does. However, God has left 'fingerprints' of His existence everywhere.</p><p>From the vastness of the cosmos to the intricate coding of DNA, creation screams of an intelligent Designer. Furthermore, the universal sense of 'right and wrong' inside every human heart points to a moral Lawgiver.</p>",
                verses: [
                    { text: "The heavens declare the glory of God; And the firmament shows His handiwork.", ref: "Psalm 19:1" },
                    { text: "For since the creation of the world His invisible attributes are clearly seen... even His eternal power and Godhead.", ref: "Romans 1:20" }
                ],
                conclusion: "God has revealed Himself through creation, our conscience, and ultimately through His Word and His Son."
            },
            {
                id: "holy-spirit-who", category: "God", title: "Who is the Holy Spirit?",
                summary: "Meet the third person of the Trinity and His role today.",
                explanation: "<p>The Holy Spirit is not an 'impersonal force' or a ghost. He is the third person of the Trinity—equal with the Father and the Son. When a person trusts in Jesus, the Holy Spirit comes to live inside them.</p><p>His role is to comfort us, guide us into truth, and empower us to live a life that pleases God. He also convicts the world of sin and points people toward Jesus.</p>",
                verses: [
                    { text: "But the Helper, the Holy Spirit, whom the Father will send in My name, He will teach you all things...", ref: "John 14:26" }
                ],
                conclusion: "The Holy Spirit is God's personal presence in the life of every believer."
            },
            {
                id: "why-read-bible", category: "Bible", title: "Why read the Bible?",
                summary: "Is this ancient book still relevant for the 21st century?",
                explanation: "<p>The Bible claims to be the 'God-breathed' Word of God. It is more than just a collection of history or poetry; it is a spiritual manual for life. It provides wisdom for our relationships, comfort for our sorrows, and light for our future.</p><p>Reading the Bible is the primary way we hear God speak. It doesn't just give us information; it has the power to transform our hearts.</p>",
                verses: [
                    { text: "Your word is a lamp to my feet And a light to my path.", ref: "Psalm 119:105" },
                    { text: "All Scripture is given by inspiration of God, and is profitable for doctrine, for reproof, for correction...", ref: "2 Timothy 3:16" }
                ],
                conclusion: "The Bible is the ultimate authority for truth and the most vital resource for a spiritual life."
            },
            {
                id: "heaven-real", category: "Heaven", title: "Is Heaven a real place?",
                summary: "What happens to us after we die?",
                explanation: "<p>The Bible speaks of Heaven as a real, physical place where God dwells in His full glory. It is described as a place of perfect restoration. There will be no more pain, no more death, and no more sorrow.</p><p>However, the greatest thing about Heaven is not the 'golden streets' or 'pearly gates'—it is the fact that we will be with God face-to-face, experiencing His love forever.</p>",
                verses: [
                    { text: "And God will wipe away every tear from their eyes; there shall be no more death, nor sorrow, nor crying.", ref: "Revelation 21:4" }
                ],
                conclusion: "Heaven is the eternal home for those who have been reconciled to God through Jesus Christ."
            },
            {
                id: "prayer-works", category: "Faith", title: "Does prayer really work?",
                summary: "Understanding the power and purpose of talking to God.",
                explanation: "<p>Prayer is simply communication with God. It isn't about repeating 'magic words' or trying to force God to do what we want. It is about aligning our hearts with His.</p><p>God promises to hear the prayers of those who seek Him. Sometimes He answers 'Yes,' sometimes 'No,' and sometimes 'Wait,' but He always answers according to His perfect wisdom and love.</p>",
                verses: [
                    { text: "The effective, fervent prayer of a righteous man avails much.", ref: "James 5:16" }
                ],
                conclusion: "Prayer is a powerful privilege that allows us to invite God's presence and power into our lives."
            }
        ];

        let currentCategory = "All";
        let searchQuery = "";
        let currentPage = 1;
        const itemsPerPage = 5;

        // Navigation
        function navigateTo(viewId) {
            document.querySelectorAll('.view-section').forEach(s => s.classList.remove('active'));
            document.getElementById(viewId).classList.add('active');
            document.getElementById('mobile-menu').classList.add('hidden');
            window.scrollTo(0, 0);

            // Update Nav Styles
            document.querySelectorAll('.nav-link').forEach(btn => {
                if (btn.innerText.toLowerCase() === (viewId === 'questions' ? 'library' : viewId)) {
                    btn.classList.add('text-primary', 'font-bold');
                } else {
                    btn.classList.remove('text-primary', 'font-bold');
                }
            });

            if (viewId === 'questions') renderLibrary();
        }

        // Theme Toggle
        function toggleTheme() {
            document.documentElement.classList.toggle('dark');
            const isDark = document.documentElement.classList.contains('dark');
            localStorage.setItem('theme', isDark ? 'dark' : 'light');
        }

        // Library Logic
        function setCategory(cat) {
            currentCategory = cat;
            currentPage = 1;
            renderLibrary();
        }

        function handleFilter() {
            searchQuery = document.getElementById('page-search').value.toLowerCase();
            currentPage = 1;
            renderLibrary();
        }

        function searchTag(tag) {
            navigateTo('questions');
            document.getElementById('page-search').value = tag;
            handleFilter();
        }

        function renderLibrary() {
            const list = document.getElementById('all-questions-list');
            const catList = document.getElementById('category-list');
            const noRes = document.getElementById('no-results');
            
            // Render Categories
            const categories = ["All", ...new Set(articles.map(a => a.category))];
            catList.innerHTML = categories.map(c => `
                <button onclick="setCategory('${c}')" class="block w-full text-left px-4 py-2 rounded-lg text-sm transition ${currentCategory === c ? 'bg-primary text-white font-bold' : 'text-slate-500 hover:bg-slate-100 dark:hover:bg-slate-800'}">
                    ${c}
                </button>
            `).join('');

            // Filter Articles
            const filtered = articles.filter(a => {
                const matchCat = currentCategory === "All" || a.category === currentCategory;
                const matchSearch = a.title.toLowerCase().includes(searchQuery) || a.summary.toLowerCase().includes(searchQuery);
                return matchCat && matchSearch;
            });

            if (filtered.length === 0) {
                list.innerHTML = '';
                noRes.classList.remove('hidden');
                document.getElementById('pagination-controls').innerHTML = '';
                return;
            }

            noRes.classList.add('hidden');
            
            // Pagination
            const totalPages = Math.ceil(filtered.length / itemsPerPage);
            const start = (currentPage - 1) * itemsPerPage;
            const end = start + itemsPerPage;
            const pageItems = filtered.slice(start, end);

            list.innerHTML = pageItems.map(a => `
                <div onclick="openArticle('${a.id}')" class="group bg-white dark:bg-slate-800 p-6 rounded-2xl border border-slate-100 dark:border-slate-700 shadow-sm hover:shadow-xl cursor-pointer transition-all">
                    <div class="flex justify-between items-start gap-4">
                        <div>
                            <span class="text-[10px] font-black text-primary uppercase tracking-[0.2em] mb-2 block">${a.category}</span>
                            <h3 class="text-xl font-bold dark:text-white group-hover:text-primary transition-colors mb-2">${a.title}</h3>
                            <p class="text-slate-500 dark:text-slate-400 text-sm line-clamp-2">${a.summary}</p>
                        </div>
                        <div class="p-2 rounded-lg bg-slate-50 dark:bg-slate-900 text-slate-400 group-hover:bg-primary group-hover:text-white transition-all">
                            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" /></svg>
                        </div>
                    </div>
                </div>
            `).join('');

            renderPagination(totalPages);
        }

        function renderPagination(total) {
            const container = document.getElementById('pagination-controls');
            if (total <= 1) { container.innerHTML = ''; return; }
            
            let html = '';
            for(let i=1; i<=total; i++) {
                html += `
                    <button onclick="goToPage(${i})" class="w-10 h-10 rounded-lg font-bold border transition ${currentPage === i ? 'bg-primary text-white border-primary' : 'bg-white dark:bg-slate-800 dark:border-slate-700 dark:text-white'}">
                        ${i}
                    </button>
                `;
            }
            container.innerHTML = html;
        }

        function goToPage(p) {
            currentPage = p;
            renderLibrary();
            window.scrollTo(0, 0);
        }

        // Article View
        function openArticle(id) {
            const a = articles.find(x => x.id === id);
            if (!a) return;

            document.getElementById('article-path').innerText = `Library / ${a.category}`;
            document.getElementById('article-category').innerText = a.category;
            document.getElementById('article-title').innerText = a.title;
            document.getElementById('article-explanation').innerHTML = a.explanation;
            document.getElementById('article-conclusion').innerText = a.conclusion;

            document.getElementById('article-verses').innerHTML = a.verses.map(v => `
                <div class="group">
                    <p class="text-xl md:text-2xl font-serif italic text-slate-800 dark:text-slate-100 mb-4 leading-relaxed transition-colors group-hover:text-primary">"${v.text}"</p>
                    <div class="flex items-center gap-4">
                        <div class="h-px flex-grow bg-slate-200 dark:bg-slate-700"></div>
                        <span class="text-xs font-black uppercase tracking-[0.2em] text-primary">${v.ref}</span>
                    </div>
                </div>
            `).join('');

            // Related
            const related = articles.filter(x => x.category === a.category && x.id !== a.id).slice(0, 2);
            document.getElementById('related-articles').innerHTML = related.map(r => `
                <div onclick="openArticle('${r.id}')" class="p-6 bg-white dark:bg-slate-800 rounded-2xl border dark:border-slate-700 cursor-pointer hover:border-primary transition shadow-sm">
                    <h4 class="font-bold dark:text-white mb-2">${r.title}</h4>
                    <p class="text-xs text-slate-500">${r.summary}</p>
                </div>
            `).join('');

            navigateTo('article');
        }

        function handleHomeSearch(e) {
            if (e.key === 'Enter') {
                const query = e.target.value;
                navigateTo('questions');
                document.getElementById('page-search').value = query;
                handleFilter();
            }
        }

        function copyArticleLink() {
            const dummy = document.createElement('input');
            document.body.appendChild(dummy);
            dummy.value = window.location.href;
            dummy.select();
            document.execCommand('copy');
            document.body.removeChild(dummy);

            const toast = document.getElementById('toast');
            toast.classList.remove('opacity-0', 'translate-y-10');
            setTimeout(() => toast.classList.add('opacity-0', 'translate-y-10'), 2000);
        }

        function handleFormSubmit(e) {
            e.preventDefault();
            const feedback = document.getElementById('form-feedback');
            feedback.innerText = "Processing...";
            feedback.className = "p-4 rounded-xl text-center font-bold bg-slate-100 text-slate-600 block";
            
            setTimeout(() => {
                feedback.innerText = "Your question has been sent! We'll reply soon.";
                feedback.className = "p-4 rounded-xl text-center font-bold bg-emerald-100 text-emerald-700 block";
                e.target.reset();
            }, 1500);
        }

        // Init
        window.onload = () => {
            // Set Dark Mode if preferred
            if (localStorage.getItem('theme') === 'dark') document.documentElement.classList.add('dark');
            
            // Render Featured on Home
            document.getElementById('featured-cards').innerHTML = articles.slice(0, 3).map((a, i) => `
                <div onclick="openArticle('${a.id}')" class="relative group p-8 bg-white dark:bg-slate-800 rounded-[2rem] shadow-sm hover:shadow-2xl transition-all cursor-pointer border border-slate-100 dark:border-slate-700 flex flex-col h-full">
                    <div class="text-4xl font-black text-slate-100 dark:text-slate-700 absolute top-6 right-8 transition-colors group-hover:text-primary/10">0${i+1}</div>
                    <span class="text-[10px] font-black text-primary uppercase tracking-[0.2em] mb-4">${a.category}</span>
                    <h3 class="text-2xl font-bold dark:text-white mb-4 leading-tight">${a.title}</h3>
                    <p class="text-slate-500 text-sm mb-8 flex-grow leading-relaxed">${a.summary}</p>
                    <div class="flex items-center gap-2 text-primary font-bold text-sm">
                        Learn More
                        <svg class="w-4 h-4 transition-transform group-hover:translate-x-2" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3" /></svg>
                    </div>
                </div>
            `).join('');

            // Mobile Menu
            document.getElementById('mobile-menu-btn').onclick = () => {
                document.getElementById('mobile-menu').classList.toggle('hidden');
            };
        };
    </script>
</body>
</html>

