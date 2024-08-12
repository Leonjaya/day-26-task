# day-26-task
import React from 'react';
import { BrowserRouter as Router, Routes, Route } from 'react-router-dom';
import Navbar from './components/Navbar';
import Footer from './components/Footer';
import Home from './pages/Home';
import About from './pages/About';
import Blog from './pages/Blog';
import Contact from './pages/Contact';

function App() {
  return (
    <Router>
      <Navbar />
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
        <Route path="/blog" element={<Blog />} />
        <Route path="/contact" element={<Contact />} />
      </Routes>
      <Footer />
    </Router>
  );
}

export default App;
import React from 'react';
import { Link } from 'react-router-dom';
import './Navbar.css';

const Navbar = () => {
  return (
    <nav className="navbar">
      <div className="navbar-logo">
        <Link to="/">Guvi Blog</Link>
      </div>
      <div className="navbar-links">
        <Link to="/">Home</Link>
        <Link to="/about">About</Link>
        <Link to="/blog">Blog</Link>
        <Link to="/contact">Contact</Link>
      </div>
    </nav>
  );
};

export default Navbar;
import React from 'react';
import './Footer.css';

const Footer = () => {
  return (
    <footer className="footer">
      <p>&copy; 2024 Guvi Blog. All rights reserved.</p>
    </footer>
  );
};

export default Footer;
import React from 'react';
import { Link } from 'react-router-dom';
import './BlogList.css';

const BlogList = ({ blogs }) => {
  return (
    <div className="blog-list">
      {blogs.map(blog => (
        <div key={blog.id} className="blog-card">
          <Link to={`/blog/${blog.id}`}>
            <h2>{blog.title}</h2>
            <p>{blog.excerpt}</p>
          </Link>
        </div>
      ))}
    </div>
  );
};

export default BlogList;
import React from 'react';
import './Home.css';

const Home = () => {
  return (
    <div className="home">
      <h1>Welcome to the Guvi Blog</h1>
      <p>Your source for the latest tech news and insights.</p>
    </div>
  );
};

export default Home;
import React from 'react';
import './About.css';

const About = () => {
  return (
    <div className="about">
      <h1>About Us</h1>
      <p>Learn more about the Guvi Blog and our mission to provide quality content.</p>
    </div>
  );
};

export default About;
import React from 'react';
import BlogList from '../components/BlogList';
import './Blog.css';

const blogs = [
  { id: 1, title: 'Blog Post 1', excerpt: 'This is the first blog post.' },
  { id: 2, title: 'Blog Post 2', excerpt: 'This is the second blog post.' },
  // Add more blog posts here
];

const Blog = () => {
  return (
    <div className="blog">
      <h1>Blog</h1>
      <BlogList blogs={blogs} />
    </div>
  );
};

export default Blog;
import React from 'react';
import './Contact.css';

const Contact = () => {
  return (
    <div className="contact">
      <h1>Contact Us</h1>
      <p>If you have any questions, feel free to reach out to us.</p>
    </div>
  );
};

export default Contact;
