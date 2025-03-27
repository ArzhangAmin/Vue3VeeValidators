# 🔐 Vue 3 Authentication Forms

![Vue 3](https://img.shields.io/badge/Vue.js-3.x-4FC08D?logo=vuedotjs)
![VeeValidate](https://img.shields.io/badge/VeeValidate-4.x-FF4785)
![Yup](https://img.shields.io/badge/Yup-Validation-FF6B6B)
![Bootstrap](https://img.shields.io/badge/Bootstrap-5.x-7952B3)

A complete login and registration system built with Vue 3's Options API featuring robust form validation and animated UI transitions.

## ✨ Features

- **Dual-form system** (Login + Registration) with flip animation
- **Schema-based validation** using Yup
- **Real-time error feedback** with VeeValidate
- **Responsive design** powered by Bootstrap 5
- **Form persistence** for better UX

## 🛠 Tech Stack

| Technology | Purpose |
|------------|---------|
| Vue 3 (Options API) | Core framework |
| VeeValidate v4 | Form validation |
| Yup | Validation schemas |
| Bootstrap 5 | UI components/layout |
| CSS3 | Animations/transitions |

## 🚀 Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/vue3-auth-forms.git


2. Install dependencies:
npm install

3. Run development server:
npm run dev


📂 Project Structure
src/
├── components/
│   ├── LoginForm.vue      # Login form with validation
│   └── RegisterForm.vue   # Registration form with schema
├── App.vue                # Main container with flip animation
└── main.js                # VeeValidate configuration


🔍 Validation Examples
// Registration schema
const registerSchema = {
  password: string()
    .required()
    .min(6),
  confirmPassword: string()
    .required()
    .oneOf([ref('password')], "Passwords must match")
};


📝 Customization
Edit validation schemas: Modify *.vue files in components/

Change styles: Edit the CSS in each component

Add new fields: Extend the Yup schemas and template sections

📜 License
MIT © [ArzhangAmin]

