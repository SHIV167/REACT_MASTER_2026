🔁 Converting React (Vite) Portfolio → Next.js (App Router)

Think of this as changing the engine, not the car design 🚗
Your components, pages, and data mostly stay the same — routing & rendering change.

1️⃣ Biggest Conceptual Change (IMPORTANT)
React + Vite

Uses React Router

Routes are defined in code (Routes, Route)

Everything is client-side rendered

Next.js

Uses File-based routing

No React Router

Pages are created by folders & files

Supports Server + Client rendering

👉 Routing logic moves from JS to folder structure

2️⃣ Project Setup Difference
Before (Vite)
npm create vite@latest

After (Next.js)
npx create-next-app@latest modern-portfolio-next


You choose:

App Router ✅ (recommended)

JavaScript or TypeScript

CSS support

3️⃣ Folder Structure Conversion (KEY PART)
🔴 Old (React + Vite)
src/
 ├── pages/
 │   ├── Home.jsx
 │   ├── About.jsx
 │   └── Portfolio.jsx
 ├── routes/
 │   └── AppRoutes.jsx

🟢 New (Next.js App Router)
app/
 ├── page.js           → Home (/)
 ├── about/
 │   └── page.js       → /about
 ├── portfolio/
 │   └── page.js       → /portfolio


✅ Each folder = a route
✅ page.js is mandatory

4️⃣ What Happens to React Router?

🚫 REMOVED COMPLETELY

React Router	Next.js
<BrowserRouter>	❌ Not needed
<Routes>	❌
<Route>	❌
NavLink	❌
useLocation()	❌

➡️ Next.js handles routing automatically

5️⃣ Navigation Conversion (Navbar)
React

NavLink from react-router-dom

Active route logic built-in

Next.js

Uses next/link

Active route handled using usePathname()

Conceptually:

Links are preloaded

Navigation is faster

No full page reload

6️⃣ App Layout Concept (Very Important)
React
<App>
  <Navbar />
  <Routes />
</App>

Next.js
app/
 ├── layout.js   ← shared layout
 ├── page.js


👉 layout.js replaces App.jsx

Navbar goes into layout.js

Shared across all pages automatically

No need to re-import on every page

7️⃣ Component Reuse (No Change)

Your folders stay the same:

components/
 ├── Navbar.jsx
 ├── ProjectCard.jsx
data/
 └── projects.js


✅ 100% reusable
✅ No rewrite needed

8️⃣ React Hooks in Next.js
Hooks That Stay the Same ✅

useState

useEffect

Custom hooks

Event handlers

Hooks That Change ❗

Router hooks → Next.js navigation hooks

React Router	Next.js
useNavigate()	useRouter()
useLocation()	usePathname()
9️⃣ Client vs Server Components (New Concept)

By default:

Next.js components are Server Components

If you need:

useState

useEffect

browser APIs

👉 Add at top:

"use client";


Navbar, Portfolio grid, animations → Client Components

Static pages → Server Components

🔟 Styling Conversion
React

global.css imported in main.jsx

Next.js

globals.css imported in app/layout.js

CSS itself does not change

1️⃣1️⃣ Data Handling

Your projects.js:

Can stay as static data

Or fetched on server (bonus)

Next.js can:

Render project list at build time

Improve SEO & performance

1️⃣2️⃣ Deployment Difference
React (Vite)	Next.js
Netlify / GH Pages	Vercel (best)
Static SPA	Hybrid (SSR + SSG)
Manual SEO	Built-in SEO
1️⃣3️⃣ Mental Model Summary 🧠

You are NOT rewriting your app
You are:

✔ Removing React Router
✔ Moving routing into folders
✔ Using layout instead of App.jsx
✔ Using Next.js navigation
✔ Gaining SEO + performance

✅ When Should YOU Use Next.js?

Use Next.js if:

You want SEO

You want faster loads

You want professional portfolios

You want job-ready skills

Stick with React + Vite if:

Pure SPA

Dashboard apps

Learning phase
