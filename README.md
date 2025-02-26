<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Art Gallery with Animations</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            overflow-x: hidden;
        }

        /* Header Animation */
        header {
            background: linear-gradient(45deg, #2c3e50, #3498db);
            color: white;
            text-align: center;
            padding: 30px;
            animation: slideInFromTop 1s ease-out;
        }

        @keyframes slideInFromTop {
            0% { transform: translateY(-100%); opacity: 0; }
            100% { transform: translateY(0); opacity: 1; }
        }

        /* Navigation Animation */
        nav {
            background-color: #333;
            padding: 15px;
            text-align: center;
        }

        nav a {
            color: white;
            text-decoration: none;
            margin: 0 20px;
            font-size: 18px;
            position: relative;
            transition: color 0.3s ease;
        }

        nav a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            background-color: #ffcc00;
            left: 0;
            bottom: -5px;
            transition: width 0.4s ease;
        }

        nav a:hover::after {
            width: 100%;
        }

        nav a:hover {
            color: #ffcc00;
            animation: bounce 0.5s ease;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
            40% { transform: translateY(-10px); }
            60% { transform: translateY(-5px); }
        }

        /* Gallery Animation */
        .gallery {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            padding: 20px;
        }

        .art-item {
            background-color: white;
            margin: 15px;
            padding: 15px;
            width: 250px;
            text-align: center;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
            opacity: 0;
            animation: fadeInUp 1s ease forwards;
            animation-delay: calc(0.2s * var(--i));
        }

        .art-item:nth-child(1) { --i: 1; }
        .art-item:nth-child(2) { --i: 2; }
        .art-item:nth-child(3) { --i: 3; }

        @keyframes fadeInUp {
            0% { opacity: 0; transform: translateY(50px); }
            100% { opacity: 1; transform: translateY(0); }
        }

        .art-item:hover {
            transform: scale(1.05) rotate(2deg);
            transition: transform 0.3s ease;
            box-shadow: 0 8px 16px rgba(0,0,0,0.3);
        }

        .art-item img {
            max-width: 100%;
            height: auto;
            border-radius: 5px;
            transition: transform 0.5s ease;
        }

        .art-item:hover img {
            transform: scale(1.1);
        }

        /* Footer Animation */
        footer {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 15px;
            width: 100%;
            animation: fadeIn 2s ease-in;
        }

        @keyframes fadeIn {
            0% { opacity: 0; }
            100% { opacity: 1; }
        }
    </style>
</head>
<body>
    <header>
        <h1>Art Gallery</h1>
        <p>Discover Beautiful Creations</p>
    </header>

    <nav>
        <a href="#home">Home</a>
        <a href="#gallery">Gallery</a>
        <a href="#about">About</a>
        <a href="#contact">Contact</a>
    </nav>

    <section class="gallery" id="gallery">
        <div class="art-item">
            <img src="https://via.placeholder.com/200x150" alt="Artwork 1">
            <h3>Painting 1</h3>
            <p>A beautiful landscape</p>
        </div>
        <div class="art-item">
            <img src="https://via.placeholder.com/200x150" alt="Artwork 2">
            <h3>Painting 2</h3>
            <p>Abstract art</p>
        </div>
        <div class="art-item">
            <img src="https://via.placeholder.com/200x150" alt="Artwork 3">
            <h3>Sculpture</h3>
            <p>A modern piece</p>
        </div>
    </section>

    <footer>
        <p>© 2025 Art Gallery | All Rights Reserved</p>
    </footer>
</body>
</html>
