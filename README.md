<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Envy Digital | AI Automation & Marketing Systems</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap" rel="stylesheet">
    <style>
        /* Define the custom dark theme and vibrant orange accent */
        :root {
            --color-primary: #10151E; /* Deep Navy Blue from logo background */
            --color-accent: #FF6600; /* Vibrant Orange for CTA/Highlight */
            --color-text: #E5E7EB; /* Light Gray Text */
        }
        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--color-primary);
            color: var(--color-text);
            overflow-x: hidden;
        }

        /* Subtle Glow/Shadow for key elements */
        .glow-button {
            box-shadow: 0 0 15px rgba(255, 102, 0, 0.5);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .glow-button:hover {
            box-shadow: 0 0 30px rgba(255, 102, 0, 0.8);
            transform: translateY(-2px);
        }

        /* Animation classes for scroll effects (simulating AOS) */
        .fade-in {
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.8s ease-out, transform 0.8s ease-out;
        }
        .fade-in.is-visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Geometric background visual for Hero */
        .hero-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            overflow: hidden;
            opacity: 0.1;
        }
        .hero-bg::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle at 70% 30%, var(--color-accent) 0%, transparent 40%),
                        radial-gradient(circle at 30% 70%, #00FFFF 0%, transparent 40%);
            animation: rotate-bg 60s linear infinite;
        }
        @keyframes rotate-bg {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        /* Flywheel visual line connector */
        .flywheel-connector {
            position: absolute;
            z-index: 0;
            opacity: 0.3;
        }
        
        /* Custom Message Box and Loader Styles */
        #custom-message-box {
            display: none;
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            z-index: 1000;
            max-width: 90vw;
            width: 500px;
            background-color: var(--color-primary);
            border: 2px solid var(--color-accent);
            border-radius: 12px;
            padding: 24px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
        }
        #custom-message-overlay {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            z-index: 999;
        }
        .spinner {
            border: 4px solid rgba(255, 255, 255, 0.3);
            border-top: 4px solid var(--color-accent);
            border-radius: 50%;
            width: 24px;
            height: 24px;
            animation: spin 1s linear infinite;
            display: inline-block;
            margin-right: 8px;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
    </style>
</head>
<body>

    <!-- Custom Message Box and Overlay --><div id="custom-message-overlay" onclick="closeCustomMessageBox()"></div>
    <div id="custom-message-box">
        <h3 id="message-title" class="text-2xl font-bold mb-4 text-orange-400"></h3>
        <div id="message-content" class="text-gray-300 mb-6 whitespace-pre-wrap"></div>
        <button onclick="closeCustomMessageBox()" class="w-full px-4 py-2 bg-orange-600 text-white font-semibold rounded-lg hover:bg-orange-700 transition duration-300">
            Close
        </button>
    </div>
    
    <!-- Header & Navigation --><header class="sticky top-0 z-50 bg-color-primary/90 backdrop-blur-sm shadow-lg">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4 flex justify-between items-center">
            <!-- Logo (Using the uploaded file reference) --><a href="#" class="flex items-center space-x-2">
                <img src="uploaded:3.png" alt="Envy Digital Logo" class="h-8 w-auto">
            </a>
            <nav class="hidden md:flex space-x-8 text-sm font-medium">
                <a href="#flywheel" class="hover:text-amber-500 transition duration-300">Flywheel</a>
                <a href="#benefits" class="hover:text-amber-500 transition duration-300">Benefits</a>
                <a href="#proof" class="hover:text-amber-500 transition duration-300">Proof</a>
                <a href="#services" class="hover:text-amber-500 transition duration-300">Services</a>
            </nav>
            <a href="#cta" class="hidden sm:block px-4 py-2 text-sm font-semibold rounded-lg bg-white text-gray-900 transition duration-300 hover:bg-gray-200">
                Contact Us
            </a>
        </div>
    </header>

    <main>
        <!-- 1. Hero Section --><section class="relative pt-24 pb-32 overflow-hidden min-h-screen flex items-center">
            <!-- Geometric/Abstract AI Background Visual --><div class="hero-bg"></div>

            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10 text-center">
                <p class="text-sm font-semibold uppercase tracking-widest text-orange-400 mb-4 fade-in">
                    The Future of Scalable Growth
                </p>
                <h1 class="text-5xl sm:text-7xl lg:text-8xl font-extrabold text-white leading-tight mb-6 fade-in" style="transition-delay: 0.1s;">
                    Automate Your Growth with <span class="text-transparent bg-clip-text bg-gradient-to-r from-orange-400 to-red-600">AI-Driven Systems</span>
                </h1>
                <p class="max-w-3xl mx-auto text-xl text-gray-400 mb-10 fade-in" style="transition-delay: 0.2s;">
                    Envy Digital designs and implements autonomous marketing funnels and complete business workflows, turning manual effort into self-sustaining revenue flywheels that scale infinitely.
                </p>
                <div class="fade-in mb-16" style="transition-delay: 0.3s;">
                    <a href="#cta" class="glow-button inline-block px-10 py-4 text-lg font-bold rounded-xl text-white bg-orange-600 hover:bg-orange-700 transition duration-300 shadow-xl">
                        Book a Free Automation Strategy Call
                    </a>
                </div>

                <!-- ✨ AI Headline Generator --><div id="headline-generator" class="max-w-xl mx-auto p-6 bg-gray-900 rounded-xl border border-gray-700 fade-in" style="transition-delay: 0.5s;">
                    <p class="text-sm font-semibold text-white mb-3">
                        <span class="text-orange-400">Test Our AI:</span> Generate a high-converting headline for your business.
                    </p>
                    <textarea id="business-description" class="w-full p-3 mb-4 bg-gray-800 border border-gray-700 rounded-lg text-sm text-gray-200 placeholder-gray-500 focus:ring-orange-500 focus:border-orange-500" rows="2" placeholder="Describe your business in one sentence (e.g., 'B2B SaaS platform for financial reporting')."></textarea>
                    <button id="headline-button" onclick="generateHeadline()" class="glow-button w-full px-8 py-3 text-sm font-bold rounded-xl text-white bg-cyan-600 hover:bg-cyan-700 transition duration-300">
                        Generate AI Headline Suggestions ✨
                    </button>
                    <div id="headline-output" class="mt-4 text-left text-sm text-gray-400 hidden"></div>
                </div>

            </div>
        </section>

        <!-- 2. How It Works (AI Flywheel Section) --><!-- ... existing flywheel section ... --><section id="flywheel" class="py-24 sm:py-32 border-t border-gray-800">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
                <h2 class="text-4xl font-bold text-white mb-4 fade-in">The AI Flywheel System</h2>
                <p class="max-w-2xl mx-auto text-gray-400 text-lg mb-16 fade-in" style="transition-delay: 0.1s;">
                    We build integrated systems where every result feeds back into the process, creating perpetual, scalable growth.
                </p>

                <div class="relative flex flex-col md:flex-row justify-between items-center space-y-12 md:space-y-0 md:space-x-8">
                    <!-- Step 1: Input Data --><div class="w-full md:w-1/3 p-6 bg-gray-900 rounded-2xl shadow-2xl relative z-10 fade-in" style="transition-delay: 0.2s;">
                        <div class="text-5xl mb-4 text-orange-500">⚙️</div>
                        <h3 class="text-xl font-semibold mb-2 text-white">1. Input Data & Systems</h3>
                        <p class="text-gray-400">We connect your CRM, ad platforms, and existing data sources, consolidating all customer information into a single AI-ready matrix.</p>
                    </div>

                    <!-- Arrow 1 (Desktop) --><div class="hidden md:block flywheel-connector border-t-2 border-dashed border-orange-600 w-16"></div>
                    <!-- Arrow 1 (Mobile) --><div class="md:hidden flywheel-connector border-l-2 border-dashed border-orange-600 h-16 absolute left-1/2 -translate-x-1/2 top-[calc(100%)]"></div>

                    <!-- Step 2: AI Automates --><div class="w-full md:w-1/3 p-6 bg-gray-900 rounded-2xl shadow-2xl relative z-10 fade-in" style="transition-delay: 0.4s;">
                        <div class="text-5xl mb-4 text-cyan-400">🧠</div>
                        <h3 class="text-xl font-semibold mb-2 text-white">2. AI Automation & Action</h3>
                        <p class="text-gray-400">AI agents autonomously handle lead qualification, content personalization, outreach, scheduling, and reporting—24/7, without human latency.</p>
                    </div>

                    <!-- Arrow 2 (Desktop) --><div class="hidden md:block flywheel-connector border-t-2 border-dashed border-orange-600 w-16"></div>
                    <!-- Arrow 2 (Mobile) --><div class="md:hidden flywheel-connector border-l-2 border-dashed border-orange-600 h-16 absolute left-1/2 -translate-x-1/2 top-[calc(200%)]"></div>

                    <!-- Step 3: Scalable Results & Feedback --><div class="w-full md:w-1/3 p-6 bg-gray-900 rounded-2xl shadow-2xl relative z-10 fade-in" style="transition-delay: 0.6s;">
                        <div class="text-5xl mb-4 text-red-500">📈</div>
                        <h3 class="text-xl font-semibold mb-2 text-white">3. Self-Sustaining Scale</h3>
                        <p class="text-gray-400">The results (conversions, cost data, engagement) are analyzed, automatically refining the AI's strategies and driving perpetual optimization and revenue scale.</p>
                    </div>
                </div>

            </div>
        </section>
        <!-- ... existing benefits section ... --><section id="benefits" class="py-24 sm:py-32 border-t border-gray-800">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-16">
                    <span class="text-sm font-semibold uppercase tracking-wider text-orange-500 fade-in">Transform Your Operations</span>
                    <h2 class="text-4xl font-bold text-white mt-2 fade-in">Why Switch to AI Automation Now?</h2>
                </div>
                
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
                    <!-- Benefit 1 --><div class="p-8 border border-gray-700 rounded-xl bg-gray-900/50 hover:bg-gray-900 transition duration-300 fade-in">
                        <div class="text-4xl text-orange-500 mb-4">⏱️</div>
                        <h3 class="text-xl font-semibold text-white mb-3">Save Hundreds of Hours</h3>
                        <p class="text-gray-400">Automate repetitive business tasks like data entry, reporting, and customer service follow-ups instantly.</p>
                    </div>
                    <!-- Benefit 2 --><div class="p-8 border border-gray-700 rounded-xl bg-gray-900/50 hover:bg-gray-900 transition duration-300 fade-in" style="transition-delay: 0.1s;">
                        <div class="text-4xl text-cyan-500 mb-4">🚀</div>
                        <h3 class="text-xl font-semibold text-white mb-3">AI-Powered Growth Engine</h3>
                        <p class="text-gray-400">Turn your marketing funnels into intelligent, self-optimizing systems that consistently drive high-quality leads.</p>
                    </div>
                    <!-- Benefit 3 --><div class="p-8 border border-gray-700 rounded-xl bg-gray-900/50 hover:bg-gray-900 transition duration-300 fade-in" style="transition-delay: 0.2s;">
                        <div class="text-4xl text-red-500 mb-4">💰</div>
                        <h3 class="text-xl font-semibold text-white mb-3">Scale Revenue, Not Workload</h3>
                        <p class="text-gray-400">Increase your output and revenue capacity without the proportional increase in staffing or manual labor costs.</p>
                    </div>
                    <!-- Benefit 4 --><div class="p-8 border border-gray-700 rounded-xl bg-gray-900/50 hover:bg-gray-900 transition duration-300 fade-in" style="transition-delay: 0.3s;">
                        <div class="text-4xl text-green-500 mb-4">🎯</div>
                        <h3 class="text-xl font-semibold text-white mb-3">24/7 Precision Engagement</h3>
                        <p class="text-gray-400">Ensure every lead receives an instant, personalized response, maximizing conversion windows around the clock.</p>
                    </div>
                </div>
            </div>
        </section>
        <!-- ... existing proof section ... --><section id="proof" class="py-24 sm:py-32 bg-gray-900 border-y border-gray-800">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="md:grid md:grid-cols-2 md:gap-12 items-center">
                    <div class="mb-12 md:mb-0 fade-in">
                        <span class="text-sm font-semibold uppercase tracking-wider text-orange-500">Real Results, Automated</span>
                        <h2 class="text-4xl font-bold text-white mt-2 mb-6">Quantifiable Success, Powered by AI</h2>
                        <p class="text-lg text-gray-400">AI isn't a theory; it's a proven catalyst for operational efficiency and exponential growth. We build solutions that deliver measurable results—fast.</p>
                    </div>
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-8">
                        <!-- Stat 1 --><div class="p-6 border-l-4 border-orange-500 rounded-lg shadow-lg bg-color-primary fade-in" style="transition-delay: 0.1s;">
                            <p class="text-5xl font-extrabold text-orange-500">3x Faster</p>
                            <p class="text-sm text-gray-300 mt-2">Lead Response Time</p>
                            <p class="text-xs text-gray-500 mt-1">For a B2B SaaS client using our AI qualification chatbots.</p>
                        </div>
                        <!-- Stat 2 --><div class="p-6 border-l-4 border-cyan-500 rounded-lg shadow-lg bg-color-primary fade-in" style="transition-delay: 0.2s;">
                            <p class="text-5xl font-extrabold text-cyan-500">40% Reduced</p>
                            <p class="text-sm text-gray-300 mt-2">Operational Costs</p>
                            <p class="text-xs text-gray-500 mt-1">Through automated data entry, reporting, and email management.</p>
                        </div>
                        <!-- Testimonial Carousel Placeholder --><div class="sm:col-span-2 mt-4 fade-in" style="transition-delay: 0.3s;">
                            <div class="p-6 bg-gray-800 rounded-xl border border-gray-700">
                                <p class="text-lg italic text-gray-300">"The AI Funnel system transformed our workflow. We went from processing leads manually to fully automated qualification in less than two weeks. It's truly self-sustaining."</p>
                                <p class="mt-4 font-semibold text-white">— Sarah K., CMO, TechStart Inc.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 5. Services Section --><section id="services" class="py-24 sm:py-32">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-16">
                    <span class="text-sm font-semibold uppercase tracking-wider text-white">Our Core Expertise</span>
                    <h2 class="text-4xl font-bold text-orange-500 mt-2">End-to-End AI System Design</h2>
                </div>

                <div class="grid grid-cols-1 lg:grid-cols-2 gap-12">
                    <!-- Service Group 1: Funnel & Lead --><div class="space-y-6 fade-in">
                        <h3 class="text-2xl font-bold border-b border-gray-700 pb-2 text-white">Marketing Automation</h3>
                        <div class="p-6 bg-gray-900 rounded-xl hover:shadow-2xl hover:shadow-orange-900/50 transition duration-300">
                            <h4 class="text-xl font-semibold text-orange-400 mb-2">AI Funnel Automation</h4>
                            <p class="text-gray-400">Design and deployment of complete, hands-off funnels using AI to identify, qualify, and convert leads with perfect timing and personalization.</p>
                        </div>
                        <div class="p-6 bg-gray-900 rounded-xl hover:shadow-2xl hover:shadow-cyan-900/50 transition duration-300">
                            <h4 class="text-xl font-semibold text-orange-400 mb-2">Lead Nurturing & Chatbots</h4>
                            <p class="text-gray-400">24/7 conversational AI agents embedded in your website and email sequence for instant, natural, and highly effective lead nurturing.</p>
                        </div>
                    </div>

                    <!-- Service Group 2: Operations & Data --><div class="space-y-6 fade-in" style="transition-delay: 0.2s;">
                        <h3 class="text-2xl font-bold border-b border-gray-700 pb-2 text-white">Business System Integration</h3>
                        <div class="p-6 bg-gray-900 rounded-xl hover:shadow-2xl hover:shadow-orange-900/50 transition duration-300">
                            <h4 class="text-xl font-semibold text-orange-400 mb-2">Data-Driven Ad Management</h4>
                            <p class="text-gray-400">AI monitors ad performance in real-time and automatically adjusts budgets, audience segments, and creative variants for maximum ROI.</p>
                        </div>
                        <div class="p-6 bg-gray-900 rounded-xl hover:shadow-2xl hover:shadow-cyan-900/50 transition duration-300">
                            <h4 class="text-xl font-semibold text-orange-400 mb-2">Business Task Automation</h4>
                            <p class="text-gray-400">Automate internal tasks, including CRM updates, email triage, report generation, and cross-platform data synchronization.</p>
                        </div>
                    </div>
                </div>
                
                <!-- Subtle Marketing Integration Highlight --><div class="mt-16 p-8 bg-orange-600/10 border border-orange-600 rounded-xl text-center fade-in" style="transition-delay: 0.4s;">
                    <p class="text-lg text-orange-300 font-medium">
                        <span class="font-bold text-white">Seamless Integration:</span> Our systems work with your existing paid ads, social content, and CRM tools (HubSpot, Salesforce, etc.) to unify your digital presence.
                    </p>
                </div>

            </div>
        </section>

        <!-- ✨ AI Audit Insight Generator Section (New) --><section id="ai-audit" class="py-24 sm:py-32 bg-gray-900 border-y border-gray-800">
            <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 text-center fade-in">
                <span class="text-sm font-semibold uppercase tracking-wider text-orange-500">Instant Strategic Value</span>
                <h2 class="text-4xl font-bold text-white mt-2 mb-6">Get a Quick AI Automation Insight ✨</h2>
                <p class="text-lg text-gray-400 mb-8">
                    Enter your primary business objective below and our AI will suggest one high-impact automation strategy tailored to your goal.
                </p>
                
                <div class="bg-color-primary p-8 rounded-xl shadow-2xl border border-gray-700">
                    <input type="text" id="business-goal" placeholder="e.g., Increase lead volume by 50%" class="w-full p-4 mb-4 bg-gray-800 border border-gray-700 rounded-lg text-lg text-gray-200 placeholder-gray-500 focus:ring-orange-500 focus:border-orange-500">
                    <button id="audit-button" onclick="generateAuditInsight()" class="glow-button w-full px-8 py-4 text-lg font-bold rounded-xl text-white bg-orange-600 hover:bg-orange-700 transition duration-300">
                        Generate Actionable Insight ✨
                    </button>
                </div>
            </div>
        </section>

        <!-- 6. Final CTA Section --><section id="cta" class="py-24 sm:py-32 bg-orange-600">
            <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 text-center fade-in">
                <h2 class="text-4xl sm:text-5xl font-extrabold text-white mb-6">
                    Ready to Scale Smarter?
                </h2>
                <p class="text-xl text-orange-100 mb-10">
                    Stop trading time for growth. Claim your complimentary, no-obligation AI Automation Audit today and map out your next generation of business systems.
                </p>
                
                <!-- Mock Form/Booking Link --><div class="bg-white p-8 rounded-xl shadow-2xl max-w-lg mx-auto">
                    <p class="text-lg font-semibold text-gray-800 mb-4">Get Your Free AI Automation Audit</p>
                    <input type="email" placeholder="Your Work Email" class="w-full p-3 mb-4 border border-gray-300 rounded-lg focus:ring-orange-500 focus:border-orange-500 text-gray-800">
                    <a href="#" class="w-full inline-block px-8 py-3 text-lg font-bold rounded-xl text-white bg-gray-900 hover:bg-gray-800 transition duration-300">
                        Map My Automation Strategy
                    </a>
                </div>
            </div>
        </section>

    </main>

    <!-- Footer --><footer class="py-12 border-t border-gray-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center sm:text-left">
            <div class="grid grid-cols-1 sm:grid-cols-4 gap-8">
                <!-- Logo & Mission --><div class="sm:col-span-2">
                    <img src="uploaded:3.png" alt="Envy Digital Logo" class="h-6 w-auto mb-4 mx-auto sm:mx-0">
                    <p class="text-sm text-gray-500 max-w-xs mx-auto sm:mx-0">
                        Building self-sustaining, AI-driven systems that automate business operations and marketing for exponential, scalable growth.
                    </p>
                </div>

                <!-- Quick Links --><div>
                    <h4 class="font-semibold text-white mb-3">Links</h4>
                    <ul class="space-y-2 text-sm text-gray-400">
                        <li><a href="#flywheel" class="hover:text-orange-500">How It Works</a></li>
                        <li><a href="#benefits" class="hover:text-orange-500">Benefits</a></li>
                        <li><a href="#proof" class="hover:text-orange-500">Case Studies</a></li>
                        <li><a href="#services" class="hover:text-orange-500">Services</a></li>
                    </ul>
                </div>

                <!-- Contact --><div>
                    <h4 class="font-semibold text-white mb-3">Connect</h4>
                    <ul class="space-y-2 text-sm text-gray-400">
                        <li><a href="#" class="hover:text-orange-500">jonah@envydigital.agency</a></li>
                        <li>0435 78 06 08</li>
                        <li><a href="#cta" class="hover:text-orange-500">Book a Call</a></li>
                    </ul>
                </div>
            </div>

            <div class="mt-12 text-center border-t border-gray-800 pt-8">
                <p class="text-xs text-gray-600">&copy; 2025 Envy Digital. All rights reserved. | Systems built for the future.</p>
            </div>
        </div>
    </footer>

    <script>
        // --- GEMINI API SETUP ---
        const API_KEY = ""; // Provided by environment
        const API_URL = "https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-09-2025:generateContent?key=" + API_KEY;
        const RETRY_LIMIT = 3;

        /**
         * Executes fetch request with exponential backoff for resilience.
         * @param {string} url - The API endpoint URL.
         * @param {object} options - Fetch options (method, headers, body).
         * @returns {Promise<Response>}
         */
        async function exponentialBackoffFetch(url, options) {
            for (let attempt = 0; attempt < RETRY_LIMIT; attempt++) {
                try {
                    const response = await fetch(url, options);
                    if (response.ok) {
                        return response;
                    } else if (response.status === 429 && attempt < RETRY_LIMIT - 1) {
                        const delay = Math.pow(2, attempt) * 1000;
                        await new Promise(resolve => setTimeout(resolve, delay));
                        // Continue to next attempt
                    } else {
                        // Throw non-retryable errors
                        const errorBody = await response.json();
                        throw new Error(`API Error ${response.status}: ${errorBody.error.message}`);
                    }
                } catch (error) {
                    if (attempt === RETRY_LIMIT - 1) {
                        throw error; // Throw after final attempt
                    }
                    // Continue to next attempt
                }
            }
        }

        /**
         * Generic function to call the Gemini API.
         * @param {string} userQuery - The user's prompt.
         * @param {string} systemPrompt - The instruction for the model.
         * @param {boolean} useGrounding - Whether to enable Google Search grounding.
         * @returns {Promise<{text: string, sources: Array<{uri: string, title: string}>}>}
         */
        async function generateContent(userQuery, systemPrompt, useGrounding) {
            const payload = {
                contents: [{ parts: [{ text: userQuery }] }],
                systemInstruction: { parts: [{ text: systemPrompt }] },
            };

            if (useGrounding) {
                payload.tools = [{ "google_search": {} }];
            }

            const options = {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify(payload)
            };

            const response = await exponentialBackoffFetch(API_URL, options);
            const result = await response.json();
            const candidate = result.candidates?.[0];

            if (candidate && candidate.content?.parts?.[0]?.text) {
                const text = candidate.content.parts[0].text;
                let sources = [];
                const groundingMetadata = candidate.groundingMetadata;
                
                if (groundingMetadata && groundingMetadata.groundingAttributions) {
                    sources = groundingMetadata.groundingAttributions
                        .map(attribution => ({
                            uri: attribution.web?.uri,
                            title: attribution.web?.title,
                        }))
                        .filter(source => source.uri && source.title);
                }

                return { text, sources };

            } else {
                throw new Error("Failed to generate content or received an empty response.");
            }
        }
        
        // --- CUSTOM MESSAGE BOX FUNCTIONS ---
        function showCustomMessageBox(content, title = "AI Result", sources = []) {
            document.getElementById('message-title').textContent = title;
            
            let htmlContent = content.replace(/\n/g, '<br>');
            
            if (sources.length > 0) {
                htmlContent += '<br><br><span class="font-semibold text-orange-400">Sources:</span>';
                sources.forEach(src => {
                    htmlContent += `<br>• <a href="${src.uri}" target="_blank" class="text-cyan-400 hover:text-cyan-300 underline">${src.title}</a>`;
                });
            }

            document.getElementById('message-content').innerHTML = htmlContent;
            document.getElementById('custom-message-overlay').style.display = 'block';
            document.getElementById('custom-message-box').style.display = 'block';
        }

        function closeCustomMessageBox() {
            document.getElementById('custom-message-overlay').style.display = 'none';
            document.getElementById('custom-message-box').style.display = 'none';
        }

        function showLoading(buttonId, isLoading) {
            const button = document.getElementById(buttonId);
            if (isLoading) {
                button.disabled = true;
                button.originalText = button.innerHTML;
                button.innerHTML = '<span class="spinner"></span> Generating...';
            } else {
                button.disabled = false;
                button.innerHTML = button.originalText;
            }
        }

        // --- FEATURE 1: AI Headline Generator ---
        async function generateHeadline() {
            const buttonId = 'headline-button'; 
            const descriptionInput = document.getElementById('business-description');
            const userQuery = descriptionInput.value.trim();

            if (!userQuery) {
                showCustomMessageBox("Please describe your business first to get tailored headlines.", "Input Required");
                return;
            }
            
            showLoading(buttonId, true);

            const systemPrompt = `You are a highly creative marketing AI working for Envy Digital. Generate three extremely bold, high-converting, and confident headlines for a digital agency specializing in AI automation based on the user's business description. Each headline must be under 12 words and separated by a newline. Do not include any introductory or concluding text, just the three headlines.`;
            
            try {
                const { text } = await generateContent(`My business is a: ${userQuery}`, systemPrompt, false);

                let resultText = "Here are 3 AI-Optimized Headline Suggestions:\n\n" + text;
                showCustomMessageBox(resultText, "AI Headline Suggestions");
                
            } catch (error) {
                console.error("Headline generation failed:", error);
                showCustomMessageBox("Sorry, the AI service encountered an error. Please try again.", "Error");
            } finally {
                showLoading(buttonId, false);
            }
        }

        // --- FEATURE 2: AI Audit Insight Generator (Grounded) ---
        async function generateAuditInsight() {
            const buttonId = 'audit-button'; 
            
            const goalInput = document.getElementById('business-goal');
            const goal = goalInput.value.trim();

            if (!goal) {
                showCustomMessageBox("Please enter your primary business goal to receive a relevant AI strategy insight.", "Input Required");
                return;
            }

            showLoading(buttonId, true);

            const systemPrompt = `You are a senior AI Automation strategist for Envy Digital. Based on the business goal provided by the user, provide a concise, single-paragraph insight (under 6 sentences) suggesting one cutting-edge, high-impact AI automation strategy. The suggestion must be actionable, focused on the goal's outcome (scaling, efficiency, lead gen, etc.), and reference current industry trends.`;
            const userQuery = `My primary business goal is to: ${goal}`;
            
            try {
                const { text, sources } = await generateContent(userQuery, systemPrompt, true);

                let resultText = `<span class="font-semibold text-xl text-cyan-400">Strategy Insight for: ${goal}</span>\n\n` + text;
                showCustomMessageBox(resultText, "AI Automation Strategy", sources);
                
            } catch (error) {
                console.error("Audit insight generation failed:", error);
                showCustomMessageBox("Sorry, the AI service encountered an error while generating the insight. Please try again.", "Error");
            } finally {
                showLoading(buttonId, false);
            }
        }

        // JavaScript for Scroll-Based Fade-In Animations
        document.addEventListener('DOMContentLoaded', () => {
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('is-visible');
                        observer.unobserve(entry.target); // Stop observing once visible
                    }
                });
            }, {
                threshold: 0.1 // Trigger when 10% of the element is visible
            });

            // Apply observer to all elements with the 'fade-in' class
            document.querySelectorAll('.fade-in').forEach(element => {
                observer.observe(element);
            });
        });
    </script>
</body>
</html>
