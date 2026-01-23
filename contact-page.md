📩 Contact Page – Complete Implementation (React Way)
🧠 What We’re Building

A Contact page with:

Name, Email, Message fields

Client-side validation

Smooth animations

Optional email sending (future-ready)

SPA routing (no page reload)

Route:

/contact

🧱 Tech Used (No new heavy tools)

React 18

React Router DOM

Framer Motion (already added)

CSS (Flexbox)

Optional: EmailJS (future)

📁 Folder Structure (Updated)
src/
├── pages/
│   ├── Home.jsx
│   ├── About.jsx
│   ├── Portfolio.jsx
│   └── Contact.jsx   ✅
│
├── components/
│   ├── Navbar.jsx
│   ├── ProjectCard.jsx
│
├── animations/
│   └── variants.js

🧭 Routing – Add Contact Page
routes/AppRoutes.jsx
import Contact from "../pages/Contact";

<Route path="/contact" element={<Contact />} />


✅ Route added
✅ SPA navigation preserved

🔗 Navbar – Add Contact Link
components/Navbar.jsx
<li>
  <NavLink to="/contact">Contact</NavLink>
</li>


Now your menu has:

Home

About

Portfolio

Contact

🎨 Contact Page Design Philosophy

✔ Clean
✔ Minimal
✔ Easy to scan
✔ Mobile-first

Layout:

Page title

Short intro text

Form centered on page

🎬 Contact Page Animations (IMPORTANT)
Animations Used

Page fade + slide on load

Form fields staggered entry

Button hover animation

Why?

Makes form feel alive

Guides user attention

Professional UX

🧩 Contact Page Component (Key Example)
pages/Contact.jsx
import { motion } from "framer-motion";
import { useState } from "react";
import { pageVariants, fadeUpVariants } from "../animations/variants";

function Contact() {
  const [formData, setFormData] = useState({
    name: "",
    email: "",
    message: "",
  });

  const handleChange = (e) => {
    setFormData({ ...formData, [e.target.name]: e.target.value });
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    alert("Message sent (demo)");
  };

  return (
    <motion.section
      className="page contact"
      variants={pageVariants}
      initial="hidden"
      animate="visible"
      exit="exit"
    >
      <motion.h2 variants={fadeUpVariants}>Contact Me</motion.h2>

      <motion.p variants={fadeUpVariants}>
        Feel free to reach out for projects or collaborations.
      </motion.p>

      <motion.form
        onSubmit={handleSubmit}
        className="contact-form"
        variants={fadeUpVariants}
      >
        <input
          type="text"
          name="name"
          placeholder="Your Name"
          onChange={handleChange}
          required
        />

        <input
          type="email"
          name="email"
          placeholder="Your Email"
          onChange={handleChange}
          required
        />

        <textarea
          name="message"
          placeholder="Your Message"
          onChange={handleChange}
          required
        />

        <motion.button whileHover={{ scale: 1.05 }}>
          Send Message
        </motion.button>
      </motion.form>
    </motion.section>
  );
}

export default Contact;

⚛️ React Hooks Used (Why & Where)
useState

Used for:

Form input state

Controlled components

Validation-ready logic

Why controlled inputs?

Predictable state

Easy validation

Easy API integration later

🎬 Animation Variants (Reminder)

Your existing variants.js supports this page without changes:

pageVariants → page transition

fadeUpVariants → text & form animation

Reusable ✔
Scalable ✔

📱 Responsive Behavior

Form stacks vertically

Inputs full width

Button easy to tap

Mobile-friendly by default
