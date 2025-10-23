## Lab 2: The "Modern" Refactor (Migrating to Tailwind CSS)

**Objective:** Recreate the exact same component without writing _any_ custom CSS, using Tailwind's utility classes. We will also add responsive design and dark mode features.

**Prerequisites:**

- We will use the official online playground to avoid complex installation steps today: **[play.tailwindcss.com](https://play.tailwindcss.com)**

### Step 1: Setup the Playground

1.  Go to [play.tailwindcss.com](https://play.tailwindcss.com).
2.  Delete **all** the default code in the HTML pane (left side).
3.  Copy the `<body>` content from your Lab 1 HTML and paste it into the playground:

```html
<!-- Paste this into Tailwind Play HTML pane -->
<div class="hero-card">
  <img
    class="hero-avatar"
    src="https://i.pravatar.cc/300"
    alt="Developer Avatar"
  />
  <h1 class="hero-name">Alex Developer</h1>
  <p class="hero-title">Frontend Engineer & UI Enthusiast</p>
</div>
```

_Note: It will look ugly again because standard CSS classes like `.hero-card` don't mean anything to Tailwind._

### Step 2: Refactor the Container

We will replace the `class="hero-card"` with Tailwind utilities that match our old CSS values.

- `width: 320px` -> `w-80`
- `background-color: #ffffff` -> `bg-white`
- `padding: 32px` -> `p-8`
- `border-radius: 16px` -> `rounded-2xl`
- `text-align: center` -> `text-center`
- `box-shadow: ...` -> `shadow-lg`

**Update your HTML:**

```html
<div class="w-80 bg-white p-8 rounded-2xl text-center shadow-lg">
  <!-- inner content... -->
</div>
```

### Step 3: Refactor the Content

Now, let's style the image and text to match Lab 1.

**1. The Image (`.hero-avatar`):**

- `width: 128px` -> `w-32`
- `height: 128px` -> `h-32`
- `border-radius: 50%` -> `rounded-full`
- _New requirement:_ In Tailwind, images don't center automatically in a text-center container. Add `mx-auto` (margin-x: auto) to center it.

**2. The Name (`.hero-name`):**

- `margin-top: 24px` -> `mt-6`
- `margin-bottom: 8px` -> `mb-2`
- `font-size: 24px` -> `text-3xl`
- `font-weight: 700` -> `font-bold`
- `color: #0f172a` -> `text-slate-900`

**3. The Title (`.hero-title`):**

- `font-size: 16px` -> `text-base`
- `color: #64748b` -> `text-slate-500`

**Final Refactored HTML:**

```html
<div class="w-80 bg-white p-8 rounded-2xl text-center shadow-lg">
  <img
    class="w-32 h-32 rounded-full mx-auto"
    src="https://i.pravatar.cc/300"
    alt="Developer Avatar"
  />
  <h1 class="mt-6 mb-2 text-3xl font-bold text-slate-900">Alex Developer</h1>
  <p class="text-base text-slate-500">Frontend Engineer & UI Enthusiast</p>
</div>
```

_Wait, where is the gray background?_ In Tailwind Play, we can add utility classes directly to the `<html>` or `<body>` tags if we want, but for now, you can just see the white card against the white background.

### Step 4: Tailwind Superpowers (Responsive & Dark Mode)

Let's do things that are difficult in standard CSS but easy in Tailwind.

**1. Make it Responsive (Mobile First):**
Currently, the card is strictly `w-80` (320px). Let's say on small phones, we want it to be full width, but on tablets and up, it should be fixed width.

- Update the main `<div>` width class: `w-full md:w-80`
  - _Translation: Be 100% width by default, BUT on **m**e**d**ium screens and larger, be 320px wide._

**2. Add Dark Mode Support:**
We can change how it looks when the user prefers dark themes by adding `dark:` prefixes.

- Update the main `<div>`: Add `dark:bg-slate-800`
- Update the `<h1>`: Add `dark:text-white`
- Update the `<p>`: Add `dark:text-slate-400`

**Final Component:**

```html
<!-- Try resizing the preview window to test responsiveness. -->
<!-- Try toggling the "Dark Mode" switch in Tailwind Play to test dark mode. -->

<div
  class="w-full md:w-80  bg-white dark:bg-slate-800  p-8 rounded-2xl text-center shadow-lg"
>
  <img
    class="w-32 h-32 rounded-full mx-auto"
    src="https://i.pravatar.cc/300"
    alt="Developer Avatar"
  />
  <h1 class="mt-6 mb-2 text-3xl font-bold text-slate-900 dark:text-white">
    Alex Developer
  </h1>
  <p class="text-base text-slate-500 dark:text-slate-400">
    Frontend Engineer & UI Enthusiast
  </p>
</div>
```
