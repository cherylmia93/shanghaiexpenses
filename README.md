Digital Trip Ledger & Bill Splitter 🌏💸

A simplified, high-visibility financial ledger designed to visualize Splitwise CSV exports. This tool helps groups (especially those who find standard spreadsheets hard to read) understand exactly who paid what and who owes whom with zero confusion.

🌟 Features

1. Visual Ledger

Color-Coded Columns: Each person gets a distinct color column.

Clear Status Indicators: Replaces confusing + / - signs with clear "GETS" (Green) and "OWE" (Grey) indicators.

Auto-Categorization: Automatically groups generic items.

Didi/Uber items go to a "Transport" section.

Food/Dinner items go to "Dining Out".

General items are cleaned up into "Tickets" or specific categories.

Smart Text Formatting: Cleans up messy descriptions (e.g., converts "didi to airport ( diana )" to "Didi To Airport (Diana)").

2. "Who Pays Who" (Settlement Engine)

Simplified Debts: Uses a custom algorithm to calculate the fewest number of transfers required to settle up.

Priority Settlement: Unlike standard splitters, this engine prioritizes the Largest Creditor.

Example: If Cheryl paid the most, the algorithm ensures debtors pay Cheryl directly (e.g., Alex pays Cheryl $1400) rather than splitting payments between multiple people.

Personalized Filters: Filter the view to see only payments involving a specific person.

3. Export Options

Print-Friendly View: A "Save as PDF" button that strips away UI elements, sets landscape mode, and formats the ledger for A4 printing.

Python/LaTeX Generator: Includes a backend script (generate_ledger.py) to generate professional-grade PDF reports via LaTeX.

🚀 How to Run (React App)

This project is built as a single-file React component for ease of portability.

Prerequisites

Node.js installed.

Installation Steps

Create a generic React app (using Vite is recommended for speed):

npm create vite@latest trip-ledger -- --template react
cd trip-ledger
npm install


Install Dependencies:
This project uses lucide-react for icons and standard CSS/Tailwind.

npm install lucide-react


Setup Tailwind CSS:
Follow standard Tailwind installation instructions.

Install tailwind: npm install -D tailwindcss postcss autoprefixer && npx tailwindcss init -p

Add paths to tailwind.config.js.

Add directives to index.css.

Add the Code:

Copy the contents of DigitalLedger.jsx into your src/App.jsx (or src/App.js) file.

Run:

npm run dev


🐍 Advanced: Python PDF Generator

If you prefer a programmatic PDF generation (non-web), a Python script is included.

Ensure you have Python installed.

Install a LaTeX distribution (like MiKTeX or TeX Live) to compile the .tex output.

Run the script:

python generate_ledger.py


This reads the CSV and outputs a .tex file which can be compiled into a PDF.

📂 File Structure

DigitalLedger.jsx - The main React application code.

generate_ledger.py - Python script for calculating debts and generating LaTeX.

Shanghai_Trip_Ledger.tex - The LaTeX template used by the python script.

🤝 Logic Explanation

Why doesn't this match Splitwise exactly?

Splitwise often prioritizes clearing smallest debts first or maintaining specific friend-links. This tool uses a "Largest Creditor First" approach.

It identifies the person owed the most money (e.g., Cheryl).

It identifies the people who owe the most money (e.g., Alex, Timmy).

It matches them directly.

Result: The main payer collects full checks from the big spenders, while smaller debts are settled among the remaining group. This reduces the number of small, fragmented transactions.

📝 License

Free to use for your own holiday trips!
