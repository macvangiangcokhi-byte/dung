# Base44 Setup Notes

## Project Overview
This is a static HTML/CSS/JS online exam system (THPT Nguyễn Thị Duệ) for a Vietnamese high school. It uses Firebase (Auth + Firestore) via CDN scripts — no backend server, no build step.

## Structure
- `public/index.html` — redirects to `student.html`
- `public/teacher.html` — teacher/admin page (question bank, exam rooms, grading)
- `public/student.html` — student exam-taking page
- `public/assets/` — static assets (logo placeholder)
- All JS libraries (Tailwind, Firebase, pdf.js, mammoth, xlsx, lucide) are loaded via CDN — no npm install needed

## Running
- Served as static files by nginx (docker-compose.base44.yml) on port 3000
- No build step, no dependencies to install
- Firebase config (apiKey, projectId, etc.) is embedded directly in the HTML files — these are public client-side keys; security is controlled by Firestore rules and Firebase Auth
- No external secrets required

## Verification
- `curl http://localhost:3000/index.html` → 200 (redirects to student.html)
- `curl http://localhost:3000/teacher.html` → 200
- `curl http://localhost:3000/student.html` → 200
- The app requires a live Firebase project (saodo-exam) with Auth and Firestore enabled for full functionality
