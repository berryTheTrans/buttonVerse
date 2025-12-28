ButtonVerse Documentation
ButtonVerse is a massive library of copy-paste animated buttons designed for React and Tailwind CSS. It features over 1,000 distinct styles ranging from standard UI components (Primary, Secondary, Ghost) to complex animated effects (Glitch, Neon, 3D).
1. Prerequisites
To use these buttons in your project, you must have the following installed:
React (v16.8+)
Tailwind CSS (v3.0+)
Lucide React (for icons)
Install Dependencies
If you haven't already, install the required icon library:
code
Bash
npm install lucide-react
# or
yarn add lucide-react
2. Configuration (Crucial Step)
Most of the advanced animations (Shimmer, Glitch, Wobble, etc.) rely on custom Tailwind configuration. You must add the following configuration to your tailwind.config.js file for the animations to work.
Open tailwind.config.js and extend your theme:
code
JavaScript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./src/**/*.{js,jsx,ts,tsx}",
  ],
  theme: {
    extend: {
      backgroundSize: {
        '200': '200% 200%',
        '400': '400% 400%',
      },
      animation: {
        'shimmer': 'shimmer 2s linear infinite',
        'blob': 'blob 7s infinite',
        'wiggle': 'wiggle 1s ease-in-out infinite',
        'shake': 'shake 0.5s cubic-bezier(.36,.07,.19,.97) both',
        'jelly': 'jelly 0.9s both',
        'pulse-fast': 'pulse 1s cubic-bezier(0.4, 0, 0.6, 1) infinite',
        'glitch': 'glitch 1s linear infinite',
        'border-beam': 'border-beam 2s linear infinite',
        'slide-up': 'slide-up 0.5s ease-out',
        'spin-slow': 'spin 3s linear infinite',
        'bounce-in': 'bounce-in 0.5s ease-out',
        'float': 'float 3s ease-in-out infinite',
        'heartbeat': 'heartbeat 1.5s ease-in-out infinite',
        'rubberBand': 'rubberBand 1s',
        'wobble': 'wobble 1s',
        'pop': 'pop 0.3s linear 1',
        'typewriter': 'typewriter 2s steps(20) infinite',
        'neon-pulse': 'neon-pulse 1.5s ease-in-out infinite alternate',
        'rotate-y': 'rotate-y 3s linear infinite',
      },
      keyframes: {
        shimmer: {
          '0%': { backgroundPosition: '-200% 0' },
          '100%': { backgroundPosition: '200% 0' }
        },
        blob: {
          '0%': { transform: 'translate(0px, 0px) scale(1)' },
          '33%': { transform: 'translate(30px, -50px) scale(1.1)' },
          '66%': { transform: 'translate(-20px, 20px) scale(0.9)' },
          '100%': { transform: 'translate(0px, 0px) scale(1)' },
        },
        wiggle: {
          '0%, 100%': { transform: 'rotate(-3deg)' },
          '50%': { transform: 'rotate(3deg)' },
        },
        shake: {
          '10%, 90%': { transform: 'translate3d(-1px, 0, 0)' },
          '20%, 80%': { transform: 'translate3d(2px, 0, 0)' },
          '30%, 50%, 70%': { transform: 'translate3d(-4px, 0, 0)' },
          '40%, 60%': { transform: 'translate3d(4px, 0, 0)' },
        },
        jelly: {
          '0%': { transform: 'scale3d(1, 1, 1)' },
          '30%': { transform: 'scale3d(1.25, 0.75, 1)' },
          '40%': { transform: 'scale3d(0.75, 1.25, 1)' },
          '50%': { transform: 'scale3d(1.15, 0.85, 1)' },
          '65%': { transform: 'scale3d(0.95, 1.05, 1)' },
          '75%': { transform: 'scale3d(1.05, 0.95, 1)' },
          '100%': { transform: 'scale3d(1, 1, 1)' },
        },
        glitch: {
          '2%, 64%': { transform: 'translate(2px,0) skew(0deg)' },
          '4%, 60%': { transform: 'translate(-2px,0) skew(0deg)' },
          '62%': { transform: 'translate(0,0) skew(5deg)' },
        },
        'border-beam': {
          '100%': { 'offset-distance': '100%' },
        },
        'slide-up': {
          '0%': { transform: 'translateY(100%)', opacity: '0' },
          '100%': { transform: 'translateY(0)', opacity: '1' },
        },
        'bounce-in': {
          '0%': { opacity: '0', transform: 'scale(.3)' },
          '50%': { opacity: '1', transform: 'scale(1.05)' },
          '70%': { transform: 'scale(.9)' },
          '100%': { transform: 'scale(1)' },
        },
        float: {
          '0%, 100%': { transform: 'translateY(0)' },
          '50%': { transform: 'translateY(-10px)' },
        },
        heartbeat: {
          '0%': { transform: 'scale(1)' },
          '14%': { transform: 'scale(1.1)' },
          '28%': { transform: 'scale(1)' },
          '42%': { transform: 'scale(1.1)' },
          '70%': { transform: 'scale(1)' },
        },
        rubberBand: {
          '0%': { transform: 'scale3d(1, 1, 1)' },
          '30%': { transform: 'scale3d(1.25, 0.75, 1)' },
          '40%': { transform: 'scale3d(0.75, 1.25, 1)' },
          '50%': { transform: 'scale3d(1.15, 0.85, 1)' },
          '65%': { transform: 'scale3d(0.95, 1.05, 1)' },
          '75%': { transform: 'scale3d(1.05, 0.95, 1)' },
          '100%': { transform: 'scale3d(1, 1, 1)' },
        },
        wobble: {
          '0%': { transform: 'translateX(0%)' },
          '15%': { transform: 'translateX(-25%) rotate(-5deg)' },
          '30%': { transform: 'translateX(20%) rotate(3deg)' },
          '45%': { transform: 'translateX(-15%) rotate(-3deg)' },
          '60%': { transform: 'translateX(10%) rotate(2deg)' },
          '75%': { transform: 'translateX(-5%) rotate(-1deg)' },
          '100%': { transform: 'translateX(0%)' },
        },
        pop: {
          '50%': { transform: 'scale(1.2)' },
        },
        typewriter: {
          'to': { left: '100%' }
        },
        'neon-pulse': {
          '0%': { boxShadow: '0 0 5px theme("colors.purple.500"), 0 0 10px theme("colors.purple.500")' },
          '100%': { boxShadow: '0 0 20px theme("colors.purple.500"), 0 0 35px theme("colors.purple.500")' }
        },
        'rotate-y': {
          '0%': { transform: 'rotateY(0deg)' },
          '100%': { transform: 'rotateY(360deg)' }
        }
      }
    },
  },
  plugins: [],
}
3. How to Use
Find a Button: Browse the ButtonVerse gallery to find the style you need.
Copy Code: Click the Code icon on the button card.
This copies the full JSX code, including the specific Icon imports from lucide-react.
Paste: Paste the code directly into your React component.
Example Usage
If you copy a "Primary Blue" button, the code will look like this:
code
Jsx
import { ArrowRight } from 'lucide-react';

export default function MyComponent() {
  return (
    <button className="px-6 py-2.5 font-semibold text-white shadow-md transition-all duration-200 hover:shadow-lg focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-neutral-900 bg-blue-600 hover:bg-blue-700 ring-blue-400">
      Click Me
    </button>
  )
}
4. Customization
The buttons use standard Tailwind utility classes, making them easy to customize.
Change Color: Replace bg-blue-600 with bg-red-500, bg-emerald-600, etc.
Change Size: Replace px-6 py-2.5 with px-4 py-2 (small) or px-8 py-4 (large).
Change Shape: Replace rounded-md with rounded-full or rounded-none.
5. Category Guide
ButtonVerse offers styles across these major categories:
Functional: Primary, Secondary, Tertiary, Outline, Ghost, Link.
Actions: FAB (Floating Action Button), Destructive, Success, Warning, Info.
Animations: Hover FX, Click FX, Text FX, Icon FX, Loading States.
Stylized: 3D, Gradient, Special Effects (Neon, Glassmorphism, Cyberpunk).
