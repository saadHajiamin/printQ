#PrintQ — Skip the Print Shop Line

PrintQ is a browser-first print-shop queue and rush-hour management prototype built for Vibesprint 1.0 (OWASP NIE). It eliminates physical bottlenecks at campus and local print shops by giving customers self-service document configuration with live token tracking, while giving shop staff a real-time queue with dynamic ETA math and urgent-override controls.

30-Second Judge Walkthrough

Open the App: Open printq.html directly in any modern browser. Click Menu (or use the top navigation bar) to switch between Customer and Staff views.

Submit a Print Job (Customer View):

Click Choose a file to select any local PDF, DOCX, PPTX, image, or text file (PrintQ reads the page count automatically in-browser without uploading anything), or manually enter a document name and page count.

Choose Colour (B&W / Full colour), Paper size (A4 / A3), Finishing (Staple / Spiral bind), and Copies.

Click Print my document to receive a live token (e.g., P004) with a real-time countdown and 4-stage progress tracker.

Manage the Queue (Staff View):

Switch to Staff in the top navigation bar to see your newly submitted job alongside pre-seeded sample jobs.

Advance jobs through Start printing → Mark ready → Collected, or reorder queued items using the up/down arrows.

Test the Rush-Hour & Urgent Override Twist:

Toggle Urgent on any queued job (or approve a customer's priority request).

A confirmation modal calculates and displays the exact minute-by-minute delay impact on downstream customers and requires explicit staff acknowledgment before reprioritizing the queue.

Key Features

Client-Side File & Page Inspector: Parses page counts locally in the browser for PDFs, Word documents (.docx), PowerPoint decks (.pptx), TIFFs, images, and plain text files—zero server uploads required.

Dynamic Rush-Hour Wait-Time Engine: Calculates realistic ETAs based on page counts, copy counts, colour vs. B&W print speeds, A3 speed multipliers, collation/finishing times, and printer mode-switching overhead (colour/paper size changeovers).

Urgent Priority Gatekeeper: Prevents unfair line-jumping by calculating the exact delay added to every other waiting customer and requiring staff confirmation before moving a job to the front.

Cross-Tab Live Sync: Uses localStorage and browser storage events so opening Customer in one browser tab and Staff in another updates both views in real time.

Zero-Dependency Glassmorphism UI: Built in a single self-contained HTML file with Dark/Light mode support, Web Audio pickup chimes, and responsive layouts.

Zero-Secret Setup

No build tools, package managers, API keys, logins, or backend servers are required:

Download or clone this repository.

Double-click printq.html (or rename to index.html for GitHub Pages / Vercel / Netlify) to launch it immediately in your browser.

Pre-Loaded Demo Data

On first launch, PrintQ seeds three realistic jobs (P001–P003) across Printing and Queued states so queue depth, rush-hour indicators, and urgent-delay math are immediately testable.

To reset demo data: Open browser DevTools (F12) → Application → Local Storage → clear printq_v3 and refresh the page.

Known Limitations & Privacy Note

Local-Only Persistence: All queue state is stored strictly in the browser's localStorage and sessionStorage. No files, user names, or job metadata ever leave your device.

Simulated Hardware Spooling: Advancing statuses simulates physical printer progress and payment collection without connecting to hardware drivers or payment gateways.
