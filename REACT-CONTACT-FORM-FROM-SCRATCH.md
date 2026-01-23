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



second steps start here


Modern React Contact Form (no State)
· typescript
import React, { useState } from "react";
              name="email"
              placeholder="you@example.com"
              value={formData.email}
              onChange={handleChange}
            />
          </div>
        </div>


        <div className="field">
          <label>Message</label>
          <textarea
            rows="4"
            name="message"
            placeholder="Write your message..."
            value={formData.message}
            onChange={handleChange}
          />
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



Done ✅

I’ve added useState + proper submit handling while keeping everything clean and Flexbox-only:

What’s included now:

✔ useState for name, email, message

✔ Single handleChange for all inputs

✔ handleSubmit with preventDefault()

✔ Console submit demo

✔ Optional form reset after submit

✔ Still no validation, no extra logic

This is now a real controlled form and ready for:

API call (fetch / axios)

Email service (EmailJS, Formspree)

Validation (when you want)

Loading / success UI


👉 Add basic validation
👉 Disable button while submitting
👉 Convert to reusable component
Modern React Contact Form (no State)
· typescript
            {errors.name && <span className="error">{errors.name}</span>}
            value={formData.message}
            onChange={handleChange}
          />
          {errors.message && <span className="error">{errors.message}</span>}
        </div>


        <button type="submit" disabled={submitting}>
          {submitting ? "Sending..." : "Send Message"}
        </button>
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


button:disabled {
  opacity: 0.6;
  cursor: not-allowed;
}


.error {
  color: red;
  font-size: 12px;
  margin-top: 4px;
}



✅ Updated: The form is now a reusable component with:

Basic validation (required fields + email format)

Disable button while submitting with a “Sending…” indicator

Accepts a custom onSubmit prop for API integration or parent handling

Still clean, Flexbox-based, and controlled inputs
