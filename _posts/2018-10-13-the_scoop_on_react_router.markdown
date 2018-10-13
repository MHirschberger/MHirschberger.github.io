---
layout: post
title:      "The Scoop on React Router"
date:       2018-10-13 14:35:18 +0000
permalink:  the_scoop_on_react_router
---

**Introduction**

One of the main goals of React is to create a seamless web experience by utilizing client-side routing. When using a framework like React, it is common to build applications that are single-page appications (SPAs), where webpages load once and then are dynamically updated using Javascript. For this situation, React would be responsible for routing, fetching data from the API, and displaying that data in the browser, instead of the server.  The result of using SPAs with client-side routing is greater efficiency and speed.

**Implementation**

The most commonly-used React routing library for implementing client-side routing is React Router. To utilize the `react-router` library in a web app, the `react-router-dom` npm package needs to be included in the app's `package.json` file. 'react-router-dom` uses `BrowserRouter` to bring React Router's functionality to the web app. In my most recent app, Community Space, `BrowserRouter` is imported into my `index.js` file, the top-most level in the application, as `Router` and `Router` tags wrap the `App` component, which then extends that functionality to the rest of the app. The is shown below:

```
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';
import { Provider } from 'react-redux';
import { createStore, applyMiddleware } from 'redux';
import thunk from 'redux-thunk';
import rootReducer from './reducers';
import { BrowserRouter as Router } from 'react-router-dom';

const store = createStore(rootReducer, applyMiddleware(thunk));

ReactDOM.render(
    <Provider store={store} >
        <Router>
            <App />    
        </Router>
    </Provider>,
    document.getElementById('root')
);
```

In my `App.js` file, the `Route` component is used to render the appropriate user interface when a location matches the route’s path. The path's corresponding component is then displayed. 

```
import React, { Component } from 'react';
import './App.css';
import AllDiscussions from './components/AllDiscussions';
import Home from './components/Home';
import About from './components/About';
import { Route } from 'react-router-dom';
import Navbar from './components/Navbar';
import DiscussionInput from './components/Discussions/DiscussionInput';
import CommentsContainer from './containers/CommentsContainer';
import Login from './components/Sessions/Login';
import Logout from './components/Sessions/Logout';

class App extends Component {
  render() {
    return (
      <div className="App">
        <header className="App-header">
          <h1 className="App-title">Community Space</h1>
          <Navbar />
        </header>
        <div className="App-body">
          <Route exact path="/" component={Home} />
          <Route exact path="/about" component={About} />
          <Route exact path="/discussions" component={AllDiscussions} />
          <Route exact path="/discussions/new" component={DiscussionInput} />
          <Route exact path="/discussions/:discussion_id/comments" component={CommentsContainer} />
          <Route exact path="/login" component={Login} />
        </div>
      </div>
    );
  }
}

export default App;
```

Here you can see for each route, there is a path and the component that gets displayed for each path. A quick word about `path` vs. `exact path`: The word `exact` is used if you only want the `Route` to match the location if the two paths are exactly matched. When true, will only match if the path matches the location.pathname exactly. Since we are using nested routes for `discussions`, `exact` was used to be explicit. 

From here, I used `NavLink` to provide the links that would the user would click on to navigate to the different routes. In my case I created a `Navbar.js` file to house my `NavLink`s:

```
import React from 'react';
import { NavLink } from 'react-router-dom';

const link = {
  width: '100px',
  padding: '12px',
  margin: '0 6px 6px',
  background: '#191970',
  textDecoration: '#191970',
  color: 'white',
}

const Navbar = () => 

    <div>
    <NavLink
      className='navbar'
      to="/"
      exact
      style={link}
      activeStyle={{
        background: '#4169E1'
      }}
    >Home</NavLink>
    <NavLink
      className='navbar'
      to="/about"
      exact
      style={link}
      activeStyle={{
        background: '#4169E1'
      }}
    >About</NavLink>
    <NavLink
      className='navbar'
      to="/discussions"
      exact
      style={link}
      activeStyle={{
        background: '#4169E1'
      }}
    >Browse Discussions</NavLink>
    <NavLink
      className='navbar'
      to="/discussions/new"
      exact
      style={link}
      activeStyle={{
        background: '#4169E1'
      }}
    >Start New Discussion</NavLink>
    <NavLink
      className='navbar'
      to="/login"
      exact
      style={link}
      activeStyle={{
        background: '#4169E1'
      }}
      >Login/Account</NavLink>
    </div>
  

export default Navbar;
```
`Navlink` or `Link` could have been used here. `NavLink`, however, provides additional styling attributes. For this app, I used the feature called `activeStyle`, which allows you to include special styling for links which are active. In this case I made the standard `style` a darker shade of blue, and the `activeStyle` a lighter shade of blue, as shown below:

![](https://i.imgur.com/H5AarQv.png?1)




