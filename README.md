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
    <title>Interactive Web Page</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Welcome to My Interactive Web Page!</h1>
    </header>

    <section id="gallery">
        <h2>Image Gallery</h2>
        <div class="gallery-images">
            <img src="image1.jpg" alt="Image 1" class="gallery-img">
            <img src="image2.jpg" alt="Image 2" class="gallery-img">
            <img src="image3.jpg" alt="Image 3" class="gallery-img">
        </div>
    </section>

    <section id="tabs">
        <button class="tab-button" onclick="toggleTab(1)">Tab 1</button>
        <button class="tab-button" onclick="toggleTab(2)">Tab 2</button>
        <div class="tab-content" id="tab1">
            <p>Content of Tab 1.</p>
        </div>
        <div class="tab-content" id="tab2">
            <p>Content of Tab 2.</p>
        </div>
    </section>

    <section id="form-validation">
        <h2>Form Validation</h2>
        <form id="userForm">
            <label for="email">Email:</label>
            <input type="email" id="email" required>
            <span id="email-error" class="error-message"></span><br>
            
            <label for="password">Password (min 8 characters):</label>
            <input type="password" id="password" required>
            <span id="password-error" class="error-message"></span><br>
            
            <button type="submit">Submit</button>
        </form>
    </section>

    <button id="dynamicButton">Click Me!</button>

    <script src="script.js"></script>
</body>
</html>


CSS Styles (styles.css):

body {
    font-family: Arial, sans-serif;
}

button {
    padding: 10px 20px;
    font-size: 16px;
    cursor: pointer;
    transition: background-color 0.3s;
}

button:hover {
    background-color: #4CAF50;
}

.gallery-images img {
    width: 100px;
    height: 100px;
    margin: 10px;
    cursor: pointer;
    transition: transform 0.3s;
}

.gallery-images img:hover {
    transform: scale(1.1);
}

.tab-content {
    display: none;
}

.tab-content.active {
    display: block;
}

.error-message {
    color: red;
    font-size: 12px;
}

button.active {
    background-color: #008CBA;
}


JavaScript (script.js):

// Event Handling

// Button click to change text and color
document.getElementById("dynamicButton").addEventListener("click", function() {
    this.innerHTML = "You clicked me!";
    this.style.backgroundColor = "#f44336";
});

// Hover effect for gallery images
const galleryImages = document.querySelectorAll(".gallery-img");
galleryImages.forEach(img => {
    img.addEventListener("mouseover", () => {
        img.style.transform = "scale(1.1)";
    });
    img.addEventListener("mouseout", () => {
        img.style.transform = "scale(1)";
    });
});

// Keypress detection
document.addEventListener("keypress", (e) => {
    console.log("Key pressed: " + e.key);
});

// Double-click action
document.getElementById("dynamicButton").addEventListener("dblclick", function() {
    alert("Double-clicked!");
});

// Form Validation
const form = document.getElementById("userForm");
form.addEventListener("submit", function(event) {
    let valid = true;
    
    // Email validation
    const email = document.getElementById("email");
    const emailError = document.getElementById("email-error");
    const emailPattern = /^[^ ]+@[^ ]+\.[a-z]{2,3}$/;
    if (!email.value.match(emailPattern)) {
        emailError.textContent = "Please enter a valid email address.";
        valid = false;
    } else {
        emailError.textContent = "";
    }

    // Password validation
    const password = document.getElementById("password");
    const passwordError = document.getElementById("password-error");
    if (password.value.length < 8) {
        passwordError.textContent = "Password must be at least 8 characters.";
        valid = false;
    } else {
        passwordError.textContent = "";
    }

    // If validation fails, prevent form submission
    if (!valid) {
        event.preventDefault();
    }
});

// Tabs interaction
function toggleTab(tabNumber) {
    document.querySelectorAll(".tab-content").forEach(tab => {
        tab.classList.remove("active");
    });
    document.getElementById("tab" + tabNumber).classList.add("active");
}

// Real-time feedback while typing in the password field
const passwordField = document.getElementById("password");
passwordField.addEventListener("input", () => {
    if (passwordField.value.length < 8) {
        passwordField.style.borderColor = "red";
    } else {
        passwordField.style.borderColor = "green";
    }
});
