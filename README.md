# CommunityHub Advanced React Assignment

This is a React application built as part of the Week 9 assignment for learning React Router, custom hooks, API fetching, and component-based architecture.

## Features

- React Router for navigation
- Custom `useFetch` hook for data fetching
- API integration with JSONPlaceholder
- Component-based architecture
- Responsive layout
- Navigation between pages:
  - Home
  - Posts (with PostList and PostCard components)
  - Post Detail (dynamic route)
  - Create Post (form simulation)
  - About

## Project Structure

```
src/
├── components/
│   ├── Layout/
│   │   └── Layout.jsx
│   ├── Post/
│   │   ├── PostCard.jsx
│   │   └── PostList.jsx
│   └── shared/
│       ├── Button.jsx
│       └── Loading.jsx
├── hooks/
│   └── useFetch.js
├── pages/
│   ├── Home.jsx
│   ├── Posts.jsx
│   ├── PostDetail.jsx
│   ├── CreatePost.jsx
│   └── About.jsx
├── App.jsx
└── main.jsx
```

## Installation

1. Clone the repository
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the development server:
   ```bash
   npm run dev
   ```

## Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build

## Learning Objectives

This project demonstrates:
- useEffect hook for side effects
- API fetching with fetch()
- Custom hook creation
- React Router implementation
- Dynamic routing with useParams
- Component composition
- State management with useState
- Conditional rendering
- Form handling

## API Used

- JSONPlaceholder: https://jsonplaceholder.typicode.com/

## Notes

This assignment focuses on learning core React concepts and patterns. The CreatePost form simulates submission by logging to console rather than actually posting to an API.