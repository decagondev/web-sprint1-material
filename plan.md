# Plan for Building Web Unit 1 Sprint 1 Course Content Site

## Overview
This plan outlines the steps to create a static HTML site for the BloomTech "Web Unit 1 Sprint 1" course, converting Canvas LMS content to a clean, styled HTML page using Tailwind CSS with dark/light theme support.

## Analysis Findings
- **Course Structure**: Web Unit 1 Sprint 1 (JavaScript and HTML I) with 4 modules:
  - Module 1: First Steps into JavaScript
  - Module 2: Program Flow
  - Module 3: Functions
  - Module 4: HTML & CSS I
- **Content Type**: HTML pages with course material, case studies, and embedded videos
- **Design Elements**: The original design uses colors #93005a (purple) and #00808c (teal) as primary colors

## Implementation Plan

### 1. Project Setup
- [ ] Create index.html file for the main landing page
- [ ] Add HTML5 doctype and basic structure
- [ ] Add meta tags for viewport, description, etc.
- [ ] Include Tailwind CSS via CDN
- [ ] Add theme toggle functionality (light/dark mode)

### 2. Design System
- [ ] Define color scheme based on original colors (#93005a, #00808c) for both light/dark themes
- [ ] Create consistent typography hierarchy
- [ ] Design consistent component styles (cards, buttons, navigation)
- [ ] Implement responsive layout with mobile-first approach

### 3. Navigation Structure
- [ ] Create header with course title and theme toggle
- [ ] Design module navigation card system
- [ ] Create sidebar with links to main content sections
- [ ] Make navigation sticky on desktop and collapsible on mobile

### 4. Content Structure
- [ ] Build welcome section with embedded intro video
- [ ] Design module cards with visual indicators for progression
- [ ] Create consistent content template for lesson pages
- [ ] Add footer with relevant links and information

### 5. Module Content Display
- [ ] Design clean, readable content cards
- [ ] Style the case study highlight boxes
- [ ] Format code snippets with syntax highlighting
- [ ] Create "next lesson" navigation for content flow

### 6. Features & Components
- [ ] Create theme toggle button with animation
- [ ] Build responsive navigation system
- [ ] Implement collapsible content sections
- [ ] Add module progress tracking (visual indicators)

### 7. Optimization
- [ ] Minimize Tailwind CSS classes (focus on utility-first)
- [ ] Ensure responsive design works on all devices
- [ ] Implement proper semantic HTML structure
- [ ] Add appropriate ARIA attributes for accessibility

### 8. Testing & Review
- [ ] Test on multiple devices and browsers
- [ ] Verify theme toggle functionality
- [ ] Check all links and navigation paths
- [ ] Review accessibility with automated tools

## Technical Implementation Details

### HTML Structure
```html
<!DOCTYPE html>
<html lang="en" class="light">
<head>
  <!-- Meta tags, title, Tailwind CSS CDN -->
</head>
<body class="bg-gray-50 dark:bg-gray-900 text-gray-900 dark:text-gray-100 transition-colors duration-200">
  <!-- Header -->
  <!-- Main content with sidebar and content area -->
  <!-- Footer -->
  <!-- Theme toggle script -->
</body>
</html>
```

### Theme Toggle Implementation
```javascript
// Simple theme toggle between light and dark mode
function toggleTheme() {
  const html = document.documentElement;
  if (html.classList.contains('dark')) {
    html.classList.remove('dark');
    localStorage.theme = 'light';
  } else {
    html.classList.add('dark');
    localStorage.theme = 'dark';
  }
}

// Initialize theme based on user preference or system setting
if (localStorage.theme === 'dark' || (!('theme' in localStorage) && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
  document.documentElement.classList.add('dark');
} else {
  document.documentElement.classList.remove('dark');
}
```

### Color Scheme
- **Light Theme**:
  - Primary: #93005a (purple)
  - Secondary: #00808c (teal)
  - Background: #f9fafb (gray-50)
  - Text: #111827 (gray-900)
  
- **Dark Theme**:
  - Primary: #d946ef (purple-500)
  - Secondary: #06b6d4 (cyan-500)
  - Background: #111827 (gray-900)
  - Text: #f9fafb (gray-50)

## Guidelines
- Focus on creating a clean, modern educational platform
- Maintain the learning flow of the original content
- Ensure easy navigation between modules and lessons
- Make the site fully responsive for all device sizes
- Implement proper accessibility features 