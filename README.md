# SpreadsheetApp

A modern spreadsheet web application built with **React** and **Vite**, designed to replicate key spreadsheet behaviors similar to Excel and Google Sheets.

This project demonstrates spreadsheet core functionality including **column sorting, filtering, clipboard operations, and persistent storage**, implemented with a strong focus on **clean architecture, performance, and UX**.

---

# Features

## Task 1 — Column Sort & Filter

### Column Sorting

- Three-state sorting:
  - Ascending
  - Descending
  - None (reset)

- Sorting works on **computed values**, including formula results.
- Sorting only affects the **view layer**, not the underlying data.

This ensures:

- Formulas continue referencing original cell positions.
- Data integrity remains intact.

### Column Filtering

- Excel-like dropdown filters in column headers.
- Multiple value filtering supported.
- Filtering hides rows without deleting them.
- Filters are fully reversible.

### UX Details

- Visual indicators for sorting direction.
- Filter icon highlights when active.
- Sorting and filtering can be combined.

---

## Task 2 — Multi-Cell Copy & Paste (Clipboard Integration)

### Clipboard Support

The spreadsheet integrates with the browser Clipboard API to support:

- **Ctrl+C** — Copy selected cells
- **Ctrl+V** — Paste from Excel / Google Sheets
- **Ctrl+Z** — Undo pasted changes

### Multi-Cell Paste

Handles tab-separated clipboard data including:

- Multi-row pastes
- Multi-column pastes
- Large data blocks

Example supported clipboard format:

10 20 30
40 50 60

### Copy Behavior

- Copies **computed values** instead of formulas.
- Maintains spreadsheet layout when pasting.
- Supports **internal copy-paste between cells**.

### Undo Support

All paste operations are **undoable**, ensuring users can safely revert accidental changes.

---

## Task 3 — Local Storage Persistence

Spreadsheet data is automatically saved to **local storage**.

### Auto Save

- Debounced saving (500ms)
- Prevents excessive storage writes
- Saves only meaningful state changes

### Persisted Data

The following spreadsheet state is saved:

- Cell values
- Formulas
- Cell styles
- Grid dimensions

### Non-Persisted Data

The following are intentionally not stored:

- Undo / redo history
- Current selection
- Temporary UI state

### Error Handling

- Safe parsing of stored data
- Automatic reset if corrupted data is detected
- Storage limit protection

---

# Project Structure

```
SpreadsheetApp/
├── src/
│   ├── App.jsx
│   ├── App.css
│   ├── main.jsx
│   ├── index.css
│   ├── assets/
│   └── engine/
│       └── core.js
├── public/
├── package.json
├── vite.config.js
├── eslint.config.js
└── README.md
```

The **engine layer** separates spreadsheet logic from UI components, improving maintainability and scalability.

---

# Technologies Used

- **React** — UI framework
- **Vite** — Fast development environment
- **ESLint** — Code quality and linting
- **JavaScript (ES2020+)**
- **CSS**

---

# Getting Started

## Prerequisites

Make sure the following are installed:

- Node.js (v18 or higher)
- npm or yarn
- Git

---

## Clone Repository

```
git clone https://github.com/tauhidst07/spreadhsheet.git
cd SpreadsheetApp
```

---

## Install Dependencies

```
npm install
```

or

```
yarn install
```

---

## Run Development Server

```
npm run dev
```

Application runs at:

http://localhost:5173

---

## Build for Production

```
npm run build
```

Build files will be generated inside:

```
dist/
```

---

## Preview Production Build

```
npm run preview
```

---

## Run Linter

```
npm run lint
```

---

# Browser Support

This application supports modern browsers:

- Chrome
- Firefox
- Safari
- Edge

All browsers supporting **ES2020+ JavaScript**.

---

# Development Workflow

1. Create a new branch

```
git checkout -b feature/feature-name
```

2. Run lint checks

```
npm run lint
```

3. Commit changes

```
git commit -m "Describe your change"
```

4. Push to repository and open a Pull Request

---

# Future Improvements

Potential enhancements include:

- Formula engine with advanced functions
- Drag-to-fill cell values
- Keyboard navigation
- Virtualized grid for large datasets
- Column resizing
- Row grouping

---

# License

This project is created for evaluation purposes as part of the **AI Native Office Internship task**.
