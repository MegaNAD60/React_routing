ROUTING IN REACT APPLICATIONS
Navigating between links was challenging when I began creating React applications. As a single page application, React does not provide any default modalities for routing between different pages. The purpose of this article is to explain how navigation between links can be achieved in react applications using react-router-dom. I will also explain important concept such as Single Page Application (SPA), React-router, and routing.
What are Single-page applications?
Single page applications (SPA) are websites that renders dynamic contents upon user request without loading a new page. When a user navigates through internal links on a website, by default, an entire new page is loaded but with SPA, different contents are rendered dynamically on a single static page. React applications are example of SPA.
What is React-router?
React-router is a library which, offers routing among dynamic components in React applications.
What is Routing?
Routing means techniques that offer navigation among pages or components on websites based on user request.
How To Achieve Routing With React App.
As noted above, React apps are Single Page Application. In order to navigate through internal links, we must use react-router library. This section will guide you through on how to build a react app that offer routing to dynamic contents.
To create a react app, you must install Node.js and NPM (Node Package Manager) on your computer. Visit https://nodejs.org to download Node.js and NPM if you don't have them on your PC.
Create a folder for your react project, navigate to the directory of the folder on your terminal and run one of the command below.
npx create-react-app my-app
OR
npm init react-app my-app
Each of the above commands create a new react app. For Yarn users, run:
Yarn create-react-app my-app
Note: my-app can be any name of your choice.
Navigate to your react app directory on your terminal and run the command below to install react-router-dom.
npm install react-router-dom
When installation is finished, start server by running:
npm start
Your default browser will automatically open on localhost:3000 and displays the image below.
We've created our react app and install react-router-dom; next, we shall build our various pages and components. At src directory, create a folder called pages with the following files.
· Home.js
· About.js
· Contact.js.
Fill each of these files with their dynamic contents.
Home.js
function Home(){

    return (
        <>
          <h1>Home Page</h1>
        </>
    );
}

export default Home;
About.js
function About(){

    return (
        <>
          <h1>About Page</h1>
        </>
    );
}

export default About;
Contact.js
function Contact(){

    return (
        <>
          <h1>Contact Page</h1>
        </>
    );
}

export default Contact;
Next, create a folder called 'components' at src directory; create a nav.js file; import Link from react-router-dom and fill in the below codes.
import { Link } from "react-router-dom";

function Nav(){
    return (
        <>
          <nav className="nav">
            <Link to="/">Home</Link>
            <Link to="/about">About</Link>
            <Link to="/contact">Book</Link>
          </nav>
        </>
    );
}

export default Nav;
In our above codes, Link element allows users navigate between pages. Link accept a 'to' attributes that points to the resources it's linking to.
Add some CSS styles to our nav component. This can be done in index.css file.
.navbar{
  background-color: rgb(14, 136, 207);
  padding: 3px;
  display: flex;
  justify-content: center;
  gap: 20px;
}

.navbar a{
  text-decoration: none;
  color: white;
  font-size: 1.3rem;
}

.navbar a:hover{
  color: aqua;
}
Notice we use 'a' element selector when styling our Link element. This is because Link elements are anchor tags but with slightly different functionality.
Next, open Index.js file, Import BrowserRouter from react-router-dom and Update root const by wrapping app component between BrowserRouter tags. See codes below.
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';
import { BrowserRouter } from 'react-router-dom';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <BrowserRouter>
    <App />
  </BrowserRouter>
);
Next, in App.js file, import routes and route from react-router-dom and updates its contents as seen below.
import React from 'react';
import './App.css';
import Home from './pages/Home';
import About from './pages/About';
import Contact from './pages/Contact';
import Nav from './components/Nav';
import { Route, Routes } from 'react-router-dom';

function App() {
  return (
    <div className="App">
      <Nav />

      <Routes>
        <Route path='/' element={<Home />}></Route>
        <Route path='/about' element={<About />}></Route>
        <Route path='/contact' element={<Contact />}></Route>
      </Routes>
    </div>
  );
}

export default App;
In our codes above, we imported Nav component and render it on app function. We created Routes that is the parent component of Route. Each Route tag has a path and element attributes. The element attributes takes in components to be rendered. Path attributes indicates the url route. The forward slash of Home component signifies the default route.
We can now click on the links and navigate to different components. See video below.

In conclusion, this article explain how routing can be achieved in react apps using react-router-dom. Important concept such as Single Page Application (SPA), React-router, and routing were explained.
I hope this article was helpful? if yes follow me on twitter https://twitter.com/dauda_nehemiah and linkedIn https://www.linkedin.com/in/nehemiah-dauda for more insightful tutorials and technical articles.