👗 Boutique Book Pro
Elegant Management System for Fashion Designers & Tailors
Boutique Book Pro is a lightweight, single-page application (SPA) designed to help boutique owners, fashion designers, and tailors manage orders, track measurements, calculate costs, and generate invoices with style and ease.

Built with a "Glassmorphism" UI and a vibrant floral aesthetic, it combines beauty with powerful business logic.

✨ Key Features
📊 Dashboard & Analytics
Real-time Financials: Track Total Revenue, Net Profit, and overall Profit Margin instantly.

Urgent Alerts: Automatic detection of orders due within 3 days or overdue.

Cost Breakdown: Visual progress bars analyzing spending on Fabric, Labor, Dyeing, and Handwork.

✂️ Order Management
Kanban-style Status: Track orders from Pending → Processing → Completed → Delivered.

Detailed Costing: Built-in calculator for fabric consumption, dyeing, labor, and packing costs to determine exact profit per order.

Measurement Log: Standardized fields for body measurements (Length, Bust, Waist, etc.).

Visual Reference: Upload and compress design sketches or fabric photos directly to the order card.

🤝 Client Communication
PDF Invoicing: One-click generation of professional PDF invoices using jsPDF.

WhatsApp Integration: Direct deep-link to WhatsApp with pre-filled invoice summaries for customers.

Data Export: Export all order data to CSV for external accounting.

🔐 Security & Tech
Google Authentication: Secure login via Firebase Auth.

Cloud Sync: All data is stored in Firebase Realtime Database.

Responsive Design: Fully mobile-friendly UI using Tailwind CSS.

🛠️ Tech Stack
Frontend: HTML5, Vanilla JavaScript (ES6+)

Styling: Tailwind CSS (via CDN)

Backend: Firebase (Auth & Realtime Database)

Libraries:

jsPDF & jspdf-autotable (PDF Generation)

Google Fonts (Playfair Display & Inter)

🚀 Installation & Setup
Since this is a serverless web app using CDN links, you do not need npm or node. However, you must configure your own Firebase project for the backend to work.

Step 1: Clone or Download
Download the index.html file containing the code.

Step 2: Create a Firebase Project
Go to the Firebase Console.

Click Add project and follow the setup steps.

Once created, go to Project Settings (gear icon) > General.

Scroll down to "Your apps" and select the </> (Web) icon.

Register the app (you can ignore Firebase Hosting for now).

Copy the firebaseConfig object provided.

Step 3: Enable Authentication & Database
Authentication: Go to Build > Authentication > Sign-in method. Enable Google.

Database: Go to Build > Realtime Database. Click Create Database.

Rules: Set your database rules to allow authenticated users to read/write their own data:

JSON

{
  "rules": {
    "users": {
      "$uid": {
        ".read": "$uid === auth.uid",
        ".write": "$uid === auth.uid"
      }
    }
  }
}
Step 4: Update Configuration
Open index.html in a text editor. Look for the firebaseConfig variable (around line 520) and replace it with your own keys:

JavaScript

// REPLACE THIS BLOCK WITH YOUR OWN CONFIG FROM FIREBASE CONSOLE
const firebaseConfig = {
    apiKey: "YOUR_API_KEY",
    authDomain: "YOUR_PROJECT_ID.firebaseapp.com",
    projectId: "YOUR_PROJECT_ID",
    storageBucket: "YOUR_PROJECT_ID.firebasestorage.app",
    messagingSenderId: "YOUR_SENDER_ID",
    appId: "YOUR_APP_ID"
};
Step 5: Run
Simply open index.html in any modern web browser (Chrome, Edge, Firefox, Safari).

📖 Usage Guide
Login: Click "Sign in with Google" to access your private dashboard.

New Order: Click the "New Order" button.

Enter Customer details.

Input measurement data.

Use the Fabric Calculator (Price/m * Meters) to estimate costs.

Set the Selling Price to see your estimated profit immediately.

Upload a photo of the dress design.

Manage: Use the Tabs (Overview, Orders, Insights) to navigate.

Invoice: In the Orders tab, click the 📄 icon to download a PDF or the WhatsApp icon to send a chat.

🎨 Customization
Background: The floral background is an SVG data URI in the CSS. You can replace the .floral-bg background-image property with any image URL.

Colors: The app uses Tailwind's fuchsia, violet, and emerald color palettes. You can Find & Replace fuchsia with blue or rose in the HTML to change the primary theme color globally.

📄 License
This project is open-source and available under the MIT License. You are free to modify and use it for personal or commercial purposes.

Created with ❤️ for the Fashion Industry.
