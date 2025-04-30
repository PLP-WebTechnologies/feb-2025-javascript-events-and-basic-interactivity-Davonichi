# 🎯 JavaScript Event Handling & Interactive Elements Assignment

Welcome to the **ultimate JavaScript playground**! 🎉 This assignment is where we turn boring web pages into dynamic, responsive, *alive* experiences. Get ready to master **event handling**, build **interactive components**, and validate forms like a pro! 💪

## 📁 Assignment Structure

```
📂 js-event-assignment/
├── index.html         # Your playground – where it all comes together
├── style.css          # Keep it cute (optional but encouraged)
└── script.js          # The JavaScript wizardry happens here
```

---

## 🧪 What to Build

Here’s what your interactive bundle of joy should include:

### 1. Event Handling 🎈  
- Button click ✅  
- Hover effects ✅  
- Keypress detection ✅  
- Bonus: A secret action for a *double-click* or *long press* 🤫

### 2. Interactive Elements 🎮  
- A button that changes text or color  
- An image gallery or slideshow  
- Tabs or accordion-style content  
- Bonus: Add some animation using JS or CSS ✨

### 3. Form Validation 📋✅  
- Required field checks  
- Email format validation  
- Password rules (e.g., min 8 characters)  
- Bonus: Real-time feedback while typing

---

## 🧙‍♂️ Pro Tips

- Keep your code clean and commented – your future self will thank you!
- Think about **user experience** – what makes your site more *fun* to use?
- Don’t be afraid to **Google and experiment** – that’s how real developers roll!

---

## 🎉 Now Go Make It Fun!

Remember – this isn't just code. It's your **first step toward creating magical user experiences**. So play around, break stuff (then fix it), and most of all, have FUN! 😄

Happy Coding! 💻✨  

HTML Structure: (index.html)

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Webpage</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Interactive Webpage with JavaScript</h1>
    </header>

    <section>
        <h2>Button Click and Hover Effects</h2>
        <button id="changeTextButton">Click me!</button>
        <p id="hoverMessage">Hover over the button!</p>
    </section>

    <section>
        <h2>Image Gallery</h2>
        <div id="gallery">
            <img src="image1.jpg" alt="Image 1">
            <img src="image2.jpg" alt="Image 2">
            <img src="image3.jpg" alt="Image 3">
        </div>
    </section>

    <section>
        <h2>Tabs</h2>
        <div class="tabs">
            <button class="tab" data-tab="1">Tab 1</button>
            <button class="tab" data-tab="2">Tab 2</button>
            <button class="tab" data-tab="3">Tab 3</button>
        </div>
        <div class="tab-content" id="tab-1">
            <p>Content for Tab 1</p>
        </div>
        <div class="tab-content" id="tab-2">
            <p>Content for Tab 2</p>
        </div>
        <div class="tab-content" id="tab-3">
            <p>Content for Tab 3</p>
        </div>
    </section>

    <section>
        <h2>Form Validation</h2>
        <form id="myForm">
            <label for="username">Username (required):</label>
            <input type="text" id="username" required><br>

            <label for="email">Email (required):</label>
            <input type="email" id="email" required><br>

            <label for="password">Password (min 8 characters):</label>
            <input type="password" id="password" required><br>

            <button type="submit">Submit</button>
        </form>
    </section>

    <footer>
        <p>Created with ❤️ using JavaScript</p>
    </footer>

    <script src="script.js"></script>
</body>
</html>

CSS Styles (styles.css):

body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    margin: 0;
    padding: 0;
}

header {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 20px;
}

section {
    margin: 20px;
    padding: 20px;
    background-color: white;
    border-radius: 8px;
}

button {
    padding: 10px 20px;
    background-color: #4CAF50;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #45a049;
}

button:active {
    background-color: #3e8e41;
}

#gallery img {
    margin: 10px;
    width: 200px;
    height: 200px;
    cursor: pointer;
}

.tabs {
    display: flex;
}

.tab {
    padding: 10px;
    margin-right: 5px;
    background-color: #f1f1f1;
    cursor: pointer;
}

.tab:hover {
    background-color: #ddd;
}

.tab-content {
    display: none;
    padding: 20px;
    background-color: #f1f1f1;
    margin-top: 10px;
}

input {
    padding: 8px;
    margin: 10px 0;
    width: 200px;
}

.error {
    color: red;
    font-size: 12px;
}

footer {
    text-align: center;
    padding: 10px;
    background-color: #333;
    color: white;
    position: fixed;
    width: 100%;
    bottom: 0;
}

JavaScript (script.js):

// 1. Event Handling 🎈

document.getElementById('changeTextButton').addEventListener('click', function() {
    document.getElementById('hoverMessage').textContent = 'You clicked the button!';
});

document.getElementById('changeTextButton').addEventListener('mouseover', function() {
    document.getElementById('hoverMessage').textContent = 'Hovering over the button!';
});

// 2. Image Gallery 🎮

const images = document.querySelectorAll('#gallery img');
images.forEach(image => {
    image.addEventListener('click', function() {
        alert('Image clicked: ' + image.alt);
    });
});

// 3. Tabs Functionality 🎮

const tabs = document.querySelectorAll('.tab');
tabs.forEach(tab => {
    tab.addEventListener('click', function() {
        const tabNumber = tab.getAttribute('data-tab');
        const contents = document.querySelectorAll('.tab-content');
        contents.forEach(content => {
            content.style.display = 'none';
        });
        document.getElementById('tab-' + tabNumber).style.display = 'block';
    });
});

// 4. Form Validation 📋✅

const form = document.getElementById('myForm');
form.addEventListener('submit', function(event) {
    let valid = true;
    let username = document.getElementById('username').value;
    let email = document.getElementById('email').value;
    let password = document.getElementById('password').value;

    if (!username) {
        alert('Username is required');
        valid = false;
    }

    const emailPattern = /^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,6}$/;
    if (!email || !emailPattern.test(email)) {
        alert('Please enter a valid email');
        valid = false;
    }

    if (password.length < 8) {
        alert('Password must be at least 8 characters long');
        valid = false;
    }

    if (!valid) {
        event.preventDefault();
    }
});

// 5. Secret Action - Double Click or Long Press 🤫

let timer;
document.getElementById('changeTextButton').addEventListener('mousedown', function() {
    timer = setTimeout(function() {
        alert('Long press detected!');
    }, 1000); // Trigger long press after 1 second
});

document.getElementById('changeTextButton').addEventListener('mouseup', function() {
    clearTimeout(timer);
});

document.getElementById('changeTextButton').addEventListener('dblclick', function() {
    alert('Double click detected!');
});
