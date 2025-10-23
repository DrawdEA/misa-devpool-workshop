## Lab 1: The "Classic" Way (HTML & Standard CSS)

**Objective:** Understand the fundamental relationship between HTML structure and CSS styling by building a simple profile card.

**Prerequisites:**

- A code editor (like VS Code).
- A web browser (Chrome, Firefox, Edge, etc.).

### Step 1: Project Setup

1.  Create a new folder on your computer named `workshop-lab`.
2.  Open this folder in your code editor.
3.  Create two new blank files inside this folder:
    - `index.html`
    - `styles.css`

### Step 2: The HTML Skeleton

Open `index.html` and add the following code. This defines the **structure** of our page. Notice the `class` attributes—these are the "hooks" our CSS will use later.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Lab 1: Classic Dev-Folio</title>
    <!-- This line links our HTML to our CSS file -->
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <!-- The main container for our card -->
    <div class="hero-card">
      <!-- Avatar Image -->
      <img
        class="hero-avatar"
        src="https://i.pravatar.cc/300"
        alt="Developer Avatar"
      />
      <!-- Name Headline -->
      <h1 class="hero-name">Alex Developer</h1>
      <!-- Title Paragraph -->
      <p class="hero-title">Frontend Engineer & UI Enthusiast</p>
    </div>
  </body>
</html>
```

**Action:** Open `index.html` in your browser. It should look very plain and unstructured. This is normal!

### Step 3: The CSS Styling

Open `styles.css` and add the following rules. We will style the page from the outside in.

```css
/* 1. Resetting some defaults and styling the page background */
body {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica,
    Arial, sans-serif;
  background-color: #f1f5f9; /* Light gray-blue */
  margin: 0;
  min-height: 100vh; /* Full viewport height */
  display: grid; /* these 3 lines... */
  place-items: center; /* ...perfectly center... */
  padding: 20px; /* ...our content. */
}

/* 2. Styling the card container */
.hero-card {
  background-color: #ffffff;
  width: 320px;
  padding: 32px;
  border-radius: 16px; /* Rounded corners */
  text-align: center; /* Centers text inside the card */
  box-shadow: 0 10px 15px -3px rgb(0 0 0 / 0.1); /* deeply technical shadow rule */
}

/* 3. Styling the avatar image */
.hero-avatar {
  width: 128px;
  height: 128px;
  border-radius: 50%; /* Makes a square image a perfect circle */
}

/* 4. Styling the typography */
.hero-name {
  margin-top: 24px;
  margin-bottom: 8px;
  font-size: 24px;
  font-weight: 700; /* Bold */
  color: #0f172a; /* Dark slate */
}

.hero-title {
  margin: 0;
  font-size: 16px;
  color: #64748b; /* Medium gray */
}
```

**Action:** Refresh your browser. You should now have a clean, centered, professional-looking profile card.

---
