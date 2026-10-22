Assignment 6.4 — Positioning Practice

1. Project structure
Create a folder named Assignment-6.4 containing these files:


text
Assignment-6.4/
├── index.html
└── style.css
2. HTML code — index.html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Assignment 6.4 - Positioning Practice</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <!-- Page Header -->
    <header class="hero" id="home">
        <h1>CSS Positioning Practice</h1>
        <p>Learn sticky navigation, fixed buttons, and positioned badges.</p>
        <a href="#about" class="hero-button">Explore More</a>
    </header>

    <!-- Sticky Navigation Bar -->
    <nav class="navbar">
        <a href="#home" class="logo">WebLearn</a>
        <div class="nav-links">
            <a href="#home">Home</a>
            <a href="#about">About</a>
            <a href="#services">Services</a>
            <a href="#contact">Contact</a>
        </div>
    </nav>

    <main>
        <!-- About Section -->
        <section class="content-section about" id="about">
            <h2>About Us</h2>
            <p>
                Welcome to WebLearn! This webpage demonstrates how CSS
                positioning controls the placement of elements on a page.
                Scroll through the sections to see the sticky navigation
                bar remain at the top of the viewport.
            </p>
            <p>
                CSS positioning is useful for navigation menus, notifications,
                badges, floating help buttons, and other interface elements.
            </p>
        </section>

        <!-- Services Section -->
        <section class="content-section services" id="services">
            <h2>Our Services</h2>

            <div class="card-container">
                <article class="service-card">
                    <span class="badge">Popular</span>
                    <h3>Web Design</h3>
                    <p>
                        Create attractive, responsive, and user-friendly
                        websites using HTML and CSS.
                    </p>
                    <a href="#contact" class="card-button">Learn More</a>
                </article>

                <article class="service-card">
                    <span class="badge new-badge">New</span>
                    <h3>Web Development</h3>
                    <p>
                        Build functional websites with modern development
                        techniques and responsive layouts.
                    </p>
                    <a href="#contact" class="card-button">Learn More</a>
                </article>

                <article class="service-card">
                    <span class="badge">Featured</span>
                    <h3>UI Design</h3>
                    <p>
                        Design clear interfaces with useful layouts,
                        readable text, and consistent visual styles.
                    </p>
                    <a href="#contact" class="card-button">Learn More</a>
                </article>
            </div>
        </section>

        <!-- Positioning Explanation -->
        <section class="content-section positioning" id="positioning">
            <h2>CSS Positioning Properties</h2>

            <div class="info-card">
                <h3>Position: Sticky</h3>
                <p>
                    The navigation bar sticks to the top of the viewport
                    when scrolling past its original position.
                </p>
            </div>

            <div class="info-card">
                <h3>Position: Fixed</h3>
                <p>
                    The floating help button stays in the same position
                    relative to the browser viewport while scrolling.
                </p>
            </div>

            <div class="info-card">
                <h3>Position: Absolute and Relative</h3>
                <p>
                    Each badge is positioned absolutely inside its card.
                    The card uses position relative as the reference point.
                </p>
            </div>

            <div class="info-card">
                <h3>Z-Index</h3>
                <p>
                    The z-index property controls the stacking order
                    of overlapping positioned elements.
                </p>
            </div>
        </section>

        <!-- Contact Section -->
        <section class="content-section contact" id="contact">
            <h2>Contact Us</h2>
            <p>Have a question? Use the floating help button at the bottom-right.</p>
            <p>Email: hello@example.com</p>
            <a href="#home" class="hero-button">Back to Top</a>
        </section>
    </main>

    <!-- Fixed Floating Help Button -->
    <a class="help-button" href="#contact" aria-label="Get help">
        ? Help
    </a>

    <footer>
        <p>Assignment 6.4 | CSS Positioning Practice</p>
    </footer>

</body>
</html>
3. CSS code — style.css

css

/* General styling */
* {
    box-sizing: border-box;
    scroll-behavior: smooth;
}

body {
    margin: 0;
    font-family: Arial, sans-serif;
    line-height: 1.6;
    color: #1e293b;
    background-color: #f8fafc;
}

/* Hero section */
.hero {
    min-height: 280px;
    padding: 60px 20px;
    text-align: center;
    color: white;
    background: linear-gradient(135deg, #1d4ed8, #7c3aed);
}

.hero h1 {
    margin-top: 0;
    font-size: 36px;
}

.hero-button {
    display: inline-block;
    margin-top: 15px;
    padding: 10px 22px;
    color: white;
    background-color: #2563eb;
    border-radius: 8px;
    text-decoration: none;
}

/* Sticky navigation */
.navbar {
    position: sticky;
    top: 0;
    z-index: 1000;

    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 10px;

    padding: 15px 30px;
    background-color: #0f172a;
    box-shadow: 0 3px 10px rgba(0, 0, 0, 0.15);
}

.logo {
    color: #93c5fd;
    font-size: 22px;
    font-weight: bold;
    text-decoration: none;
}

.nav-links {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}

.nav-links a {
    color: white;
    text-decoration: none;
}

.nav-links a:hover {
    color: #93c5fd;
}

/* Page sections */
.content-section {
    max-width: 1100px;
    min-height: 320px;
    margin: 30px auto;
    padding: 35px 25px;
    border-radius: 12px;
}

.content-section h2 {
    margin-top: 0;
    font-size: 28px;
}

.about {
    background-color: #dbeafe;
}

.services {
    background-color: #f1f5f9;
}

.positioning {
    background-color: #ede9fe;
}

.contact {
    background-color: #dcfce7;
}

/* Service card layout */
.card-container {
    display: flex;
    justify-content: center;
    align-items: stretch;
    flex-wrap: wrap;
    gap: 25px;
}

.service-card {
    /* Reference point for absolute badges */
    position: relative;
    z-index: 1;

    width: 300px;
    max-width: 100%;
    padding: 35px 20px 25px;

    background-color: white;
    border: 2px solid #cbd5e1;
    border-radius: 12px;
    box-shadow: 0 4px 12px rgba(15, 23, 42, 0.08);
}

.service-card h3 {
    color: #1d4ed8;
}

/* Badge positioned relative to its card */
.badge {
    position: absolute;
    top: -12px;
    right: 15px;
    z-index: 2;

    padding: 4px 12px;
    color: white;
    background-color: #dc2626;
    border-radius: 20px;
    font-size: 12px;
    font-weight: bold;
}

.new-badge {
    background-color: #16a34a;
}

.card-button {
    display: inline-block;
    padding: 8px 15px;
    color: white;
    background-color: #2563eb;
    border-radius: 6px;
    text-decoration: none;
}

/* Positioning information cards */
.info-card {
    margin: 15px 0;
    padding: 15px 20px;
    background-color: white;
    border-left: 5px solid #7c3aed;
    border-radius: 8px;
}

/* Fixed floating help button */
.help-button {
    position: fixed;
    right: 25px;
    bottom: 25px;
    z-index: 2000;

    padding: 14px 22px;
    color: white;
    background-color: #ea580c;
    border: 2px solid white;
    border-radius: 30px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.25);
    text-decoration: none;
    font-weight: bold;
}

.help-button:hover {
    background-color: #c2410c;
}

/* Footer */
footer {
    padding: 20px;
    text-align: center;
    color: white;
    background-color: #0f172a;
}

/* Responsive design */
@media (max-width: 600px) {
    .hero h1 {
        font-size: 27px;
    }

    .navbar {
        justify-content: center;
        padding: 12px;
    }

    .nav-links {
        justify-content: center;
        gap: 12px;
    }

    .content-section {
        margin: 15px 10px;
        padding: 25px 15px;
    }

    .card-container {
        flex-direction: column;
        align-items: center;
    }

    .service-card {
        width: 100%;
        max-width: 350px;
    }

    .help-button {
        right: 15px;
        bottom: 15px;
    }
}
4. Expected output
The webpage will include a gradient header, a dark sticky navigation bar, three service cards with badges, multiple scrollable sections, and an orange floating help button.

CSS Positioning Practice
Learn sticky navigation, fixed buttons, and positioned badges.

WebLearn
Home

About

Services

Sticky navbar — remains at the top while scrolling.
Our Services
Popular

Web Design
Create attractive, responsive websites.

Learn More

New

Web Development
Build functional, responsive websites.

Learn More

UI Design
Design clear and consistent user interfaces.

The badge is positioned relative to its parent card.

CSS Positioning Properties
Sticky: Navigation stays at the top.

Fixed: Help button stays at the viewport corner.

Absolute + Relative: Badges stay anchored to their cards.

Z-index: Controls which elements appear on top.

? Help

Illustrative design preview. The actual sticky behavior and floating button can be tested by scrolling the webpage in your browser.
5. Explanation of CSS positioning
Property

Purpose in this assignment

position: sticky

Keeps the navigation bar at the top while scrolling.

position: fixed

Keeps the help button in the bottom-right corner of the viewport.

position: relative

Establishes the reference point for each card's badge.

position: absolute

Places the badge at the top-right of its card.

z-index

Controls the stacking order of overlapping elements.

How the badge works
The parent card has position: relative, while the badge has position: absolute. This makes top: -12px and right: 15px position the badge relative to its card rather than the entire webpage.

The navigation uses z-index: 1000, and the help button uses z-index: 2000, so the help button appears above other positioned elements when they overlap.

6. How to run the assignment
Save the HTML code in index.html.

Save the CSS code in style.css in the same folder.

Open index.html in Chrome.

Scroll down the page to check that the navigation bar sticks to the top.

Verify that the help button stays at the bottom-right and the badges remain attached to their cards.

7. Screenshot and submission
Take a screenshot of the webpage with the sticky navbar, a visible card badge, and the floating help button. You can take an additional screenshot after scrolling to demonstrate the sticky behavior.

Submit these files:

index.html

style.css

positioning-practice.png — screenshot of the working webpage

8. Conclusion
This assignment demonstrates how CSS positioning controls the placement and stacking of webpage elements. The sticky navigation improves navigation while scrolling, the fixed help button remains accessible, and absolute positioning places badges inside relatively positioned cards. The z-index property ensures that overlapping elements appear in the intended order.