# CommunityHub Advanced React Application

A sophisticated React application demonstrating modern frontend development practices, built as part of the Week 9 advanced React assignment.

## 🚀 Overview

CommunityHub is a full-featured React application showcasing:
- **React Router v7** for client-side routing
- **Custom Hooks** for reusable data fetching logic
- **Component-Based Architecture** with reusable UI components
- **API Integration** with JSONPlaceholder REST API
- **Dynamic Routing** for individual post views
- **Form Handling** for post creation simulation
- **Responsive Design** principles

## 📋 Features

- **Navigation System**: Persistent layout with navigation links
- **Post Management**: 
  - Browse latest posts from JSONPlaceholder
  - View individual post details
  - Create new posts (simulated)
- **Loading & Error States**: Graceful handling of API requests
- **Modern React Practices**:
  - Custom `useFetch` hook
  - Functional components with hooks
  - Conditional rendering
  - Proper state management
- **Clean Code Structure**: Well-organized file hierarchy

## 🛠️ Technology Stack

- **Frontend Library**: React 18
- **Routing**: React Router DOM v7
- **Build Tool**: Vite
- **Styling**: CSS (with potential for CSS Modules/Tailwind extension)
- **API**: JSONPlaceholder (https://jsonplaceholder.typicode.com/)
- **Package Manager**: npm

## 📁 Project Structure

```
src/
├── components/
│   ├── Layout/
│   │   └── Layout.jsx          # Application layout with navigation
│   ├── Post/
│   │   ├── PostCard.jsx        # Individual post preview component
│   │   └── PostList.jsx        # Post listing with data fetching
│   └── shared/
│       ├── Button.jsx          # Reusable button component
│       └── Loading.jsx         # Loading indicator component
├── hooks/
│   └── useFetch.js             # Custom data fetching hook
├── pages/
│   ├── Home.jsx                # Landing page
│   ├── Posts.jsx               # Posts listing page
│   ├── PostDetail.jsx          # Single post view (dynamic route)
│   ├── CreatePost.jsx          # Post creation form
│   └── About.jsx               # About page
├── App.jsx                     # Route configuration
└── main.jsx                    # Application entry point
```

## 🔧 Installation & Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/theecolboy/week-9-react-advance.git
   cd week-9-react-advance
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Start the development server**:
   ```bash
   npm run dev
   ```

4. **Build for production**:
   ```bash
   npm run build
   ```

5. **Preview production build**:
   ```bash
   npm run preview
   ```

## 🌐 Available Routes

| Path       | Component      | Description                     |
|------------|----------------|---------------------------------|
| `/`        | Home           | Landing page                    |
| `/posts`   | Posts          | List of recent posts            |
| `/posts/:id`| PostDetail    | Detailed view of a specific post|
| `/create`  | CreatePost     | Form to create a new post       |
| `/about`   | About          | Information about the app       |

## 💡 Key Implementation Details

### Custom Hook (`useFetch.js`)
```javascript
import { useState, useEffect } from "react";

function useFetch(url) {
  const [data, setData] = useState([]);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    async function fetchData() {
      try {
        const res = await fetch(url);
        if (!res.ok) throw new Error("Error fetching data");
        const json = await res.json();
        setData(json);
      } catch (err) {
        setError(err.message);
      } finally {
        setLoading(false);
      }
    }
    fetchData();
  }, [url]);

  return { data, loading, error };
}
```

### Dynamic Routing
Utilizes `useParams` hook to capture post ID from URL:
```javascript
import { useParams } from "react-router-dom";
import { useEffect, useState } from "react";

function PostDetail() {
  const { id } = useParams();
  const [post, setPost] = useState(null);
  // ... fetch post data based on id
}
```

### Component Reusability
- `Button` component accepts `variant` and `children` props
- `PostCard` component receives `post` prop for display
- Layout component uses `Outlet` for nested routing

## 🎯 Learning Outcomes

This project demonstrates proficiency in:
- **React Fundamentals**: JSX, components, props, state
- **Hooks API**: useState, useEffect, useContext, custom hooks
- **Routing**: BrowserRouter, Routes, Route, Link, useParams, useNavigate
- **Data Fetching**: Async/await with fetch API, error handling
- **Application Structure**: Scalable folder organization
- **Development Tooling**: Vite, npm scripts, ES modules
- **Best Practices**: Component composition, separation of concerns

## 📱 Responsive Design Considerations

While the current implementation focuses on functionality, the component-based architecture makes it straightforward to:
- Add CSS modules or styled-components
- Implement responsive breakpoints
- Add accessibility attributes (aria-labels, semantic HTML)
- Implement dark/light mode themes

## 🔄 Future Enhancements

1. **State Management**: Integrate Redux or Context API for global state
2. **Authentication**: Add mock authentication system
3. **Real API Integration**: Connect to actual backend for post creation
4. **UI Enhancements**: 
   - Add Tailwind CSS or Material-UI
   - Implement animations with Framer Motion
   - Add form validation with React Hook Form
5. **Testing**: 
   - Unit tests with Jest and React Testing Library
   - End-to-end tests with Cypress
6. **Performance**:
   - Implement React Query for advanced data fetching
   - Add code splitting and lazy loading
   - Implement caching strategies

## 📝 Assignment Requirements Met

✅ **useEffect Hook**: Used in PostDetail and useFetch hooks  
✅ **API Fetching**: Integrated with JSONPlaceholder API  
✅ **Custom Hook**: Created useFetch.js for reusable data fetching  
✅ **React Router**: Implemented with BrowserRouter, Routes, Route  
✅ **Dynamic Routes**: Used useParams for post detail viewing  
✅ **Pages System**: Created all required page components  
✅ **Basic Form**: CreatePost form with controlled components  
✅ **Clean Structure**: Organized component and page directories  

## 🤝 Contributing

This project was created as an educational assignment. However, if you'd like to suggest improvements:
1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Open a pull request

## 📄 License

This project is for educational purposes and is licensed under the MIT License.

## 🙏 Acknowledgments

- [JSONPlaceholder](https://jsonplaceholder.typicode.com/) for providing the free REST API
- [React Documentation](https://react.dev/) for excellent learning resources
- [Vite](https://vitejs.dev/) for the fast build tooling
- [React Router](https://reactrouter.com/) for the routing solution

---

**Built with ❤️ using React and modern frontend technologies**