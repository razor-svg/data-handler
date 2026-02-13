# data-handler
Responsive dashboard for the Moroccan market with a client-side SQL engine. Filters JSON sales data (MAD) using vanilla JS. Demonstrates filter, map, and reduce methods for dynamic rendering and KPI calculation. No database required.




🇲🇦 Moroccan Sales Dashboard & Lightweight SQL Engine
A responsive, single-page web dashboard designed for the local market, featuring a custom-built, browser-based SQL simulation engine.

This project demonstrates advanced manipulation of JSON datasets using vanilla JavaScript, specifically focusing on Array.prototype methods (map, filter, reduce, sort) and Regular Expressions to parse and execute SQL-like queries without a backend database.

Status
Tech
License

📋 Overview
This dashboard visualizes sales data for Moroccan clients, including transaction amounts in MAD (Moroccan Dirham) and major cities (Casablanca, Rabat, Marrakech, etc.).

The core feature is the SQL Query Bar, which allows users to filter the data dynamically using standard SQL syntax (e.g., SELECT * WHERE ville = 'Casablanca' AND montant > 1000).

✨ Key Features
Interactive KPI Dashboard: Real-time calculation of Total Revenue, Average Basket Size, and Top Selling City using reduce().
Custom SQL Parser: A lightweight engine that interprets SELECT, WHERE, AND, and comparison operators (=, >, <, >=, <=, !=) using Regex.
Dynamic Data Table:
Rendering: Uses map() to transform JSON objects into HTML table rows.
Sorting: Client-side sorting functionality using sort().
Responsive Design: A modern UI with a sidebar layout, optimized for desktop and mobile, featuring a color palette inspired by the Moroccan flag.
🛠️ Technical Implementation
1. Data Manipulation (JavaScript Array Methods)
The project strictly uses native JavaScript methods to handle the dataset:

filter(): Used within the SQL engine to subset data based on user conditions (e.g., filtering by City or Status).
map(): Used to iterate over the filtered dataset and generate HTML DOM elements (table rows) dynamically.
reduce(): Used to aggregate data for the KPI cards (summing revenue, counting orders per city).
sort(): Implements the table column sorting logic (ascending/descending).
2. The SQL Simulation Engine
Since there is no backend database, a custom parser was built to handle text input:

Input Parsing: The input string is normalized and split by keywords (SELECT, WHERE, AND).
Regex Matching: Regular expressions identify column names, operators, and values (handling both strings like 'Casablanca' and numbers like 5000).
Execution: The parsed conditions are converted into JavaScript logic and applied to the raw JSON array.
3. UI/UX
Semantic HTML: Clean structure using <aside>, <main>, <section>.
CSS Grid & Flexbox: Used for the KPI card layout and the main dashboard structure.
No External Libraries: Pure vanilla JS (no jQuery, no React).
🚀 How to Run
Clone this repository.
Open index.html (or the HTML file provided) in any modern web browser.
No build tools or servers are required.
💻 SQL Syntax Guide
The simulator supports the following syntax patterns:

Select All: SELECT *
Simple Filter: SELECT * WHERE ville = 'Rabat'
Numeric Comparison: SELECT * WHERE montant > 3000
Multiple Conditions: SELECT * WHERE ville = 'Tanger' AND status = 'Payé'
Inequality: SELECT * WHERE status != 'Annulé'
📊 Sample Data
The dashboard comes pre-loaded with a JSON dataset representing local orders:

Cities: Casablanca, Rabat, Tanger, Agadir, Marrakech, Fès, Oujda.
Currency: MAD (Moroccan Dirham).
Status: Payé, En attente, Annulé.
📝 License
This project is open source and available for educational purposes.
