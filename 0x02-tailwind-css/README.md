# ALX Intermediate Frontend - Tailwind CSS WEEK 2 | 0x02

This repository contains exercises and projects for learning **Tailwind CSS** by building responsive layouts using **Grid** and **Flexbox**.  
Each task builds progressively on the previous one, from setup to creating complex layouts.

### Personal takeway**: 

---> **PROBLEM** At first when I tried to install tailwind I didn't succeed. I checked which option is better to keep installing it for each project or install it globally. Global option sounded good to me so I proceeded with it. In Tailwind Docs I tried VITE  option but it didn't work because I didn't give it time and didn't want to proceed as it kept showing errors. I checked with CHATGPT but it gave me old setups only after checking the output it realizes that it was using an older setup. 

---> **REASON** I believe that I made some mistakes while installing it with vite in terms of files. For example creating a src/ manually where it is provided when you install tailwind. 

---> **LEARNING** Everything seems complicated at first because simply it is new. 
    therefore, I will get back to install VITE globally to see the underlying problem and understand more about VITE itself.
    
---> **SOLUTION** After error and trial and deleting directories for 2 hours I took a step back and read the TAILWIND DOCS. There was the option of CLI, I was already watching a video on it and the setup took only 5 minutes. 


## To view how I sat tailwind via CLI please check with HOW_TO_SETUP_TAILWIND.md file.

## 📂 Repository Structure
alx-intermediate-frontend/
└── 0x02-tailwind-css/
├── src/
│ ├── input.css
│ └── output.css
|── imgs/ 
├── tailwind.config.js
├── 1-index.html
├── 2-index.html
├── 3-nav_index.html
├── 4-flexbox_index.html
├── 5-gridflex_index.html
└── 6-imageGallery.html
└── README.md


## 🚀 0. Setting Up and Installing Tailwind CSS
**Objective:** Configure and install Tailwind CSS.

### Instructions
1. Install Tailwind CSS.
2. Create `tailwind.config.js`:
   ```js
   /** @type {import('tailwindcss').Config} */
   module.exports = {
     content: ["./src/**/*.{html,js}"],
     theme: {
       extend: {},
     },
     plugins: [],
   }
## IMPORTANT! Install tailwind using the Tailwind CLI way not vite. Through CLI is much easier to setup. 

### 1. Creating a Responsive CSS Grid Layout
#### File: 1-index.html

* **Objective**: Create a 3-column grid layout with responsive design.
- Use Tailwind’s grid grid-cols-3 gap-4.
- Each column has increasing shades of blue:
    ```<div class="bg-blue-200 p-4">Column 1</div>
    <div class="bg-blue-300 p-4">Column 2</div>
    <div class="bg-blue-400 p-4">Column 3</div>```
- Add a responsive rule in input.css:
    ``` @media (max-width: 768px) {
    main { grid-template-columns: 1fr; }
    }```

### 🟩 2. Building a Complex Page Layout with Nested Grids
#### File: 2-index.html

* **Objective**: Create nested grids for more advanced layouts.

- Outer grid: grid grid-cols-2 gap-4
- Nested grids with different colors:
    - Blue nested grid: bg-blue-200 grid grid-cols-2 p-4 gap-2
    - Red nested grid: bg-red-200 grid grid-cols-2 p-4 gap-2
- Each nested cell uses increasing color shades (bg-blue-400, bg-blue-500, etc).

### 🟨 3. Flexbox Basics - Navigation Bar
#### File: 3-nav_index.html

* **Objective**: Build a responsive Flexbox navigation bar.

### 🟥 4. Responsive Flexbox Layout
#### File: 4-flexbox_index.html
* **Objective**: Use Flexbox for a sidebar + content layout.
    - main → flex
    - aside → w-1/3 bg-gray-300 p-4
    - section → w-2/3 bg-gray-500 p-4
On small screens, the layout stacks vertically.

### 🟧 5. Combining Grid + Flexbox
#### File: 5-gridflex_index.html

* **Objective**: Combine CSS Grid and Flexbox for a multi-section layout.
    - main → grid grid-cols-1 lg:grid-cols-3 gap-4 mt-4
    - min-h-screen
    - section → lg:col-span-2 flex

### 🖼 6. Responsive Image Gallery
#### File: 6-imageGallery.html

* **Objective**: Create an image gallery with CSS Grid.
- 3-column layout for larger screens.
- On smaller screens → grid-cols-1.



