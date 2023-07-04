# **ROUTING IN REACT APPLICATIONS.**
React apps are Single Page Applications (SPA) and by default, React does not provide any modalities for routing. Nevertheless, routing in React is achieve using external library known as React-router-dom. What this article aim to achieve is to create a navigation bar that navigate between internal links and render different contents.

To better our understandings on the steps in Routing, we need to have basic knowledge on some concepts and they include:
* React,
* Single Page Applications,
* React router dom, and
* Routing.

This article will do justice by explaining the above concepts.

## **What is React?**
React also known as ReactJS is a JavaScript library used in building interactive web interface. React library build **Single Page Applications (SPA)** using independent componenets that area reusable.
## **What are Single-page applications?**
**Single page applications (SPA)** are websites that renders different contents based on user request without loading a new page. When a user navigates through internal links on websites, by default, an entire new page is loaded but with SPA, different contents are rendered and changed while the page remains static.
## **What Is React-router?**
React-router is a library that enable React apps navigate between links and render different contents based on user request.
## **What Is Routing?**
Routing is the act of navigating to different sites, contents or pages using links based on user request.
## **Step By Step Guide On How To Render dynamic Content Through Routing in React App.**
In this section, we shall be building a navigation bar that contain links rendering different contents based on user request.

**Note:** To create a react app, you must install Node.js and NPM (Node Package Manager) on your computer. Visit [https://nodejs.org](https://nodejs.org) to download Node.js and NPM if you don't have them on your PC.

**Prerequisite:** To have the best out of this article, it is important to be knowledgeable in JavaScript and React library tools such as:
* Object,
* Object Destructuring,
* JSX,
* Components,
* Variables, amongst other.

If you are unfamiliar with the above tools, we recommend taking some time to learn and get familiar with them.

* ### **Step 1 - Create A React App.**
Create a folder for your react project and navigate to the directory of the folder on your terminal to create a react app as seen below.
```
C:\Users\Username\Desktop>mkdir react-app
C:\Users\Username\Desktop>cd react-app
```
Create a react app using one of the command below.
```
C:\Users\Username\Desktop\react-app>npx create-react-app my-app
```
OR
```
C:\Users\Username\Desktop\react-app>npm init react-app my-app
```
For Yarn users, run:
```
C:\Users\Username\Desktop\react-app>Yarn create-react-app my-app
```
Note: my-app can be any name of your choice.
* ### **Step 2 - Install React-router-dom.**
Navigate to your react app directory on your terminal and run the command below to install react-router-dom.
```
C:\Users\Username\Desktop\react-app>cd my-app
C:\Users\Username\Desktop\react-app\my-app>npm install react-router-dom
```
When installation is finished, start server by running:
```
C:\Users\Username\Desktop\react-app\my-app>npm start
```
Your default browser opens on localhost:3000 and displays the image below.
![image](/images/react.png)
* ### **Step 3 - Index.js file**
In Index.js file, Import BrowserRouter from react-router-dom and Update root const by wrapping app component between BrowserRouter tags. See codes below.
```
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
```
* ### **Step 4 - Create pages**
In src directory, create a folder called pages with the following files:
* Home.js
* About.js
* Contact.js.

Fill each of these files with their dynamic contents as seen below.
* Home.js
```
function Home(){

    return (
        <>
          <h1>Home Page</h1>
        </>
    );
}

export default Home;
```
* About.js
```
function About(){

    return (
        <>
          <h1>About Page</h1>
        </>
    );
}

export default About;
```
* Contact.js
```
function Contact(){

    return (
        <>
          <h1>Contact Page</h1>
        </>
    );
}

export default Contact;
```
* ### **Step 5 - Create a Nav Component**
Next, create a components folder at src directory with Nav.js file in the folder. In Nav.js file, import Link from react-router-dom using object destructuring and return a nav element at Nav function as seen below.
```
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
```
Note that in our above codes, Link element is used to navigate between pages. Link accept a 'to' attributes that points to the resources it's linking to.
* ### **Step 6 - Create Routes and Route and render Nav Componenet**
In App.js file, Import all pages and components. Also Import routes and route from react-router-dom using object destructuring. Next, render Nav component and create necessary routes as seen in codes below.
```
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
```
In our above codes, each Route tag has a path and element attributes. The element attributes takes in components to be rendered. Path attributes indicates the url route. The forward slash of Home component signifies the default route.
* ### **Step 7 - CSS Styling**
Add CSS styles to our nav component. This can be done in index.css file.
```
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
```
Note we use 'a' element selector when styling our Link element. This is because Link elements are anchor tags but with slightly different functionality.

We can now click on the links and navigate to different components. See video [Here](https://www.youtube.com/watch?v=s73UPVliw0M)

In conclusion, this article explain how routing can be achieved in react apps using react-router-dom. Important concept such as Single Page Application (SPA), React-router, and routing were explained.
I hope this article was helpful? if yes follow me on [twitter](https://twitter.com/dauda_nehemiah) and [linkedIn](https://www.linkedin.com/in/nehemiah-dauda) for more insightful tutorials and technical articles.