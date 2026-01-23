✅ STEP 1: Create Project
npm create vite@latest modern-portfolio -- --template react
cd modern-portfolio
npm install
npm install react-router-dom
npm run dev

✅ STEP 2: FINAL PROJECT STRUCTURE (COPY THIS)
modern-portfolio/
│
├── public/
│
├── src/
│   ├── assets/
│   │   └── profile.png
│   │
│   ├── components/
│   │   ├── Navbar.jsx
│   │   └── ProjectCard.jsx
│   │
│   ├── pages/
│   │   ├── Home.jsx
│   │   ├── About.jsx
│   │   └── Portfolio.jsx
│   │
│   ├── data/
│   │   └── projects.js
│   │
│   ├── routes/
│   │   └── AppRoutes.jsx
│   │
│   ├── styles/
│   │   └── global.css
│   │
│   ├── App.jsx
│   ├── main.jsx
│   └── index.css
│
├── package.json
├── vite.config.js
└── index.html

✅ STEP 3: FILE CONTENTS (IMPORTANT)
src/main.jsx
import React from "react";
import ReactDOM from "react-dom/client";
import { BrowserRouter } from "react-router-dom";
import App from "./App";
import "./styles/global.css";

ReactDOM.createRoot(document.getElementById("root")).render(
  <BrowserRouter>
    <App />
  </BrowserRouter>
);

src/App.jsx
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

src/routes/AppRoutes.jsx
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

src/components/Navbar.jsx
import { NavLink } from "react-router-dom";

function Navbar() {
  return (
    <nav className="navbar">
      <h2>Shiv</h2>
      <ul>
        <li><NavLink to="/">Home</NavLink></li>
        <li><NavLink to="/about">About</NavLink></li>
        <li><NavLink to="/portfolio">Portfolio</NavLink></li>
      </ul>
    </nav>
  );
}

export default Navbar;

src/pages/Home.jsx
function Home() {
  return (
    <section className="page">
      <h1>Hello, I'm Shiv 👋</h1>
      <p>Frontend Developer | React</p>
    </section>
  );
}

export default Home;

src/pages/About.jsx
function About() {
  return (
    <section className="page">
      <h2>About Me</h2>
      <p>
        I am a React developer focused on clean UI, performance,
        and real-world applications.
      </p>
    </section>
  );
}

export default About;

src/pages/Portfolio.jsx
import projects from "../data/projects";
import ProjectCard from "../components/ProjectCard";

function Portfolio() {
  return (
    <section className="page">
      <h2>My Projects</h2>

      <div className="grid">
        {projects.map(project => (
          <ProjectCard key={project.id} {...project} />
        ))}
      </div>
    </section>
  );
}

export default Portfolio;

src/components/ProjectCard.jsx
function ProjectCard({ title, description, tech }) {
  return (
    <div className="card">
      <h3>{title}</h3>
      <p>{description}</p>
      <div className="tags">
        {tech.map((item, i) => (
          <span key={i}>{item}</span>
        ))}
      </div>
    </div>
  );
}

export default ProjectCard;

src/data/projects.js
const projects = [
  {
    id: 1,
    title: "Portfolio Website",
    description: "Modern React portfolio",
    tech: ["React", "Vite", "Router"],
  },
  {
    id: 2,
    title: "E-commerce UI",
    description: "Shopping UI with React",
    tech: ["React", "CSS"],
  },
];

export default projects;

src/styles/global.css
body {
  margin: 0;
  font-family: Arial, sans-serif;
}

.navbar {
  display: flex;
  justify-content: space-between;
  padding: 15px 30px;
  background: #111;
}

.navbar h2 {
  color: white;
}

.navbar ul {
  display: flex;
  list-style: none;
  gap: 20px;
}

.navbar a {
  color: white;
  text-decoration: none;
}

.page {
  padding: 40px;
}

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
}

.card {
  padding: 20px;
  border: 1px solid #ddd;
}

.tags span {
  margin-right: 10px;
  font-size: 12px;
  color: #555;
}

✅ STEP 4: PUSH TO GITHUB 🚀
git init
git add .
git commit -m "Initial modern portfolio"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/modern-portfolio.git
git push -u origin main

✅ STEP 5: DEPLOY
🔹 Netlify / Vercel

Build command: npm run build

Output folder: dist

🔹 GitHub Pages
