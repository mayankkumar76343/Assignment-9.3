Assignment 9.3 — Combine Flexbox and Grid Responsively.Project structure
Create a folder named Assignment-9.3 with these three files:


text
Assignment-9.3/
├── index.html
├── style.css
└── script.js
1. HTML file — index.html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="A modern responsive landing page built with CSS Grid and Flexbox.">
    <title>Assignment 9.3 | Flexbox & Grid</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <!-- Header and Navigation -->
    <header class="header">
        <nav class="navbar container">
            <a href="#" class="logo">Web<span>Space</span></a>

            <button class="menu-toggle" id="menu-toggle"
                    aria-label="Toggle navigation"
                    aria-expanded="false"
                    aria-controls="nav-links">
                ☰
            </button>

            <ul class="nav-links" id="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#features">Features</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact" class="nav-button">Get Started</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <!-- Hero Section -->
        <section class="hero container" id="home">
            <div class="hero-content">
                <p class="eyebrow">WELCOME TO WEBSPACE</p>
                <h1>Build Something <span>Amazing.</span></h1>
                <p class="hero-description">
                    Discover simple, creative and powerful digital solutions
                    designed to help you bring your ideas to life.
                </p>
                <div class="hero-buttons">
                    <a href="#features" class="btn btn-primary">Explore Features</a>
                    <a href="#about" class="btn btn-secondary">Learn More</a>
                </div>
            </div>

            <div class="hero-image">
                <img
                    src="https://images.unsplash.com/photo-1498050108023-c5249f4df085?auto=format&fit=crop&w=1000&q=85"
                    alt="Laptop and workspace for web development">
            </div>
        </section>

        <!-- Features Section -->
        <section class="features-section" id="features">
            <div class="container">
                <div class="section-heading">
                    <p class="eyebrow">WHAT WE OFFER</p>
                    <h2>Features Designed for You</h2>
                    <p>Everything you need to turn your ideas into reality.</p>
                </div>

                <div class="features-grid">
                    <article class="feature-card">
                        <div class="feature-icon">🎨</div>
                        <h3>Creative Design</h3>
                        <p>Enjoy clean, modern designs that look great on every device.</p>
                        <a href="#about">Learn more →</a>
                    </article>

                    <article class="feature-card">
                        <div class="feature-icon">⚡</div>
                        <h3>Fast Performance</h3>
                        <p>Build smooth digital experiences with efficient layouts.</p>
                        <a href="#about">Learn more →</a>
                    </article>

                    <article class="feature-card">
                        <div class="feature-icon">📱</div>
                        <h3>Fully Responsive</h3>
                        <p>Make your website adapt to phones, tablets and desktops.</p>
                        <a href="#about">Learn more →</a>
                    </article>

                    <article class="feature-card">
                        <div class="feature-icon">🔒</div>
                        <h3>Secure Platform</h3>
                        <p>Follow good development practices for reliable websites.</p>
                        <a href="#about">Learn more →</a>
                    </article>

                    <article class="feature-card">
                        <div class="feature-icon">🚀</div>
                        <h3>Easy to Launch</h3>
                        <p>Start building your next project with a simple foundation.</p>
                        <a href="#about">Learn more →</a>
                    </article>

                    <article class="feature-card">
                        <div class="feature-icon">💬</div>
                        <h3>Helpful Support</h3>
                        <p>Keep your workflow organized and your goals in focus.</p>
                        <a href="#about">Learn more →</a>
                    </article>
                </div>
            </div>
        </section>

        <!-- About Section -->
        <section class="about-section container" id="about">
            <div>
                <p class="eyebrow">OUR APPROACH</p>
                <h2>Simple layouts. Better experiences.</h2>
            </div>
            <p>
                This landing page combines CSS Grid for structured page
                layouts and Flexbox for navigation, hero alignment and
                the internal content of feature cards.
            </p>
        </section>

        <!-- Call to Action -->
        <section class="cta-section" id="contact">
            <div class="container cta-content">
                <h2>Ready to create something great?</h2>
                <p>Start exploring the possibilities today.</p>
                <a href="#home" class="btn btn-light">Back to Top ↑</a>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer class="footer">
        <div class="container footer-content">
            <a href="#home" class="logo">Web<span>Space</span></a>
            <p>© 2026 WebSpace. Created for Assignment 9.3.</p>
        </div>
    </footer>

    <script src="script.js"></script>
</body>
</html>
2. CSS file — style.css
This file uses CSS Grid for the feature cards and overall content layout, and Flexbox for navigation, hero alignment, buttons, and card content. Media queries make the page responsive on mobile devices.


css

/* Assignment 9.3: Combine Flexbox and Grid Responsively */

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

:root {
    --primary: #635bff;
    --primary-dark: #4b43df;
    --dark: #172033;
    --text: #667085;
    --light: #f7f8fc;
    --white: #ffffff;
    --border: #e8eaf2;
}

html {
    scroll-behavior: smooth;
    scroll-padding-top: 90px;
}

body {
    font-family: Arial, Helvetica, sans-serif;
    color: var(--dark);
    line-height: 1.6;
    background: var(--white);
}

a {
    text-decoration: none;
}

.container {
    width: min(1120px, 90%);
    margin-inline: auto;
}

/* Header and Navbar: Flexbox */

.header {
    background: var(--white);
    border-bottom: 1px solid var(--border);
    position: sticky;
    top: 0;
    z-index: 10;
}

.navbar {
    min-height: 76px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 24px;
}

.logo {
    font-size: 1.7rem;
    font-weight: 800;
    color: var(--dark);
}

.logo span {
    color: var(--primary);
}

.nav-links {
    display: flex;
    align-items: center;
    gap: 32px;
    list-style: none;
}

.nav-links a {
    color: var(--dark);
    font-size: 0.95rem;
    font-weight: 600;
    transition: color 0.2s ease;
}

.nav-links a:hover {
    color: var(--primary);
}

.nav-links .nav-button {
    color: var(--white);
    background: var(--primary);
    padding: 11px 20px;
    border-radius: 8px;
}

.nav-links .nav-button:hover {
    background: var(--primary-dark);
    color: var(--white);
}

.menu-toggle {
    display: none;
    font-size: 1.7rem;
    border: none;
    background: transparent;
    color: var(--dark);
    cursor: pointer;
}

/* Hero Section: CSS Grid */

.hero {
    display: grid;
    grid-template-columns: 1fr 1fr;
    align-items: center;
    gap: 60px;
    padding-top: 85px;
    padding-bottom: 85px;
}

.hero-content {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 22px;
}

.eyebrow {
    color: var(--primary);
    font-size: 0.8rem;
    font-weight: 800;
    letter-spacing: 2px;
}

.hero h1 {
    font-size: clamp(2.5rem, 5vw, 4rem);
    line-height: 1.12;
    letter-spacing: -2px;
}

.hero h1 span {
    color: var(--primary);
}

.hero-description {
    color: var(--text);
    font-size: 1.05rem;
    max-width: 480px;
}

.hero-buttons {
    display: flex;
    flex-wrap: wrap;
    gap: 14px;
    margin-top: 5px;
}

.btn {
    display: inline-flex;
    justify-content: center;
    align-items: center;
    padding: 13px 22px;
    border-radius: 8px;
    font-weight: 700;
    transition: transform 0.2s ease, background 0.2s ease;
}

.btn:hover {
    transform: translateY(-2px);
}

.btn-primary {
    color: var(--white);
    background: var(--primary);
}

.btn-primary:hover {
    background: var(--primary-dark);
}

.btn-secondary {
    color: var(--dark);
    border: 1px solid var(--border);
    background: var(--white);
}

.hero-image img {
    display: block;
    width: 100%;
    min-height: 300px;
    max-height: 420px;
    object-fit: cover;
    border-radius: 20px;
    box-shadow: 0 20px 50px rgba(23, 32, 51, 0.12);
}

/* Features Section: CSS Grid */

.features-section {
    background: var(--light);
    padding: 85px 0;
}

.section-heading {
    text-align: center;
    max-width: 650px;
    margin: 0 auto 45px;
}

.section-heading h2,
.about-section h2,
.cta-section h2 {
    font-size: clamp(1.8rem, 3.5vw, 2.5rem);
    line-height: 1.2;
    margin: 12px 0;
}

.section-heading > p:last-child {
    color: var(--text);
}

/* Responsive card grid */

.features-grid {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 24px;
}

.feature-card {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 14px;
    padding: 28px;
    background: var(--white);
    border: 1px solid var(--border);
    border-radius: 14px;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.feature-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 15px 35px rgba(23, 32, 51, 0.08);
}

.feature-icon {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 54px;
    height: 54px;
    background: #efedff;
    border-radius: 12px;
    font-size: 1.6rem;
}

.feature-card h3 {
    font-size: 1.2rem;
}

.feature-card p {
    color: var(--text);
    font-size: 0.95rem;
    flex-grow: 1;
}

.feature-card a {
    color: var(--primary);
    font-size: 0.92rem;
    font-weight: 700;
}

/* About Section: Grid */

.about-section {
    display: grid;
    grid-template-columns: 1fr 1fr;
    align-items: center;
    gap: 50px;
    padding-top: 80px;
    padding-bottom: 80px;
}

.about-section > p {
    color: var(--text);
    font-size: 1.05rem;
}

/* Call to Action */

.cta-section {
    padding: 65px 0;
    text-align: center;
    background: var(--primary);
    color: var(--white);
}

.cta-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 12px;
}

.cta-section h2 {
    margin: 0;
}

.cta-section p {
    color: #eeecff;
    margin-bottom: 12px;
}

.btn-light {
    color: var(--primary);
    background: var(--white);
}

.btn-light:hover {
    background: #f0efff;
}

/* Footer: Flexbox */

.footer {
    padding: 25px 0;
    background: var(--white);
}

.footer-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 20px;
}

.footer-content p {
    color: var(--text);
    font-size: 0.88rem;
}

/* Tablet layout */

@media (max-width: 900px) {
    .hero {
        gap: 35px;
        padding-top: 60px;
        padding-bottom: 60px;
    }

    .features-grid {
        grid-template-columns: repeat(2, minmax(0, 1fr));
    }

    .nav-links {
        gap: 20px;
    }

    .about-section {
        gap: 30px;
    }
}

/* Mobile layout */

@media (max-width: 600px) {
    .navbar {
        min-height: 68px;
        flex-wrap: wrap;
        padding-top: 12px;
        padding-bottom: 12px;
    }

    .menu-toggle {
        display: block;
    }

    .nav-links {
        display: none;
        flex-direction: column;
        align-items: stretch;
        width: 100%;
        gap: 0;
        padding: 8px 0;
    }

    .nav-links.active {
        display: flex;
    }

    .nav-links li a {
        display: block;
        padding: 12px 8px;
    }

    .nav-links .nav-button {
        text-align: center;
        margin-top: 5px;
    }

    .hero {
        grid-template-columns: 1fr;
        gap: 35px;
        padding-top: 48px;
        padding-bottom: 55px;
    }

    .hero h1 {
        font-size: 2.65rem;
        letter-spacing: -1px;
    }

    .hero-image img {
        min-height: 220px;
        max-height: 300px;
    }

    .hero-buttons {
        width: 100%;
    }

    .btn {
        padding: 12px 16px;
    }

    .features-section {
        padding: 60px 0;
    }

    .section-heading {
        margin-bottom: 30px;
    }

    .features-grid {
        grid-template-columns: 1fr;
        gap: 18px;
    }

    .feature-card {
        padding: 24px;
    }

    .about-section {
        grid-template-columns: 1fr;
        gap: 18px;
        padding-top: 55px;
        padding-bottom: 55px;
    }

    .cta-section {
        padding: 50px 0;
    }

    .footer-content {
        flex-direction: column;
        text-align: center;
        gap: 8px;
    }
}

/* Accessibility: reduced motion preference */

@media (prefers-reduced-motion: reduce) {
    html {
        scroll-behavior: auto;
    }

    *,
    *::before,
    *::after {
        transition-duration: 0.01ms !important;
        animation-duration: 0.01ms !important;
    }
}
3. JavaScript file — script.js
This file makes the mobile navigation menu open and close when the hamburger button is clicked.


javascript

const menuToggle = document.getElementById("menu-toggle");
const navLinks = document.getElementById("nav-links");

menuToggle.addEventListener("click", () => {
    const isOpen = navLinks.classList.toggle("active");

    menuToggle.setAttribute("aria-expanded", String(isOpen));
    menuToggle.setAttribute("aria-label",
        isOpen ? "Close navigation" : "Toggle navigation"
    );

    menuToggle.textContent = isOpen ? "✕" : "☰";
});

// Close the mobile menu after selecting a navigation link.
navLinks.querySelectorAll("a").forEach((link) => {
    link.addEventListener("click", () => {
        navLinks.classList.remove("active");
        menuToggle.setAttribute("aria-expanded", "false");
        menuToggle.setAttribute("aria-label", "Toggle navigation");
        menuToggle.textContent = "☰";
    });
});
4. Expected output
Hjemmeside på abonnement (2026) – Guide & Pris
 
Desktop view
Horizontal navigation, two-column hero section, and a three-column feature card grid.

Smartphone screen landing page. Mobile phone frame, smartphones application presentation template and black smartphone realistic 3D vector illustration. Mobile software, app programming website design
 
Mobile view
Hamburger navigation, stacked hero content, and single-column feature cards.

These images are visual references for the intended design, not screenshots of your running code.

5. Assignment requirements checklist
Requirement

Implementation

Header and navigation

Sticky header with responsive menu

Hero section with text and image

CSS Grid

3–6 feature cards

Six cards

Grid for main layout

Hero, feature cards, and about section

Flexbox

Navbar, hero content, buttons, and cards

Mobile single-column layout

Media query at 600px

Desktop and mobile spacing

Responsive gaps, padding, and typography

HTML/CSS files

index.html and style.css

Additional functionality

script.js for mobile navigation

6. How to run and submit
Create the three files in the same folder.

Copy each code block into its matching file.

Open index.html in your browser, or run it using the VS Code Live Server extension.

Check the desktop layout at full width.

Open Chrome DevTools with F12, enable the device toolbar, and test a mobile screen such as 390 × 844.

Take screenshots of both desktop and mobile views.

Submit the project folder containing the HTML, CSS, JavaScript, and screenshots.

Note: The hero image uses an online Unsplash URL, so an internet connection is needed to display it.