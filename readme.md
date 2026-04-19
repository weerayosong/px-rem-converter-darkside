# Dark Side Converter | PX to REM

## Mini Project #3 | Dark Side Converter : PX to REM

### หลังจากเรียน DOM (Fetch API สุ่มโปเกมอน) ก็ได้เกิดไอเดียสนุก ๆ ขึ้น แล้วด้วยความที่มึน ๆ กับ ค่า rem <-> px ตอนเขียน Tailwind CSS ก็เลยทำแอปแปลงค่า สลับไป สลับมาไว้ใช้เองซะเลย

**ผสมกับไอเดียจากงาน Assignment ที่ให้สร้างเกม Cookie Clicker clone ที่วางไอเดียถึงสตาร์วอร์ ก็เลยแพลนไว้ว่า ถ้าทำ Assignment (mini project #2 Empire Strikes Clicker! นั่นเอง) จบแล้วมีเวลาว่างพอ จะมาทำแอปตัวนี้ต่อ แล้วก็จังหวะพอดี เป็นวันเสาร์์-อาทิตย์ พอดิบพอดี ก็เลยบู้ม! ออกมาเป็น Lord Darth Vader 😈 (ยังไม่พร้อมช้ Vite + React เพราะเวลาไม่ว่างมากพอจะแก้บัคแล้ว 555 และต้องการ launch งานด่วน ๆ โปรเจคต์นี้ก็เลยไฟล์เดียวจบ ๆ เหมือนเดิม; แต่! โปรเจคต์ต่อ ๆ ไปจะใช้ Vite กับทุกอย่างแน่นอน ไม่ว่าจะ Vanilla หรือ React 😊)**

**ตอนนี้กำลังจะเริ่มนอกลู่นอกทาง ไปสนใจ งานกราฟิกบนCSS svg, clip-path, SASS, Heroicons, Heroicons,blobmaker.app ซะแล้ว เสน่ห์ของ SVG คือมันเป็น "รูปภาพที่อธิบายด้วยโค้ด" 555**

### 😄 พอเลย ๆ กลับเส้นทาง Full Stack Dev ต่อ!

## จุดประสงค์

"Welcome to the dark side."

**สิ่งที่นำมาใช้ ก็จะมีประมาณนี้:**

- Here is a summary of the technical knowledge and core concepts applied in building the "PX to REM Converter" web app.

### 1. HTML (Structure & Accessibility)

- **Semantic HTML:** Used structural tags like `<nav>`, `<main>`, `<header>`, `<section>`, and `<footer>` to create a meaningful document outline.
- **Form Accessibility:** Used `<label>` tags linked to inputs (via `for` attributes or implicit wrapping) and added `aria-label` and `aria-hidden` to SVG icons for screen readers.
- **Inline SVG:** Implemented vector graphics directly in the HTML using `<svg>` tags and `<path>` coordinates, allowing them to be styled directly with CSS classes (like `text-sith-500`).

### 2. CSS & Tailwind (Styling & Responsive Design)

- **Tailwind Configuration via CDN:** Overrode default Tailwind settings directly in the browser using the `tailwind.config` script to inject custom fonts (Inter, JetBrains Mono) and custom color palettes (the `sith` red scale).
- **Responsive Layouts:** Utilized Tailwind's mobile-first breakpoints (e.g., `sm:`, `md:`). For example, changing a stacked layout on mobile to a side-by-side layout on desktop (`flex-col md:flex-row`).
- **Advanced UI Effects:** \* **Glassmorphism:** Achieved using `backdrop-filter: blur()`, semi-transparent background colors, and subtle borders.
    - **Glow Effects:** Used absolute positioning, `blur`, and `mix-blend-screen` to create the ambient red Sith glow behind the panel.
    - **Custom Scrollbar:** Wrote raw CSS inside `<style>` to style the WebKit scrollbar (`::-webkit-scrollbar`) to match the dark theme.
- **Interactive States:** Applied `hover:`, `focus:`, and `group-hover:` utilities to handle element transitions (e.g., making the input spinners appear only when hovering over the input block).

### 3. Vanilla JavaScript (Logic & DOM Manipulation)

- **Real-time Event Listeners:** \* `'input'`: Triggered calculations immediately as the user types, without needing a "Submit" button.
    - `'wheel'`: Intercepted the mouse scroll wheel to increment/decrement values quickly.
- **UX/Mobile Scroll Handling:** Used `document.activeElement === this` within the wheel event. This prevents the user from accidentally scrolling the numbers when they are just trying to scroll down the page on a mobile touchscreen.
- **Data Validation & Error Handling:** Used `isNaN()` to check if the user typed text instead of numbers, triggering the Darth Vader warning sequence instead of breaking the app.
- **Mathematical Precision:** Used `.toFixed(3)` to limit the floating-point output to 3 decimal places, preventing infinite decimals while maintaining enough precision for CSS rendering.
- **Dynamic UI Updates:** Manipulated CSS classes via JS (`classList.add/remove`) to show/hide the warning terminal and apply the `animate-pulse` effect temporarily using `setTimeout`.
- **Bi-directional Syncing:** Created a single function (`syncCalculations`) that knows which input triggered the change (`sourceElement`) and updates the _other_ inputs accordingly, preventing infinite loops.

### 4. General Development Principles

- **Single-File Architecture:** Combined HTML, CSS, and JS into one `.html` file without a build step, making it easy to deploy, share, or open locally.
- **Theming & "Gimmicks":** Stored theme-specific text (Vader's quotes) in a structured JavaScript object (`imperialLore`) and used `Math.random()` to cycle through them, proving that utility tools can also have personality and engaging UX.
