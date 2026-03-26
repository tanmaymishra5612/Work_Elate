A lightweight, extensible spreadsheet application inspired by tools like Excel and Google Sheets.
Built as part of an evaluation task, this project focuses on data manipulation, performance, and clean architecture.

📌 Features
🔹 Column Sorting & Filtering
Toggle sorting: Ascending → Descending → None
Sorting works on computed (formula) values
Excel-like dropdown controls in column headers
Filtering hides rows without deleting data
Sorting is implemented as a view-layer transformation (non-destructive)

🔹 Multi-Cell Copy & Paste
Paste directly from Excel / Google Sheets
Supports multi-row and multi-column tabular data
Uses standard shortcuts:
Ctrl + C → Copy
Ctrl + V → Paste
Internal copy-paste between cells
Undo support for paste operations

🔹 Local Storage Persistence
Auto-saves spreadsheet state to localStorage
Restores data on page reload
Persists:
Cell values
Formulas
Styles
Grid structure
Debounced saving for better performance
Handles storage errors gracefully

🧠 Key Design Decisions
Separation of raw and computed values
Ensures formulas remain intact while enabling accurate sorting/filtering.
View-layer sorting
Sorting does not mutate the underlying dataset, preserving formula references.
Non-destructive filtering
Rows are hidden instead of removed, ensuring data integrity.
Modular architecture
Logic is separated into reusable utilities (sorting, formula parsing, clipboard handling).

🏗️ Project Structure
src/
├── components/     # UI components (Grid, Cell, Toolbar)
├── utils/          # Core logic (formula, sorting, clipboard)
├── hooks/          # Custom React hooks
├── store/          # State management
└── App.tsx

⚙️ Tech Stack
React.js – UI development
TypeScript – Type safety and maintainability
Browser Clipboard API – Copy/Paste functionality
Local Storage API – Data persistence

🧪 Edge Cases Handled
Invalid formulas → returns "ERROR"
Sorting mixed data types (numbers + strings)
Empty cell references in formulas
Large clipboard paste handling
Corrupted local storage recovery

▶️ Getting Started
1️⃣ Clone the repository
git clone https://github.com/your-username/spreadsheet-app.git
cd spreadsheet-app
2️⃣ Install dependencies
npm install
3️⃣ Run the app
npm run dev

📈 Future Improvements
Formula dependency graph (auto-update dependent cells)
Keyboard navigation (arrow key support)
Advanced filtering conditions
Performance optimization for large datasets
Cell range selection

🎯 Objective

This project was built to demonstrate:

Strong problem-solving ability
Clean and scalable code structure
Attention to UX and product-level details
