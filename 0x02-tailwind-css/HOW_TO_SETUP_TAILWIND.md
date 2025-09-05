
## HOW I SET TAILWIND (The Standard Way) 🚀
This task is a continuation of 0x01, so we already have a repo. 

### 1. Create the Project Directory
I started by creating the directory `0x02-tailwind-css` inside my project folder.

### 2. Initialize the Node.js Project
Next, I opened `./0x02-tailwind-css` with Visual Studio Code and opened the terminal inside it.

I initialized the Node.js project by typing:

```bash
npm init
````

I just kept pressing ENTER to accept all the defaults, which was super quick and created the `package.json` file.

### 3. Install Tailwind CSS

Following the latest Tailwind documentation, I installed it as a dev dependency. In the terminal, I typed:

```bash
npm install -D tailwindcss
```

This command is the modern way to do it. It created the `node_modules` directory and the `package-lock.json` file.

### 4. Generate Tailwind Configuration

Now, I needed to generate the Tailwind configuration file. I ran:

```bash
npx tailwindcss init
```

This command is key! It created `tailwind.config.js` in my project root. Without this, Tailwind doesn't know what to do.

### 5. Configure Tailwind

I opened `tailwind.config.js` and edited the content array. This step is crucial because it tells Tailwind which files to scan for classes. I changed it to:

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./src/**/*.{html,js}"], // This line is the important part
  theme: {
    extend: {},
  },
  plugins: [],
}
```

### 6. Create Source Files

I created a new directory called `src/`. Inside this directory, I created two files: `input.css` and `index.html`.

In my `input.css` file, I pasted the standard Tailwind directives:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

In `index.html`, I set up the basic HTML boilerplate. The most important part was linking to the future stylesheet, which is going to be in a separate directory called `dist`. So, I added this line in the `<head>`:

```html
<link href="../dist/output.css" rel="stylesheet">
```

And for a test, I added the Hello world! heading with a few Tailwind classes:

```html
<h1 class="text-3xl font-bold underline">
  Hello world!
</h1>
```

To make my life easier, I created a shortcut in my `package.json` file. Under the `"scripts"` section, I added a `"dev"` command:

### 7. Add a Build Script

```json
"scripts": {
  "test": "echo \"Error: no test specified\" && exit 1",
  "dev": "npx tailwindcss -i ./src/input.css -o ./dist/output.css --watch"
}
```

This command watches my source files and automatically generates `output.css` in a new `dist/` folder. This is a much cleaner approach than putting it in `src/`.

Finally, I ran:

```bash
npm run dev
```

The command immediately created the `dist/` directory and the `output.css` file. I could see the terminal showing it was in "watch" mode.

### 8. Run the Development Server

With Live Server in VSC, I opened my `index.html`. The "Hello world!" heading appeared in bold, underlined, and larger, which confirmed that Tailwind was working properly.

### IMPORTANT REMARKS

* You don't need to manually edit `input.css` or `output.css` for Tailwind classes. Tailwind's CLI does the magic.
* The `npm run dev` command is what starts the watcher, and it's what you'll run whenever you start working on your project. If you're not seeing your styles, make sure the watcher is still running in your terminal.
* The `content` path in `tailwind.config.js` is the brain of the operation. If you add more files or change your directory structure, you need to update that path so Tailwind can find your new classes.

```
