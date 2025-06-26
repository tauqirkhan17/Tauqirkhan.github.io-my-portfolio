<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tauqir Khan | Digital Strategist</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&family=Lato:wght@400;700&display=swap" rel="stylesheet">
    <!-- Chosen Palette: Midnight Blue & Gold -->
    <!-- Application Structure Plan: A highly dynamic, single-page portfolio designed for an immersive user journey. The structure uses full-viewport sections and on-scroll reveal animations to guide the user through a narrative: from an impactful animated hero, to a detailed interactive timeline of experience, a visually engaging skills showcase, high-impact achievements with a custom chart, and finally, education and contact details. This non-linear, story-driven structure is chosen to create a memorable and impressive experience that stands out from standard resumes. -->
    <!-- Visualization & Content Choices: 
    - Report Info: Key Achievements (Follower Growth, Traffic Growth, Backlinks, Speaker Awards). Goal: Impress & Inform. Viz/Presentation: 'Glassmorphism' cards with large typography and icons + an interactive bar chart. Interaction: Hover effects on cards, tooltips on the chart. Justification: This combination provides both at-a-glance impact and detailed, explorable data, making achievements feel more significant. Library: Chart.js for the chart, HTML/CSS for cards.
    - Report Info: Experience Section (including new 'Rubi' startup). Goal: Organize & Detail. Viz/Presentation: Animated vertical timeline with alternating content cards. Interaction: 3D tilt effect on hover for cards, on-scroll reveal animations. Justification: The timeline format clearly shows career progression, while the advanced animations and interactivity make exploring the details feel engaging and modern. Method: HTML/CSS/JS.
    - Report Info: Skills. Goal: Organize. Viz/Presentation: Grouped cards with a subtle glow-on-hover effect. Interaction: Hover animations. Justification: Cleanly categorizes skills for readability while maintaining the high-end aesthetic of the site through micro-interactions. Method: HTML/CSS.
    - Report Info: Summary/Hero. Goal: Engage & Introduce. Viz/Presentation: Full-screen hero with a typewriter text animation. Interaction: Animated text reveal. Justification: Creates a strong, memorable first impression and immediately establishes a professional, tech-savvy tone. Method: HTML/CSS/JS. -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Lato', sans-serif;
            background-color: #0a192f;
            color: #ccd6f6;
        }
        h1, h2, h3, h4, h5, h6 {
            font-family: 'Poppins', sans-serif;
            color: #e6f1ff;
        }
        .font-poppins { font-family: 'Poppins', sans-serif; }
        .font-lato { font-family: 'Lato', sans-serif; }
        .glass-card {
            background: rgba(23, 44, 78, 0.4);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            border: 1px solid rgba(42, 143, 222, 0.2);
        }
        .text-accent { color: #f59e0b; }
        .bg-accent { background-color: #f59e0b; }
        .border-accent { border-color: #f59e0b; }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 900px;
            margin-left: auto;
            margin-right: auto;
            height: 400px;
            max-height: 50vh;
        }
        .timeline-card {
            transform-style: preserve-3d;
            transition: transform 0.5s;
        }
        .timeline-card:hover {
            transform: perspective(1000px) rotateY(5deg) rotateX(10deg) scale3d(1.05, 1.05, 1.05);
        }
        .reveal {
            opacity: 0;
            transform: translateY(50px);
            transition: opacity 0.6s ease-out, transform 0.6s ease-out;
        }
        .reveal.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body class="antialiased">

    <header id="navbar" class="bg-slate-900/50 backdrop-blur-md sticky top-0 z-50 transition-all duration-300">
        <div class="container mx-auto px-6 py-4 flex justify-between items-center">
            <h1 class="text-xl md:text-2xl font-bold text-accent">TK</h1>
            <nav class="hidden md:flex items-center space-x-6">
                <a href="#experience" class="text-slate-300 hover:text-accent transition-colors duration-300">Experience</a>
                <a href="#skills" class="text-slate-300 hover:text-accent transition-colors duration-300">Skills</a>
                <a href="#achievements" class="text-slate-300 hover:text-accent transition-colors duration-300">Achievements</a>
                <a href="#contact" class="border border-accent text-accent px-4 py-2 rounded-md hover:bg-accent/10 transition-colors duration-300">Contact</a>
            </nav>
                        <div class="md:hidden">

                            

                <a href="#contact" class="bg-accent text-slate-900 px-4 py-2 rounded-md font-semibold">Contact</a>
            </div>
        </div>
    </header>

    <main class="container mx-auto px-6">
        
        <section id="home" class="min-h-screen flex flex-col justify-center items-start">
            <div class="max-w-4xl">
                <p class="text-accent text-lg font-lato mb-4">Hi, my name is</p>
                <h2 class="text-4xl sm:text-6xl md:text-7xl font-bold text-slate-100">Tauqir Khan.</h2>
                <h3 id="typewriter-text" class="text-3xl sm:text-5xl md:text-6xl font-bold text-slate-400 mt-2 h-20"></h3>
                <p class="text-lg text-slate-400 mt-6 max-w-2xl">
                    
                    I am a creative and results-driven B.Tech Computer Science student with a passion for building and scaling digital brands. From SEO-driven content to managing high-growth social media campaigns, I thrive on turning creative strategies into measurable results.
                </p>
                <!-- Resume Section -->

                <a href="Tauqir_khan_Resume.pdf" class="inline-block mt-8 bg-accent text-slate-900 font-bold px-8 py-4 rounded-md hover:bg-amber-400 transition-colors shadow-lg shadow-amber-500/20">Download CV</a>
            </div>
        </section>
        


        <section id="experience" class="py-24">
            <h3 class="text-3xl font-bold text-center mb-16 reveal">Professional Experience</h3>
            <div class="relative max-w-3xl mx-auto">
                <div class="absolute left-1/2 -translate-x-1/2 h-full w-0.5 bg-slate-700"></div>
                
                <div class="relative mb-12 reveal">
                    <div class="absolute left-1/2 -translate-x-1/2 mt-2 w-5 h-5 bg-accent rounded-full border-4 border-slate-800"></div>
                    <div class="md:w-[calc(50%-2rem)] md:mr-auto text-left md:text-right">
                        <div class="glass-card p-6 rounded-lg timeline-card">
                            <p class="text-sm text-accent mb-1">Nov 2024 - Apr 2025</p>
                            <h4 class="font-bold text-xl text-slate-100">Social Media Manager</h4>
                            <p class="text-slate-400 font-semibold mb-2">Skybizz Aviation, Pune</p>
                            <p class="text-slate-300 text-left">Managed multi-platform content strategy, boosting follower count by 30% in three month and designing over 50+ posts with 90%+ positive feedback.</p>
                        </div>
                    </div>
                </div>

                <div class="relative mb-12 reveal">
                    <div class="absolute left-1/2 -translate-x-1/2 mt-2 w-5 h-5 bg-accent rounded-full border-4 border-slate-800"></div>
                    <div class="md:w-[calc(50%-2rem)] md:ml-auto">
                        <div class="glass-card p-6 rounded-lg timeline-card">
                           <p class="text-sm text-accent mb-1">Oct 2024 - Nov 2024</p>
                           <h4 class="font-bold text-xl text-slate-100">Digital Marketing Associate</h4>
                           <p class="text-slate-400 font-semibold mb-2">Globussoft, Bhilai</p>
                           <p class="text-slate-300">Executed high-impact SEO strategies, building 200+ quality backlinks and creating optimized content that doubled organic traffic within a month.</p>
                        </div>
                    </div>
                </div>

            </div>
        </section>

        <section id="skills" class="py-12 md:py-20 lg:py-24">
            <h3 class="text-3xl font-bold text-center mb-16 reveal">Core Competencies</h3>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-6 max-w-6xl mx-auto">
                <div class="reveal glass-card p-6 rounded-lg text-center transition-all duration-300 hover:border-accent hover:-translate-y-2">
                    <h4 class="font-bold text-xl mb-3 text-accent">Digital Marketing</h4>
                    <ul class="space-y-2 text-slate-300">
                        <li>SEO Optimization</li>
                        <li>Social Media Marketing</li>
                        <li>Content Marketing</li>
                        <li>Link Building</li>
                    </ul>
                </div>
                <div class="reveal glass-card p-6 rounded-lg text-center transition-all duration-300 hover:border-accent hover:-translate-y-2" style="transition-delay: 100ms;">
                    <h4 class="font-bold text-xl mb-3 text-accent">Content & Design</h4>
                    <ul class="space-y-2 text-slate-300">
                        <li>Content Writing</li>
                        <li>Content Creation</li>
                        <li>Brand Storytelling</li>
                        <li>Graphic Designing</li>
                    </ul>
                </div>
                <div class="reveal glass-card p-6 rounded-lg text-center transition-all duration-300 hover:border-accent hover:-translate-y-2" style="transition-delay: 200ms;">
                    <h4 class="font-bold text-xl mb-3 text-accent">Professional Skill</h4>
                    <ul class="space-y-2 text-slate-300">
                        <li>Public Speaking</li>
                        <li>Leadership & Teamwork</li>
                        <li>Communication</li>
                    </ul>
                </div>
            </div>
        </section>
        
        <section id="achievements" class="py-24">
            <h3 class="text-3xl font-bold text-center mb-16 reveal">Impact & Achievements</h3>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-5 gap-6 max-w-7xl mx-auto mb-16">
                <div class="reveal glass-card p-6 rounded-lg text-center transition-transform hover:scale-105 lg:col-span-2">
                    <p class="text-6xl font-bold text-accent mb-2">25%</p>
                    <p class="font-semibold text-slate-200">Organic Traffic Boost</p>
                    <p class="text-sm text-slate-400">SEO & Content Optimization</p>
                </div>
                 <div class="reveal glass-card p-6 rounded-lg text-center transition-transform hover:scale-105 lg:col-span-2">
                    <p class="text-6xl font-bold text-accent mb-2">50+</p>
                    <p class="font-semibold text-slate-200">Content Pieces Designed</p>
                    <p class="text-sm text-slate-400">With 90%+ Positive Feedback</p>
                </div>

                <div class="reveal glass-card p-6 rounded-lg text-center transition-transform hover:scale-105 lg:col-span-2">
                    <p class="text-6xl font-bold text-accent mb-2">200+</p>
                    <p class="font-semibold text-slate-200">High-Quality Backlinks</p>
                    <p class="text-sm text-slate-400">Achieved in 4 Weeks</p>
                </div>
                <div class="reveal glass-card p-6 rounded-lg text-center transition-transform hover:scale-105 lg:col-span-3">
                    <p class="text-6xl font-bold text-accent mb-2">30%</p>
                    <p class="font-semibold text-slate-200">Social Follower Growth</p>
                    <p class="text-sm text-slate-400">Across all major platforms</p>
                </div>
            </div>
        
            <div class="reveal glass-card p-4 md:p-8 rounded-xl">
                <h3 class="text-2xl font-bold text-slate-200 text-center mb-4">Key Performance Metrics</h3>
                <div class="chart-container">
                    <canvas id="achievementsChart"></canvas>
                </div>
            </div>
        </section>

        <section id="education" class="py-24">
             <h3 class="text-3xl font-bold text-center mb-16 reveal">Education & Certifications</h3>
            <div class="grid grid-cols-1 md:grid-cols-5 gap-8 max-w-6xl mx-auto">
                <div class="reveal md:col-span-2 glass-card p-6 rounded-lg">
                    <h4 class="font-bold text-xl text-slate-100 mb-4">Education</h4>
                    <div class="border-l-4 border-accent pl-4 mb-6">
                        <p class="font-bold text-slate-200">B.Tech in Computer Science (AI & ML)</p>
                        <p class="text-slate-400">RCET, Bhilai, Chhattisgarh</p>
                        <p class="text-sm text-slate-500">2022 - 2026</p>
                    </div>
                    <div class="border-l-4 border-accent pl-4">
                        <p class="font-bold text-slate-200">Higher Secondary School Certificate</p>
                        <p class="text-slate-400">Patna Muslim High School, Patna, Bihar</p>
                        <p class="text-sm text-slate-500">2022</p>
                    </div>
                </div>
                <div class="reveal md:col-span-3 glass-card p-6 rounded-lg">
                    <h4 class="font-bold text-xl text-slate-100 mb-4">Certifications</h4>
                     <ul class="space-y-3 text-slate-300 columns-1 sm:columns-2">
                        <li class="flex items-start"><span class="text-accent mr-3 mt-1">&#10003;</span><span><span class="font-semibold text-slate-200">Udemy</span> - SEO: Link Building & Content Writing</span></li>
                        <li class="flex items-start"><span class="text-accent mr-3 mt-1">&#10003;</span><span><span class="font-semibold text-slate-200">Hubspot Academy</span> - Content Marketing </span></li>
                        <li class="flex items-start"><span class="text-accent mr-3 mt-1">&#10003;</span><span><span class="font-semibold text-slate-200">Google</span> - Fundamental of Digital Marketing </span></li>
                        <li class="flex items-start"><span class="text-accent mr-3 mt-1">&#10003;</span><span><span class="font-semibold text-slate-200">E-marketing Institute </span> - SEO</span></li>
                    </ul>
                </div>
            </div>
        </section>
    
        

<!-- Contact Section -->
<section id="contact" class="text-center py-12 md:py16">
    
            <h3 class="text-3xl font-bold text-slate-100 mb-2 reveal">Let's Connect</h3>
            <p class="text-lg text-slate-400 mb-8 max-w-xl mx-auto reveal">Whether you're hiring, collaborating, or just want to network — I'm just a message away.</p>
            
            <div class="flex flex-col md:flex-row justify-center items-center gap-6 mt-8 reveal">
                  <!-- LinkedIn -->
                    <a href="https://www.linkedin.com/in/tauqir-khan-79813a251/" target="_blank" class="flex items-center gap-2 text-accent hover:underline text-lg">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-accent" fill="currentColor" viewBox="0 0 24 24"><path d="M4.98 3.5C4.98 4.88 3.88 6 2.5 6S0 4.88 0 3.5 1.12 1 2.5 1s2.48 1.12 2.48 2.5zM.4 8h4.2v12H.4V8zm7.6 0h4v1.7h.1c.6-1.1 2-2.2 4-2.2 4.3 0 5.1 2.8 5.1 6.3v7.1h-4.2v-6.3c0-1.5 0-3.5-2.1-3.5s-2.5 1.6-2.5 3.4v6.4H8V8z"/></svg>
                            LinkedIn
                              </a>

                                <!-- Email -->
                                  <a href="mailto:tauqirkhan281@gmail.com" class="flex items-center gap-2 text-accent hover:underline text-lg">
                                      <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-accent" viewBox="0 0 24 24" fill="currentColor"><path d="M2 4a2 2 0 012-2h16a2 2 0 012 2v1l-10 6L2 5V4zm0 2.2l8.4 5.1c.5.3 1.2.3 1.6 0L22 6.2V20a2 2 0 01-2 2H4a2 2 0 01-2-2V6.2z"/></svg>
                                          tauqirkhan281@gmail.com
                                            </a>

                                              <!-- Phone -->
                                                <a href="tel:+918544634850" class="flex items-center gap-2 text-accent hover:underline text-lg">
                                                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-accent" viewBox="0 0 24 24" fill="currentColor"><path d="M3 2a1 1 0 011-1h3a1 1 0 011 1v3a1 1 0 01-.29.71l-1.25 1.25a16 16 0 007.59 7.59l1.25-1.25A1 1 0 0116 13h3a1 1 0 011 1v3a1 1 0 01-1 1h-.5C10.49 18 6 13.51 6 7.5V7a1 1 0 011-1h3a1 1 0 011 1v.5a1 1 0 01-.29.71L8.91 10.91A18.35 18.35 0 003.29 5.29 1 1 0 013 4V2z"/></svg>
                                                        +91 8544634850
                                                          </a>
                                                          </div>
        </section>
    
    </main>
                                        
                                    
                                        
                                        
                                                                          
                                                                                  
                                                                                    
                                                                                            

                                                                                        
                                                                                
                                                                                        
                                                                                                
                                                                                                                            
                                                                                                                    
                                        <footer class="text-center pb-8">
        <p class="text-slate-500 text-sm">Designed & Built by Tauqir Khan.</p>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            // Typewriter Effect
            const typewriterElement = document.getElementById('typewriter-text');
            const texts = ["I write content that connects.", "I drive growth with SEO.", "I craft engaging content."];
            let textIndex = 0;
            let charIndex = 0;
            let isDeleting = false;

            function typeWriter() {
                const currentText = texts[textIndex];
                if (isDeleting) {
                    typewriterElement.textContent = currentText.substring(0, charIndex - 1);
                    charIndex--;
                } else {
                    typewriterElement.textContent = currentText.substring(0, charIndex + 1);
                 
