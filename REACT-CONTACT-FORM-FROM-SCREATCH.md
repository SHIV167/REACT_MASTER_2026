import React from "react";
import "./ContactForm.css";

export default function ContactForm() {
  return (
    <div className="page">
      <form className="form">
        <h2 className="title">Contact Us</h2>

        <div className="row">
          <div className="field">
            <label>Name</label>
            <input type="text" placeholder="Your name" />
          </div>

          <div className="field">
            <label>Email</label>
            <input type="email" placeholder="you@example.com" />
          </div>
        </div>

        <div className="field">
          <label>Message</label>
          <textarea rows="4" placeholder="Write your message..." />
        </div>

        <button type="submit">Send Message</button>
      </form>
    </div>
  );
}

/* ContactForm.css */

.page {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #f2f2f2;
}

.form {
  background: #fff;
  padding: 24px;
  width: 100%;
  max-width: 420px;
  display: flex;
  flex-direction: column;
  gap: 16px;
  border-radius: 12px;
}

.title {
  text-align: center;
  margin-bottom: 8px;
}

.row {
  display: flex;
  gap: 12px;
}

.field {
  display: flex;
  flex-direction: column;
  flex: 1;
}

label {
  font-size: 14px;
  margin-bottom: 4px;
}

input,
textarea {
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 8px;
}

button {
  padding: 10px;
  border: none;
  border-radius: 8px;
  background: #000;
  color: #fff;
  cursor: pointer;
}
