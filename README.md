### index.html:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dribbble Clone</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <nav>
            <div class="logo">Dribbble Clone</div>
            <ul>
                <li><a href="#">Sign Up</a></li>
                <li><a href="#">Log In</a></li>
            </ul>
        </nav>
        <div class="header-content">
            <h1>Discover the world’s top designers & creatives</h1>
            
            <a href="#" class="cta">Sign up</a>
        </div>
    </header>

    <!-- First Gallery -->
    <section class="gallery-section">
        <button class="gallery-nav prev" onclick="scrollGallery('gallery1', -200)">&#10094;</button>
        <div class="gallery" id="gallery1">
            <div class="gallery-item"><img src="BUSI Idea 1.jpg" alt="Image 7"></div>
            <div class="gallery-item"><img src="BUSI Idea 2.jpg" alt="Image 8"></div>
            <div class="gallery-item"><img src="BUSI Idea 3.jpg" alt="Image 1"></div>
            <div class="gallery-item"><img src="BUSI Idea 4" alt="Image 2"></div>
            <div class="gallery-item"><img src="BUSI Idea 5" alt="Image 3"></div>
            <div class="gallery-item"><img src="BUSI Idea 6" alt="Image 4"></div>
            <div class="gallery-item"><img src="BUSI Idea 7" alt="Image 5"></div>
            <div class="gallery-item"><img src="BUSI Idea 8" alt="Image 6"></div>
        </div>
        <button class="gallery-nav next" onclick="scrollGallery('gallery1', 200)">&#10095;</button>
    </section>

    <!-- User Profiles -->
    <section class="profiles">
        <div class="profile-grid">

            <div class="profile-item">
                <img src="user1" alt="User 1" class="profile-pic">
                <p class="profile-name">User 1</p>
            </div>
            
            <div class="profile-item">
                <img src="user2" alt="User 2" class="profile-pic">
                <p class="profile-name">User 2</p>
            </div>
            
            <div class="profile-item">
                <img src="user3" alt="User 3" class="profile-pic">
                <p class="profile-name">User 2</p>
            </div>

            <div class="profile-item">
                <img src="user4" alt="User 4" class="profile-pic">
                <p class="profile-name">User 2</p>
            </div>

            <div class="profile-item">
                <img src="user5" alt="User 5" class="profile-pic">
                <p class="profile-name">User 2</p>
            </div>

            <div class="profile-item">
                <img src="user6" alt="User 6" class="profile-pic">
                <p class="profile-name">User 2</p>
            </div>

            <div class="profile-item">
                <img src="user7" alt="User 7" class="profile-pic">
                <p class="profile-name">User 2</p>
            </div>

            

            

            


            

            

            
    </section>

    <!-- Second Gallery -->
    <section class="gallery-section">
        <button class="gallery-nav prev" onclick="scrollGallery('gallery2', -200)">&#10094;</button>
        <div class="gallery" id="gallery2">
            
            <div class="gallery-item"><img src="212221040102 - Mathan M.jpg" alt="Image 9"></div>
            <div class="gallery-item"><img src="gallery2" alt="Image 10"></div>
            <div class="gallery-item"><img src="gallery3" alt="Image 11"></div>
            <div class="gallery-item"><img src="gallery4.jpg" alt="Image 12"></div>
            <div class="gallery-item"><img src="gallery5" alt="Image 13"></div>
            <div class="gallery-item"><img src="gallery6" alt="Image 14"></div>
            
        </div>
        <button class="gallery-nav next" onclick="scrollGallery('gallery2', 200)">&#10095;</button>
    </section>

    <footer>
        <p>&copy; 2024 Dribbble Clone. All rights reserved.</p>
    </footer>
    <script src="script.js"></script>
</body>
</html>
```
### script.js:
```
let autoScrollSpeed = 1; // Adjust the speed as needed
let scrollInterval1;
let scrollInterval2;

function startAutoScroll(galleryId) {
    const gallery = document.getElementById(galleryId);
    scrollInterval1 = setInterval(() => {
        gallery.scrollBy({
            left: autoScrollSpeed,
            behavior: 'smooth'
        });
    }, 20); // Adjust the interval for smoother scrolling
}

function stopAutoScroll() {
    clearInterval(scrollInterval1);
    clearInterval(scrollInterval2);
}

document.addEventListener("DOMContentLoaded", () => {
    const gallery1 = document.getElementById('gallery1');
    const gallery2 = document.getElementById('gallery2');

    startAutoScroll('gallery1');
    startAutoScroll('gallery2');

    gallery1.addEventListener('mouseenter', stopAutoScroll);
    gallery1.addEventListener('mouseleave', () => startAutoScroll('gallery1'));

    gallery2.addEventListener('mouseenter', stopAutoScroll);
    gallery2.addEventListener('mouseleave', () => startAutoScroll('gallery2'));
});
```
### Style.css:
```
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    background-color: #f5f5f5;
    color: #333;
}

header {
    background-color:black;
    color: white;
    padding: 20px 0;
    text-align: center;
}

nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 20px;
}

nav .logo {
    font-size: 24px;
    font-weight: bold;
}

nav ul {
    list-style: none;
    display: flex;
}

nav ul li {
    margin-left: 20px;
}

nav ul li a {
    color: white;
    text-decoration: none;
}

.header-content {
    max-width: 600px;
    margin: 40px auto;
}

.header-content h1 {
    font-size: 36px;
    margin-bottom: 10px;
}

.header-content p {
    font-size: 18px;
    margin-bottom: 20px;
}

.header-content .cta {
    display: inline-block;
    padding: 10px 20px;
    background-color: white;
    color: black;
    text-decoration: none;
    border-radius: 5px;
}

.gallery-section {
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 20px 0;
    position: relative;
}

.gallery {
    display: flex;
    overflow-x: hidden;
    scroll-behavior: smooth;
    padding: 20px;
}

.gallery-item {
    min-width: 200px;
    min-height: 150px;
    margin: 10px;
    overflow: hidden;
    border-radius: 10px;
}

.gallery-item img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 10px;
}

.gallery-nav {
    background: none;
    border: none;
    font-size: 24px;
    cursor: pointer;
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
}

.prev {
    left: 0;
}

.next {
    right: 0;
}

.profiles {
    padding: 20px;
}

.profile-grid {
    display: grid;
    grid-template-columns: repeat(7, 1fr);
    gap: 10px;
    justify-content: center;
}

.profile-item {
    text-align: center;
}

.profile-pic {
    width: 100px;
    height: 100px;
    object-fit: cover;
    border-radius: 50%;
    margin-bottom: 10px;
}

.profile-name {
    font-size: 14px;
    font-weight: bold;
}

footer {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 10px 0;
}
```
### OUTPUT:
![Screenshot (37)](https://github.com/Mathananthi/CSS-Advance/assets/135731816/f13705b5-e1d0-4bbf-ba65-62f103e42089)
![Screenshot (38)](https://github.com/Mathananthi/CSS-Advance/assets/135731816/a26ed3bb-8c78-4cbe-8c25-fb90764354d9)
