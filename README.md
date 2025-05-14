# CSS Layouts and Responsive Design

## Objectives

Implement Flexbox and Grid for layout design.
Make the webpage responsive using media queries.
Ensure proper alignment and spacing.

## Instructions

- use Flexbox or CSS Grid.
- Add a navigation bar and structure the content.
- Use media queries to adjust layout for mobile, tablet, and desktop.

>[!NOTE]
>  - Include at least:
>  - navigation bar
>  - media queries

# Tasks

- Apply Flexbox or Grid for layout.
- Make the page responsive.
- Test across different screen sizes.

Happy Coding! 💻✨


SOLUTION
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Layout Example</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <header class="header">
            <h1>Responsive Design</h1>
            <p>Flexbox & Grid Layout</p>
        </header>
        
        <nav class="navbar">
            <ul class="nav-menu">
                <li class="nav-item"><a href="#">Home</a></li>
                <li class="nav-item"><a href="#">About</a></li>
                <li class="nav-item"><a href="#">Services</a></li>
                <li class="nav-item"><a href="#">Portfolio</a></li>
                <li class="nav-item"><a href="#">Contact</a></li>
            </ul>
            <div class="hamburger">
                <span class="bar"></span>
                <span class="bar"></span>
                <span class="bar"></span>
            </div>
        </nav>
        
        <main class="main-content">
            <section class="hero">
                <h2>Welcome to Our Site</h2>
                <p>This layout adapts to different screen sizes using media queries</p>
            </section>
            
            <section class="features">
                <article class="feature-card">
                    <h3>Mobile First</h3>
                    <p>Designed with mobile devices in mind first, then scaled up.</p>
                </article>
                <article class="feature-card">
                    <h3>Flexbox</h3>
                    <p>Flexible boxes for responsive interface components.</p>
                </article>
                <article class="feature-card">
                    <h3>CSS Grid</h3>
                    <p>Two-dimensional layout system for the main content.</p>
                </article>
            </section>
            
            <section class="gallery">
                <h2>Our Work</h2>
                <div class="grid-container">
                    <div class="grid-item item1">Project 1</div>
                    <div class="grid-item item2">Project 2</div>
                    <div class="grid-item item3">Project 3</div>
                    <div class="grid-item item4">Project 4</div>
                    <div class="grid-item item5">Project 5</div>
                    <div class="grid-item item6">Project 6</div>
                </div>
            </section>
        </main>
        
        <aside class="sidebar">
            <h3>Latest News</h3>
            <ul class="news-list">
                <li>New responsive design workshop</li>
                <li>CSS Grid updates</li>
                <li>Flexbox best practices</li>
            </ul>
        </aside>
        
        <footer class="footer">
            <p>&copy; 2023 Responsive Design Example. All rights reserved.</p>
        </footer>
    </div>
</body>
</html>

/* Base Styles */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Arial', sans-serif;
    line-height: 1.6;
    color: #333;
}

.container {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
}

.header {
    background: #2c3e50;
    color: #fff;
    padding: 1rem;
    text-align: center;
}

.navbar {
    background: #34495e;
}

.nav-menu {
    display: flex;
    list-style: none;
    justify-content: space-around;
    padding: 1rem;
}

.nav-item a {
    color: #fff;
    text-decoration: none;
    padding: 0.5rem 1rem;
    transition: background-color 0.3s;
}

.nav-item a:hover {
    background-color: #2c3e50;
    border-radius: 4px;
}

.hamburger {
    display: none;
    cursor: pointer;
}

.bar {
    display: block;
    width: 25px;
    height: 3px;
    margin: 5px auto;
    background-color: #fff;
    transition: all 0.3s ease;
}

.main-content {
    flex: 1;
    padding: 1rem;
}

.hero {
    background: #ecf0f1;
    padding: 2rem;
    margin-bottom: 1rem;
    text-align: center;
    border-radius: 5px;
}

.features {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    margin-bottom: 1rem;
}

.feature-card {
    flex: 1 1 300px;
    background: #fff;
    padding: 1rem;
    border-radius: 5px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

.gallery {
    margin-bottom: 1rem;
}

.grid-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 1rem;
    margin-top: 1rem;
}

.grid-item {
    background: #3498db;
    color: #fff;
    padding: 2rem;
    text-align: center;
    border-radius: 5px;
    min-height: 150px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.sidebar {
    background: #bdc3c7;
    padding: 1rem;
    border-radius: 5px;
}

.news-list {
    list-style-position: inside;
    margin-top: 0.5rem;
}

.footer {
    background: #2c3e50;
    color: #fff;
    text-align: center;
    padding: 1rem;
    margin-top: auto;
}

/* Media Queries */
/* Tablet View */
@media (max-width: 768px) {
    .container {
        grid-template-columns: 1fr;
        grid-template-areas:
            "header"
            "nav"
            "main"
            "sidebar"
            "footer";
    }
    
    .nav-menu {
        position: fixed;
        left: -100%;
        top: 70px;
        flex-direction: column;
        background-color: #34495e;
        width: 100%;
        text-align: center;
        transition: 0.3s;
    }
    
    .nav-menu.active {
        left: 0;
    }
    
    .nav-item {
        margin: 1rem 0;
    }
    
    .hamburger {
        display: block;
        padding: 1rem;
    }
    
    .hamburger.active .bar:nth-child(2) {
        opacity: 0;
    }
    
    .hamburger.active .bar:nth-child(1) {
        transform: translateY(8px) rotate(45deg);
    }
    
    .hamburger.active .bar:nth-child(3) {
        transform: translateY(-8px) rotate(-45deg);
    }
    
    .features {
        flex-direction: column;
    }
}

/* Mobile View */
@media (max-width: 480px) {
    .header h1 {
        font-size: 1.5rem;
    }
    
    .hero {
        padding: 1rem;
    }
    
    .feature-card {
        flex: 1 1 100%;
    }
    
    .grid-container {
        grid-template-columns: 1fr;
    }
}

/* Desktop View - Sidebar Layout */
@media (min-width: 1024px) {
    .container {
        display: grid;
        grid-template-columns: 1fr 300px;
        grid-template-areas:
            "header header"
            "nav nav"
            "main sidebar"
            "footer footer";
    }
    
    .header {
        grid-area: header;
    }
    
    .navbar {
        grid-area: nav;
    }
    
    .main-content {
        grid-area: main;
    }
    
    .sidebar {
        grid-area: sidebar;
    }
    
    .footer {
        grid-area: footer;
    }
}
