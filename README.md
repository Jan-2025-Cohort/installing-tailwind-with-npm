# Set Up Tailwind CSS Using NPM

### 🎯 Objective:
In this assignment, you will initialize a new project and set up **Tailwind CSS** using **NPM**. By the end, you’ll have a custom Tailwind build that styles a button on a basic webpage.

Use this page in the tailwind documentation to help with the steps: [https://tailwindcss.com/docs/installation/tailwind-cli](https://tailwindcss.com/docs/installation/tailwind-cli)
---

## 📦 Part 1: Initialize Your Project

1. Clone this repo for your project and open it in your terminal:
   ```bash
   git clone 'github clone url'
   cd installing-tailwind-with-npm
   ```

2. Initialize NPM:
   ```bash
   npm init
   ```

---

## 🌬️ Part 2: Install Tailwind CSS

3. Install Tailwind as a development dependency:
   ```bash
   npm install tailwindcss @tailwindcss/cli
   ```

4. Generate the Tailwind config file:
   ```bash
   npx @tailwindcss/cli -i ./src/input.css -o ./src/output.css --watch
   ```

---

## 🧱 Part 3: Set Up Your Files and Folders

5. Create these folders and files (These are the terminal commands):
   ```bash
   mkdir styles dist
   touch styles/input.css index.html
   ```

6. In `styles/input.css`, paste this code:
   We are adding the tailwind style classes we want to access in this project
   ```css
   @tailwind base;
   @tailwind components;
   @tailwind utilities;
   ```

---

## ⚙️ Part 4: Configure Your Build Script
We need this script to compile the css we have in tailwind. The build script runs a command that tells Tailwind to take your custom CSS file (with @tailwind directives) and compile it into real, usable CSS that the browser can understand. It watches your files and updates the output every time you make a change.

7. Open `package.json`, find the `"scripts"` section, and add:

   ```json
   "scripts": {
     "build": "npx tailwindcss -i ./src/input.css -o ./src/output.css --watch"
   }
   ```

---

## 🧪 Part 5: Create Your Web Page

8. In `index.html`, add the following boilerplate code:

   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
     <meta charset="UTF-8" />
     <meta name="viewport" content="width=device-width, initial-scale=1.0" />
     <title>Tailwind Assignment</title>
     <link href="./src/output.css" rel="stylesheet" />
   </head>
   <body class="bg-gray-100 flex justify-center items-center h-screen">
     <button class="bg-blue-600 text-white font-bold px-6 py-3 rounded hover:bg-blue-700 transition">
       Click Me!
     </button>
   </body>
   </html>
   ```

---

## 🏗️ Part 6: Build and Watch

9. Run this command in your terminal to start Tailwind’s build process:

   ```bash
   npm run build
   ```

✅ You should now see `dist/output.css` being generated and updated as you work.

---

## 💡 Bonus Challenges

- Try changing the button to `bg-green-500` or `bg-red-600`
- Add `shadow-lg`, `rounded-full`, or `text-xl` for visual flair
- Add a second styled element below the button
