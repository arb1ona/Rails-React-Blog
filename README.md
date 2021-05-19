# Configuring React as Your Rails Frontend

    Rails, with the help of the Webpacker gem, bundles all your JavaScript code into packs. These can be found in the packs directory at `app/javascript/packs`. You can link these packs in Rails views using the `javascript_pack_tag` helper, and you can link stylesheets imported into the packs using the `stylesheet_pack_tag` helper. To create an entry point to your React environment, you will add one of these packs to your application layout.

1. Rename `app/javascript/packs/hello_react.jsx` to `/Index.jsx`
2. Add lines `app/views/layouts/application.html.erb`

   <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
   <%= javascript_pack_tag 'Index' %>

   Now that the entry file is loaded onto the page, create a React component for the homepage.

3. Create directories in `app/javascript`

   `app/javascript/components/Home.jsx`
   Import React and also the Link component from React Router. The Link component creates a hyperlink to navigate from one page to another. You then created and exported a functional component containing some Markup language for your homepage, styled with Bootstrap classes.
   With your Home component in place, you will now set up routing using React Router.

   `app/javascript/routes/Index.jsx`

   In this Index.jsx route file, you imported a couple of modules: the React module that allows us to use React, and the BrowserRouter, Route, and Switch modules from React Router, which together help us navigate from one route to another. Lastly, you imported your Home component, which will be rendered whenever a request matches the root (/) route. Whenever you want to add more pages to your application, all you need to do is declare a route in this file and match it to the component you want to render for that page.

4. You have now successfully set up routing using React Router. For React to be aware of the available routes and use them, the routes have to be available at the entry point to the application. To achieve this, you will render your routes in a component that React will render in your entry file.Create `App.jsx`

   `app/javascript/components/App.jsx`

   In the App.jsx file, you imported React and the route files you just created. You then exported a component that renders the routes within fragments. This component will be rendered at the entry point of the aplication, thereby making the routes available whenever the application is loaded.

5. Now that you have your App.jsx set up, it’s time to render it in your entry file.

   `app/javascript/packs/Index.jsx`

   In this code snippet, you imported React, the render method from ReactDOM, Bootstrap, jQuery, Popper.js, and your App component. Using ReactDOM’s render method, you rendered your App component in a div element, which was appended to the body of the page. Whenever the application is loaded, React will render the content of the App component inside the div element on the page.
