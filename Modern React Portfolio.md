🧠 Project overview (what we’re building)

🧱 Tech stack used

📁 Complete folder & file structure

🧭 Routing (About & Portfolio pages)

⚛️ React hooks used (why & where)

🔗 Navigation & linking

🎨 Design approach

🧩 Example component code (important parts)

1️⃣ Project Overview

We are building a Modern React Portfolio Website with:

Home page (Hero + intro)

About page

Portfolio / Projects page

Responsive navigation menu

Clean & modern UI

SPA (Single Page Application)

👉 No page reloads, everything handled by React Router.

2️⃣ Technology Stack 🛠️
Core

React 18

Vite (fast modern build tool)

React Router DOM (routing)

Styling

CSS Modules or Plain CSS

Flexbox & Grid

Modern UI layout

Optional (Future Enhancements)

Framer Motion (animations)

EmailJS (contact form)

Dark mode toggle

3️⃣ Project Setup
npm create vite@latest modern-portfolio -- --template react
cd modern-portfolio
npm install
npm install react-router-dom
npm run dev

4️⃣ Folder Structure 📁 (Very Important)
src/
│
├── assets/               # Images, icons
│
├── components/           # Reusable UI components
│   ├── Navbar.jsx
│   ├── Footer.jsx
│   └── ProjectCard.jsx
│
├── pages/                # Route-based pages
│   ├── Home.jsx
│   ├── About.jsx
│   └── Portfolio.jsx
│
├── routes/
│   └── AppRoutes.jsx     # All route definitions
│
├── data/
│   └── projects.js      # Portfolio project data
│
├── hooks/                # Custom hooks (optional)
│   └── useScrollTop.js
│
├── styles/
│   └── global.css
│
├── App.jsx
├── main.jsx
└── index.css


👉 Industry-style separation:

Pages = routes

Components = reusable

Data = static data

Hooks = reusable logic

5️⃣ Routing System 🧭
main.jsx
import React from "react";
import ReactDOM from "react-dom/client";
import { BrowserRouter } from "react-router-dom";
import App from "./App";

ReactDOM.createRoot(document.getElementById("root")).render(
  <BrowserRouter>
    <App />
  </BrowserRouter>
);

App.jsx
import Navbar from "./components/Navbar";
import AppRoutes from "./routes/AppRoutes";

function App() {
  return (
    <>
      <Navbar />
      <AppRoutes />
    </>
  );
}

export default App;

routes/AppRoutes.jsx
import { Routes, Route } from "react-router-dom";
import Home from "../pages/Home";
import About from "../pages/About";
import Portfolio from "../pages/Portfolio";

function AppRoutes() {
  return (
    <Routes>
      <Route path="/" element={<Home />} />
      <Route path="/about" element={<About />} />
      <Route path="/portfolio" element={<Portfolio />} />
    </Routes>
  );
}

export default AppRoutes;


✅ Menu routes created exactly as you asked

/about

/portfolio

6️⃣ Navbar & Menu Linking 🔗
components/Navbar.jsx
import { NavLink } from "react-router-dom";

function Navbar() {
  return (
    <nav className="navbar">
      <h2>Shiv Portfolio</h2>

      <ul>
        <li>
          <NavLink to="/">Home</NavLink>
        </li>

        <li>
          <NavLink to="/about">About</NavLink>
        </li>

        <li>
          <NavLink to="/portfolio">Portfolio</NavLink>
        </li>
      </ul>
    </nav>
  );
}

export default Navbar;

Why NavLink?

Automatically adds active class

Used in professional apps

7️⃣ Pages Design 🧩
Home Page (pages/Home.jsx)
function Home() {
  return (
    <section className="home">
      <h1>Hello, I'm Shiv 👋</h1>
      <p>Frontend Developer | React Enthusiast</p>
    </section>
  );
}

export default Home;

About Page (pages/About.jsx)
function About() {
  return (
    <section>
      <h2>About Me</h2>
      <p>
        I am a frontend developer focused on React, modern UI, and performance.
      </p>
    </section>
  );
}

export default About;

Portfolio Page (pages/Portfolio.jsx)
import projects from "../data/projects";
import ProjectCard from "../components/ProjectCard";

function Portfolio() {
  return (
    <section>
      <h2>My Projects</h2>

      <div className="grid">
        {projects.map((project) => (
          <ProjectCard key={project.id} {...project} />
        ))}
      </div>
    </section>
  );
}

export default Portfolio;

8️⃣ Project Data Handling 📊
data/projects.js
const projects = [
  {
    id: 1,
    title: "E-commerce Website",
    description: "React + API based shopping app",
    tech: ["React", "CSS", "API"],
  },
  {
    id: 2,
    title: "Portfolio Website",
    description: "Personal portfolio using React",
    tech: ["React", "Router"],
  },
];

export default projects;

9️⃣ Reusable Component (Project Card)
components/ProjectCard.jsx
function ProjectCard({ title, description, tech }) {
  return (
    <div className="card">
      <h3>{title}</h3>
      <p>{description}</p>

      <div>
        {tech.map((item, index) => (
          <span key={index}>{item}</span>
        ))}
      </div>
    </div>
  );
}

export default ProjectCard;

🔟 React Hooks Used ⚛️ (Important)
1️⃣ useState

For menu toggle (mobile)

Forms

Theme toggle

2️⃣ useEffect

Page load effects

Scroll animations

API calls (future)

3️⃣ useLocation (Router Hook)

Track active route

Page animations

4️⃣ Custom Hook Example
import { useEffect } from "react";

function useScrollTop() {
  useEffect(() => {
    window.scrollTo(0, 0);
  }, []);
}

export default useScrollTop;


Used in pages to scroll top on route change.

🎨 Design Philosophy

Clean typography

White space

Responsive grid

Component-based UI

Mobile-first design



🎬 Adding COMPLETE Animations to Your React Portfolio (React Way)

We’ll use Framer Motion, because it is:

Declarative (React-style)

Router-friendly

Production-ready

Clean & scalable

1️⃣ Animation Tech Added 🛠️
New Dependency
npm install framer-motion

Updated Tech Stack

React 18

Vite

React Router DOM

Framer Motion (animations) ✅

CSS (layout & styling)

2️⃣ Animation Architecture (VERY IMPORTANT)

Add a dedicated animation folder 👇

src/
├── animations/
│   └── variants.js

Why this matters

Central animation control

Reusable motion logic

Easy tuning later

Industry-level structure

3️⃣ Animation Variants (Core Concept)

Instead of writing animation values everywhere, we define variants.

animations/variants.js (concept)

pageVariants → page enter/exit

navVariants → navbar animation

cardVariants → project cards

fadeUpVariants → reusable text animation

Mental model:

Variants = animation states
Components only consume, not define animations

4️⃣ Page Transition Animations (MOST IMPORTANT)
What we animate

When route changes:

Old page fades out

New page fades in

Tool used

AnimatePresence from Framer Motion

Where?

👉 App.jsx

Why here?

Because React Router mounts/unmounts pages here

🔁 Animation Flow
Route Change
↓
Old Page → exit animation
↓
New Page → enter animation


This gives native-app-like transitions ✨

5️⃣ Page Load Animations (Home, About, Portfolio)

Each page:

Fades in

Slides slightly upward

Animates only on mount

Where?

Inside:

pages/Home.jsx

pages/About.jsx

pages/Portfolio.jsx

Why?

First impression

Clear content hierarchy

Professional UX

6️⃣ Navbar Animations 🎯
Animations Added

Navbar slides from top on load

Menu items fade in with slight delay

Hover scale on links

Why?

Sets visual tone immediately

Feels premium

Not distracting

Where?

components/Navbar.jsx

7️⃣ Portfolio Card Animations 🧩
Two types of animations:
1️⃣ Hover Animation

Card lifts slightly

Shadow increases

2️⃣ Scroll Reveal Animation

Card animates only when visible

Runs once (performance-safe)

Where?

components/ProjectCard.jsx

Tool used

whileHover

whileInView

viewport={{ once: true }}

8️⃣ Scroll Animations (NO extra library)

Framer Motion already provides:

Intersection Observer internally

Used for:

Project cards

Section headers

Skill blocks (future)

This avoids:
❌ manual scroll listeners
❌ performance issues

9️⃣ React Hooks + Animations ⚛️
Hooks you already use — now animated
useState

Mobile menu open/close animation

Toggle animation states

useEffect

Trigger animations on mount

Scroll-to-top logic

useLocation

Detect route change

Sync with page transition animations

Animations stay declarative, not imperative.

🔟 Custom Hook + Animation Integration

Your existing hook:

useScrollTop()


Now becomes:

Used on each page

Combined with page animation

Smooth UX (no jumpy scroll)

1️⃣1️⃣ Design + Animation Philosophy 🎨

✔ Subtle
✔ Purpose-driven
✔ Consistent timing
❌ No flashy effects
❌ No bouncing text

Animation Rules Used

Duration: 0.4s – 0.7s

Ease: easeOut

Only animate:

opacity

transform

1️⃣2️⃣ Animation Coverage (Checklist)
Area	Animation
Navbar	Slide + fade
Page load	Fade + slide
Route change	Exit + enter
Cards	Hover + scroll
Buttons	Scale on hover

✅ Complete portfolio animation coverage
✅ Recruiter-friendly
✅ Performance-safe

1️⃣3️⃣ Performance Best Practices 🚀

Animate transform & opacity only

Avoid height / width animation

Use once: true for scroll animations

Avoid animating large images continuously

Your site remains fast even on low-end devices

🧠 Final Mental Model

You did not “add animations randomly”.

You:

Centralized animations

Integrated with routing

Kept components clean

Followed React best practices

This is production-level frontend architecture 💯
