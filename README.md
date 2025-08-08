<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Python Mastery Journey – Ritik</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        /* Custom styles for 3D effects, animations, and graphics */
        body {
            background: linear-gradient(135deg, #1e3a8a, #4c1d95);
            min-height: 100vh;
        }
        .card {
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            transform-style: preserve-3d;
        }
        .card:hover {
            transform: rotateY(10deg) rotateX(10deg) scale(1.05);
            box-shadow: 0 20px 30px rgba(0, 0, 0, 0.3);
        }
        .completed { color: #34d399; font-weight: 600; }
        .incomplete { color: #f87171; font-weight: 600; }
        .section-toggle:hover { cursor: pointer; color: #60a5fa; }
        .progress-bar { 
            transition: width 1s ease-in-out;
            background: linear-gradient(90deg, #34d399, #60a5fa);
        }
        .hero-bg {
            background: url('data:image/svg+xml,%3Csvg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320"%3E%3Cpath fill="%23ffffff" fill-opacity="0.2" d="M0,160L48,138.7C96,117,192,75,288,90.7C384,107,480,181,576,186.7C672,192,768,128,864,101.3C960,75,1056,85,1152,112C1248,139,1344,181,1392,202.7L1440,224L1440,0L1392,0C1344,0,1248,0,1152,0C1056,0,960,0,864,0C768,0,672,0,576,0C480,0,384,0,288,0C192,0,96,0,48,0L0,0Z"%3E%3C/path%3E%3C/svg%3E') no-repeat center;
            background-size: cover;
        }
        .dark .card { background: #1f2937; }
        .dark .completed { color: #6ee7b7; }
        .dark .incomplete { color: #f87171; }
        .fade-in { animation: fadeIn 1s ease-in; }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .floating-progress {
            position: sticky;
            top: 20px;
            z-index: 10;
        }
        .nav-link:hover { color: #34d399; transform: scale(1.1); }
    </style>
</head>
<body class="text-gray-100 transition-colors duration-300">
    <div class="container mx-auto p-6 max-w-5xl">
        <!-- Hero Banner -->
        <header class="text-center mb-12 hero-bg py-12 rounded-lg">
            <h1 class="text-5xl font-extrabold mb-4 flex items-center justify-center">
                <span class="text-6xl mr-2">🐍</span> Python Mastery Journey
            </h1>
            <p class="text-2xl text-gray-200 mb-2">By Ritik</p>
            <p class="text-lg text-gray-300 max-w-2xl mx-auto">
                A complete Python learning path – from beginner to advanced, building projects and solving problems daily.
            </p>
            <button id="theme-toggle" class="mt-6 px-6 py-3 bg-blue-600 text-white rounded-full hover:bg-blue-700 transition-transform transform hover:scale-105">
                Toggle Dark Mode
            </button>
        </header>

        <!-- Navigation -->
        <nav class="mb-8 flex flex-wrap gap-4 justify-center">
            <a href="#core-python" class="nav-link px-4 py-2 bg-blue-600 rounded-lg transition-transform">Core Python</a>
            <a href="#data-structures" class="nav-link px-4 py-2 bg-blue-600 rounded-lg transition-transform">Data Structures</a>
            <a href="#modules-packages" class="nav-link px-4 py-2 bg-blue-600 rounded-lg transition-transform">Modules</a>
            <a href="#oop" class="nav-link px-4 py-2 bg-blue-600 rounded-lg transition-transform">OOP</a>
            <a href="#file-exception" class="nav-link px-4 py-2 bg-blue-600 rounded-lg transition-transform">Files</a>
            <a href="#advanced-python" class="nav-link px-4 py-2 bg-blue-600 rounded-lg transition-transform">Advanced</a>
            <a href="#system-automation" class="nav-link px-4 py-2 bg-blue-600 rounded-lg transition-transform">Automation</a>
            <a href="#multithreading" class="nav-link px-4 py-2 bg-blue-600 rounded-lg transition-transform">Multithreading</a>
            <a href="#web-dev" class="nav-link px-4 py-2 bg-blue-600 rounded-lg transition-transform">Web Dev</a>
            <a href="#data-analysis" class="nav-link px-4 py-2 bg-blue-600 rounded-lg transition-transform">Data Analysis</a>
            <a href="#git-deployment" class="nav-link px-4 py-2 bg-blue-600 rounded-lg transition-transform">Git</a>
            <a href="#testing-debugging" class="nav-link px-4 py-2 bg-blue-600 rounded-lg transition-transform">Testing</a>
            <a href="#projects" class="nav-link px-4 py-2 bg-blue-600 rounded-lg transition-transform">Projects</a>
        </nav>

        <!-- Progress Overview -->
        <section class="mb-12 floating-progress">
            <div class="bg-gray-800 p-6 rounded-lg shadow-lg card">
                <h2 class="text-2xl font-semibold mb-4">📊 Progress Overview</h2>
                <p class="text-lg">Overall Completion: <span id="progress-text">0%</span></p>
                <div class="w-full bg-gray-700 rounded-full h-4 mt-2">
                    <div id="progress-bar" class="h-4 rounded-full progress-bar" style="width: 0%"></div>
                </div>
            </div>
        </section>

        <!-- Core Python -->
        <section id="core-python" class="mb-12 fade-in">
            <h2 class="text-3xl font-semibold mb-4 section-toggle" data-target="core-python-content">📘 Core Python – Level 1</h2>
            <div id="core-python-content" class="bg-gray-800 p-6 rounded-lg shadow-lg card">
                <ul class="list-disc pl-6 space-y-2">
                    <li class="completed">✅ Variables, Data Types</li>
                    <li class="completed">✅ Input & Output</li>
                    <li class="completed">✅ Type Casting</li>
                    <li class="completed">✅ Operators (Arithmetic, Logical, Bitwise)</li>
                    <li class="completed">✅ Conditional Statements (if, elif, else)</li>
                    <li class="completed">✅ Loops (for, while)</li>
                    <li class="completed">✅ Break, Continue, Pass</li>
                    <li class="completed">✅ range(), len(), id(), type()</li>
                    <li class="completed">✅ Functions & Return Values</li>
                    <li class="completed">✅ Default Arguments, Keyword Arguments</li>
                    <li class="completed">✅ Lambda Functions</li>
                    <li class="completed">✅ Map, Filter, Reduce</li>
                    <li class="completed">✅ zip(), enumerate(), all(), any()</li>
                    <li class="completed">✅ Recursion</li>
                </ul>
            </div>
        </section>

        <!-- Data Structures -->
        <section id="data-structures" class="mb-12 fade-in">
            <h2 class="text-3xl font-semibold mb-4 section-toggle" data-target="data-structures-content">🧰 Data Structures – Level 2</h2>
            <div id="data-structures-content" class="bg-gray-800 p-6 rounded-lg shadow-lg card">
                <ul class="list-disc pl-6 space-y-2">
                    <li class="completed">✅ Lists – Indexing, Slicing, Methods</li>
                    <li class="completed">✅ Tuples – Immutable sequences</li>
                    <li class="completed">✅ Sets – Unique collections</li>
                    <li class="completed">✅ Dictionaries – Key-value pairs</li>
                    <li class="completed">✅ List, Set, Dict Comprehensions</li>
                    <li class="completed">✅ Nested Structures</li>
                </ul>
            </div>
        </section>

        <!-- Modules & Packages -->
        <section id="modules-packages" class="mb-12 fade-in">
            <h2 class="text-3xl font-semibold mb-4 section-toggle" data-target="modules-packages-content">🎯 Modules & Packages – Level 3</h2>
            <div id="modules-packages-content" class="bg-gray-800 p-6 rounded-lg shadow-lg card">
                <ul class="list-disc pl-6 space-y-2">
                    <li class="completed">✅ Importing Modules</li>
                    <li class="completed">✅ Custom Modules</li>
                    <li class="completed">✅ Built-in Modules (math, random, datetime, etc.)</li>
                    <li class="completed">✅ Exploring dir() and help()</li>
                    <li class="completed">✅ pip & installing packages</li>
                </ul>
            </div>
        </section>

        <!-- OOP -->
        <section id="oop" class="mb-12 fade-in">
            <h2 class="text-3xl font-semibold mb-4 section-toggle" data-target="oop-content">🧪 Object-Oriented Programming (OOP) – Level 4</h2>
            <div id="oop-content" class="bg-gray-800 p-6 rounded-lg shadow-lg card">
                <ul class="list-disc pl-6 space-y-2">
                    <li class="completed">✅ Classes & Objects</li>
                    <li class="completed">✅ __init__() Constructor</li>
                    <li class="completed">✅ Class vs Instance Variables</li>
                    <li class="completed">✅ Methods: Instance, Class, Static</li>
                    <li class="completed">✅ Inheritance (Single, Multi-level, Multiple)</li>
                    <li class="completed">✅ Encapsulation</li>
                    <li class="completed">✅ Abstraction</li>
                    <li class="completed">✅ Polymorphism</li>
                    <li class="completed">✅ Dunder Methods (__str__, __len__, etc.)</li>
                    <li class="completed">✅ Class Decorators, Properties</li>
                </ul>
            </div>
        </section>

        <!-- File & Exception Handling -->
        <section id="file-exception" class="mb-12 fade-in">
            <h2 class="text-3xl font-semibold mb-4 section-toggle" data-target="file-exception-content">🗂️ File & Exception Handling – Level 5</h2>
            <div id="file-exception-content" class="bg-gray-800 p-6 rounded-lg shadow-lg card">
                <ul class="list-disc pl-6 space-y-2">
                    <li class="completed">✅ Read/Write Files</li>
                    <li class="completed">✅ With Statement (Context Manager)</li>
                    <li class="completed">✅ CSV File Handling</li>
                    <li class="completed">✅ JSON File Handling</li>
                    <li class="completed">✅ Try, Except, Finally</li>
                    <li class="completed">✅ Custom Exception Classes</li>
                    <li class="completed">✅ Raising Exceptions</li>
                </ul>
            </div>
        </section>

        <!-- Advanced Python -->
        <section id="advanced-python" class="mb-12 fade-in">
            <h2 class="text-3xl font-semibold mb-4 section-toggle" data-target="advanced-python-content">🧠 Advanced Python – Level 6</h2>
            <div id="advanced-python-content" class="bg-gray-800 p-6 rounded-lg shadow-lg card">
                <ul class="list-disc pl-6 space-y-2">
                    <li class="completed">✅ Iterators & Generators</li>
                    <li class="completed">✅ Decorators (Function & Class)</li>
                    <li class="completed">✅ Regular Expressions (Regex)</li>
                    <li class="completed">✅ Type Hinting & Annotations</li>
                    <li class="completed">✅ *args, **kwargs</li>
                    <li class="completed">✅ Dataclasses</li>
                    <li class="completed">✅ time, calendar modules</li>
                    <li class="completed">✅ os, sys, platform, getpass</li>
                    <li class="completed">✅ Logging</li>
                    <li class="completed">✅ Virtual Environments (venv, pipenv)</li>
                    <li class="completed">✅ Code Quality (pylint, black, isort)</li>
                    <li class="completed">✅ Packing & Unpacking Operators</li>
                </ul>
            </div>
        </section>

        <!-- System, Automation & Web -->
        <section id="system-automation" class="mb-12 fade-in">
            <h2 class="text-3xl font-semibold mb-4 section-toggle" data-target="system-automation-content">💻 System, Automation & Web – Level 7</h2>
            <div id="system-automation-content" class="bg-gray-800 p-6 rounded-lg shadow-lg card">
                <ul class="list-disc pl-6 space-y-2">
                    <li class="completed">✅ Web Scraping (with requests, BeautifulSoup)</li>
                    <li class="completed">✅ Sending Emails (SMTP)</li>
                    <li class="completed">✅ File Renamer / Organizer Scripts</li>
                    <li class="completed">✅ PDF / Excel Automation (with PyPDF2, openpyxl)</li>
                    <li class="completed">✅ Tkinter GUI basics</li>
                    <li class="completed">✅ CLI Tools with argparse</li>
                    <li class="completed">✅ Working with APIs (GET, POST)</li>
                    <li class="completed">✅ Python + SQL (SQLite, MySQL)</li>
                </ul>
            </div>
        </section>

        <!-- Multithreading & Multiprocessing -->
        <section id="multithreading" class="mb-12 fade-in">
            <h2 class="text-3xl font-semibold mb-4 section-toggle" data-target="multithreading-content">🧵 Multithreading & Multiprocessing – Level 8</h2>
            <div id="multithreading-content" class="bg-gray-800 p-6 rounded-lg shadow-lg card">
                <ul class="list-disc pl-6 space-y-2">
                    <li class="completed">✅ threading module</li>
                    <li class="completed">✅ multiprocessing module</li>
                    <li class="completed">✅ Parallel Execution</li>
                    <li class="completed">✅ Asyncio basics</li>
                </ul>
            </div>
        </section>

        <!-- Web Development -->
        <section id="web-dev" class="mb-12 fade-in">
            <h2 class="text-3xl font-semibold mb-4 section-toggle" data-target="web-dev-content">🌐 Web Development (Basics) – Level 9</h2>
            <div id="web-dev-content" class="bg-gray-800 p-6 rounded-lg shadow-lg card">
                <ul class="list-disc pl-6 space-y-2">
                    <li class="completed">✅ Flask – Routes, Templates</li>
                    <li class="incomplete">❌ Django – Models, Views, Admin</li>
                    <li class="incomplete">❌ FastAPI (Optional)</li>
                    <li class="incomplete">❌ Hosting Python App on Render/Heroku</li>
                </ul>
            </div>
        </section>

        <!-- Data Analysis & Visualization -->
        <section id="data-analysis" class="mb-12 fade-in">
            <h2 class="text-3xl font-semibold mb-4 section-toggle" data-target="data-analysis-content">📊 Data Analysis & Visualization – Level 10</h2>
            <div id="data-analysis-content" class="bg-gray-800 p-6 rounded-lg shadow-lg card">
                <ul class="list-disc pl-6 space-y-2">
                    <li class="incomplete">❌ NumPy (Basics)</li>
                    <li class="incomplete">❌ Pandas (DataFrames, CSV, Excel)</li>
                    <li class="incomplete">❌ Matplotlib (Plotting)</li>
                    <li class="incomplete">❌ Seaborn (Charts)</li>
                    <li class="incomplete">❌ Plotly (Interactive Graphs)</li>
                </ul>
            </div>
        </section>

        <!-- Git & Deployment -->
        <section id="git-deployment" class="mb-12 fade-in">
            <h2 class="text-3xl font-semibold mb-4 section-toggle" data-target="git-deployment-content">📦 Git & Deployment</h2>
            <div id="git-deployment-content" class="bg-gray-800 p-6 rounded-lg shadow-lg card">
                <ul class="list-disc pl-6 space-y-2">
                    <li class="completed">✅ Git & GitHub</li>
                    <li class="completed">✅ README.md creation</li>
                    <li class="completed">✅ Pushing Projects</li>
                    <li class="incomplete">❌ Docker (Basic use)</li>
                    <li class="incomplete">❌ CI/CD Intro</li>
                </ul>
            </div>
        </section>

        <!-- Testing & Debugging -->
        <section id="testing-debugging" class="mb-12 fade-in">
            <h2 class="text-3xl font-semibold mb-4 section-toggle" data-target="testing-debugging-content">🧪 Testing & Debugging</h2>
            <div id="testing-debugging-content" class="bg-gray-800 p-6 rounded-lg shadow-lg card">
                <ul class="list-disc pl-6 space-y-2">
                    <li class="completed">✅ Unit Testing (unittest)</li>
                    <li class="incomplete">❌ pytest Framework</li>
                    <li class="completed">✅ Debugging Tools (pdb, breakpoints)</li>
                    <li class="incomplete">❌ Writing Test Cases</li>
                </ul>
            </div>
        </section>

        <!-- Projects -->
        <section id="projects" class="mb-12 fade-in">
            <h2 class="text-3xl font-semibold mb-4 section-toggle" data-target="projects-content">🛠 Projects (Mini to Major)</h2>
            <div id="projects-content" class="bg-gray-800 p-6 rounded-lg shadow-lg card">
                <ul class="list-disc pl-6 space-y-2">
                    <li class="incomplete">❌ CLI Calculator</li>
                    <li class="incomplete">❌ Todo App</li>
                    <li class="incomplete">❌ Quiz Game</li>
                    <li class="incomplete">❌ File Organizer</li>
                    <li class="incomplete">❌ Web Scraper Tool</li>
                    <li class="incomplete">❌ Flask Portfolio App</li>
                    <li class="incomplete">❌ ChatBot with AI</li>
                    <li class="incomplete">❌ Weather App (API-based)</li>
                    <li class="incomplete">❌ Automation Scripts Collection</li>
                    <li class="incomplete">❌ Full Django App (with Admin Panel)</li>
                </ul>
            </div>
        </section>

        <!-- Final Goal -->
        <section class="mb-12 fade-in">
            <h2 class="text-3xl font-semibold mb-4">🏁 Final Goal</h2>
            <div class="bg-gray-800 p-6 rounded-lg shadow-lg card">
                <p class="text-lg italic">
                    Master Python to the level where I can <strong>automate, build, deploy, analyze, and innovate</strong> in real-world problems under <strong>RitSky Group</strong>.
                </p>
            </div>
        </section>

        <!-- Motivation -->
        <section class="mb-12 fade-in">
            <h2 class="text-3xl font-semibold mb-4">🔥 Motivation</h2>
            <div class="bg-gray-800 p-6 rounded-lg shadow-lg card">
                <p class="text-lg italic">
                    “I don't learn just to pass — I learn to build, break, and rebuild with mastery.”
                </p>
            </div>
        </section>

        <!-- Daily Logs -->
        <section class="mb-12 fade-in">
            <h2 class="text-3xl font-semibold mb-4">📆 Daily Logs</h2>
            <div class="bg-gray-800 p-6 rounded-lg shadow-lg card">
                <p class="text-lg">
                    Check out my <a href="daily_log.md" class="text-blue-400 hover:underline">daily_log.md</a> for my daily progress log.
                </p>
            </div>
        </section>

        <!-- Connect -->
        <section class="mb-12 fade-in">
            <h2 class="text-3xl font-semibold mb-4">🔗 Connect with Me</h2>
            <div class="bg-gray-800 p-6 rounded-lg shadow-lg card">
                <p class="text-lg">📫 <a href="mailto:ritik74820@gmail.com" class="text-blue-400 hover:underline">ritik74820@gmail.com</a></p>
            </div>
        </section>

        <!-- Footer -->
        <footer class="text-center mt-12 fade-in">
            <p class="text-gray-400">Crafted with ❤️ by Ritik</p>
        </footer>
    </div>

    <script>
        // Theme Toggle
        const themeToggle = document.getElementById('theme-toggle');
        themeToggle.addEventListener('click', () => {
            document.body.classList.toggle('dark');
            localStorage.setItem('theme', document.body.classList.contains('dark') ? 'dark' : 'light');
        });

        // Load theme from localStorage
        if (localStorage.getItem('theme') === 'dark') {
            document.body.classList.add('dark');
        }

        // Collapsible Sections
        document.querySelectorAll('.section-toggle').forEach(toggle => {
            toggle.addEventListener('click', () => {
                const targetId = toggle.getAttribute('data-target');
                const section = document.getElementById(targetId);
                section.classList.toggle('hidden');
                section.classList.toggle('fade-in');
            });
        });

        // Progress Calculation
        const allItems = document.querySelectorAll('li.completed, li.incomplete');
        const completedItems = document.querySelectorAll('li.completed');
        const progress = (completedItems.length / allItems.length) * 100;
        document.getElementById('progress-text').textContent = `${progress.toFixed(1)}%`;
        document.getElementById('progress-bar').style.width = `${progress}%`;

        // Smooth Scroll for Navigation
        document.querySelectorAll('.nav-link').forEach(link => {
            link.addEventListener('click', (e) => {
                e.preventDefault();
                const targetId = link.getAttribute('href').substring(1);
                document.getElementById(targetId).scrollIntoView({ behavior: 'smooth' });
            });
        });
    </script>
</body>
</html>
