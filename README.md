## index.html
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dribbble </title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <nav>
            <div class="logo">Dribbble</div>
            <ul>
                <li><a href="#">Sign Up</a></li>
                <li><a href="#">Log In</a></li>
            </ul>
        </nav>
        <div class="header-content">
            <h1>Discover the world’s top designers & creatives</h1>
            <p>Dribbble is the leading destination to find & showcase creative work and home to the world's best design professionals.</p>
            <a href="#" class="cta">Sign up</a>
        </div>
    </header>

    <section class="gallery-section">
        <button class="gallery-nav prev" onclick="scrollGallery('gallery1', -200)">&#10094;</button>
        <div class="gallery" id="gallery1">
            <div class="gallery-item"><img src="./images/zimg7.png" alt="Image 7"></div>
            <div class="gallery-item"><img src="./images/zimg8.png" alt="Image 8"></div>
            <div class="gallery-item"><img src="./images/zimg1.jpeg" alt="Image 1"></div>
            <div class="gallery-item"><img src="./images/zimg2.jpeg" alt="Image 2"></div>
            <div class="gallery-item"><img src="./images/zimg3.jpeg" alt="Image 3"></div>
            <div class="gallery-item"><img src="./images/zimg4.jpg" alt="Image 4"></div>
            <div class="gallery-item"><img src="./images/zimg5.jpg" alt="Image 5"></div>
            <div class="gallery-item"><img src="./images/zimg6.jpg" alt="Image 6"></div>
        </div>
        <button class="gallery-nav next" onclick="scrollGallery('gallery1', 200)">&#10095;</button>
    </section>

    <section class="profiles">
        <div class="profile-grid">

            <div class="profile-item">
                <img src="./images/yimg1.avif" alt="Profile 1" class="profile-pic">
                <p class="profile-name">Profile 1</p>
            </div>
        
            <div class="profile-item">
                <img src="./images/yimg2.avif" alt="Profile 2" class="profile-pic">
                <p class="profile-name">Profile 2</p>
            </div>
            <div class="profile-item">
                <img src="./images/yimg3.avif" alt="Profile 3" class="profile-pic">
                <p class="profile-name">Profile 3</p>
            </div>

            <div class="profile-item">
                <img src="./images/yimg4.avif" alt="Profile 4" class="profile-pic">
                <p class="profile-name">Profile 4</p>
            </div>

            <div class="profile-item">
                <img src="./images/yimg5.avif" alt="Profile 5" class="profile-pic">
                <p class="profile-name">Profile 5</p>
            </div>

            <div class="profile-item">
                <img src="./images/yimg6.avif" alt="Profile 6" class="profile-pic">
                <p class="profile-name">Profile 6</p>
            </div>

            <div class="profile-item">
                <img src="./images/yimg7.avif" alt="Profile 7" class="profile-pic">
                <p class="profile-name">Profile 7</p>
            </div>



           
    </section>

    <section class="gallery-section">
        <button class="gallery-nav prev" onclick="scrollGallery('gallery2', -200)">&#10094;</button>
        <div class="gallery" id="gallery2">
            
            <div class="gallery-item"><img src="./images/dimg5.jpg" alt="Image 9"></div>
            <div class="gallery-item"><img src="./images/dimg2.jpg" alt="Image 10"></div>
            <div class="gallery-item"><img src="./images/image11.jpg" alt="Image 11"></div>
            <div class="gallery-item"><img src="./images/image12.jpg" alt="Image 12"></div>
            <div class="gallery-item"><img src="./images/image13.jpg" alt="Image 13"></div>
            <div class="gallery-item"><img src="./images/image14.jpg" alt="Image 14"></div>
            <div class="gallery-item"><img src="./images/image15.jpg" alt="Image 15"></div>
        </div>
        <button class="gallery-nav next" onclick="scrollGallery('gallery2', 200)">&#10095;</button>
    </section>

    <footer>
        <p>&copy;Dribbble 2024. All rights reserved.</p>
    </footer>
    <script src="script.js"></script>
</body>
</html>
```
## script.js
```
let autoScrollSpeed = 1; 
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
## style.css
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
    background-color: #f7a809;
    color: rgb(0, 0, 0);
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
    color:  rgb(0, 0, 0);
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
    background-color: rgb(255, 255, 255);
    color:   #f7a809;
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
    background-color:  #f7a809;
    color:  black;
    text-align: center;
    padding: 10px 0;
}
```
## output
![image](https://github.com/ajay45d/dribbble/assets/134574325/633629e9-bdd1-4c76-b3e9-25c00bd506cb)
![image](https://github.com/ajay45d/dribbble/assets/134574325/173b03aa-18d4-41c3-b49d-e8c3c19a6e28)

