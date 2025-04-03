//1. Create the HTML Structure (index.html)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Blog</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section class="blog-posts">
            <article class="post">
                <h2>Blog Post Title</h2>
                <p class="excerpt">This is an excerpt of the blog post. It's a preview of the full article...</p>
                <button class="read-more" onclick="showFullPost(this)">Read More</button>
                <div class="full-post">
                    <p>This is the full content of the blog post. It appears after clicking "Read More"...</p>
                </div>
            </article>
            <article class="post">
                <h2>Another Blog Post Title</h2>
                <p class="excerpt">This is another excerpt. More exciting content for the readers...</p>
                <button class="read-more" onclick="showFullPost(this)">Read More</button>
                <div class="full-post">
                    <p>This is the full content for the second post. Enjoy reading!</p>
                </div>
            </article>
        </section>

        <section id="contact">
            <h2>Contact Us</h2>
            <form id="contact-form">
                <label for="name">Name:</label>
                <input type="text" id="name" required><br><br>
                <label for="message">Message:</label>
                <textarea id="message" required></textarea><br><br>
                <button type="submit">Send Message</button>
            </form>
        </section>
    </main>

    <footer>
        <p>&copy; 2025 My Blog</p>
    </footer>

    <script src="script.js"></script>
</body>
</html>

//2. Style the Website with CSS (styles.css)
/* Basic reset and general styling */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
}

header {
    background-color: #333;
    color: white;
    padding: 1rem;
    text-align: center;
}

nav ul {
    list-style: none;
}

nav ul li {
    display: inline;
    margin: 0 10px;
}

nav ul li a {
    color: white;
    text-decoration: none;
}

main {
    padding: 20px;
}

.blog-posts {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}

.post {
    background-color: #f4f4f4;
    padding: 15px;
    border-radius: 8px;
    width: 48%;
}

.full-post {
    display: none;
    margin-top: 10px;
}

button.read-more {
    margin-top: 10px;
    padding: 5px 10px;
    background-color: #007BFF;
    color: white;
    border: none;
    cursor: pointer;
}

button.read-more:hover {
    background-color: #0056b3;
}

/* Responsive design */
@media (max-width: 768px) {
    .blog-posts {
        flex-direction: column;
        align-items: center;
    }

    .post {
        width: 90%;
    }
}

//3. Add JavaScript for Interactivity (script.js)
function showFullPost(button) {
    const fullPost = button.nextElementSibling;
    if (fullPost.style.display === "none" || fullPost.style.display === "") {
        fullPost.style.display = "block";
        button.textContent = "Read Less";
    } else {
        fullPost.style.display = "none";
        button.textContent = "Read More";
    }
}

// Handle contact form submission
document.getElementById("contact-form").addEventListener("submit", function (e) {
    e.preventDefault();
    alert("Thank you for contacting us!");
});


