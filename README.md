# Notes

- Created an application using vite (webpack)
- Setup eslint for the project
- Routing - refers to change in the url when we navigate to different component
- SPA - In normal website page is fully loaded whereas in single page application app is never fully loaded
- Here is the flow ->
  - user clicks on the link
  - url is changed
  - dom is updated by the react router
- Next step Implementing routes for our application
  - Install react router package (3rd party library) npm i react-router-dom@6
  - Declarative way for defining routes
  ```
  <BrowserRouter>
      <Routes>
          <Route path='product' element={<Product/>}/>
          <Route path='pricing' element={<Pricing/>}/>
          <Route path='/' element={<HomePage/>}/>
      </Routes>
  </BrowserRouter>
  ```
  - This way helps us to setup the url change with respect to the component change but still the navigation is not proper
  - We added anchor tag for navigating but we saw the issue with whole page getting reloaded so we have some good alternative that is to use Link and Navlink( which has active class also associated)
- Styling options: There are multiple options to style our web application uptil this point in course we were using one external css but we have other alternative as well. Let us explore one by one.

  - inline css , using style prop we apply style , have local scope
  - external one css file, using className, have global scope and comes with issue if project goes big
  - css modules, one file per component, component scope
  - Tailwind css, component scope, className
  - No css at all, using prebuilt css using material ui, chakra ui, mantine
  - In order to add global class for our css modules we can use something like - .nav :global(.active) {
    background-color: yellow;

- Adding nested routes to the web application and use of Outlet component

  ```
  <BrowserRouter>
      <Routes>
        <Route path="/" element={<HomePage />} />
        <Route path="product" element={<Product />} />
        <Route path="app" element={<AppLayout />}>
          <Route path="cities" element={<p>Placeholder for cities</p>} />
          <Route path="countries" element={<p>Placeholder for countries</p>} />
          <Route path="form" element={<p>Placeholder for form</p>} />
        </Route>
        <Route path="pricing" element={<Pricing />} />
        <Route path="login" element={<Login />} />
        <Route path="*" element={<PageNotFound />} />
      </Routes>
    </BrowserRouter>
  ```

  And the outlet component is the place where we want to place the nested route component. One more point to note here is by default there is no preffered route if we go to app link but we can make one of the route as default route
  using index above also we can do something like <Route index element={<HomePage />} />
  The next thing that we need to understand is how to setup fake api

  - Install json server package -> npm i json-server
  - In package.json we need to add "server": "json-server --watch data/cities.json --port 8000"
  - To run the same we need to do npm run sever

  - Storing state in url

  - Programmatic navigation using useNavigate, this is used when we want to navigate to a page without link, say for example when we submit a form we want to redirect a user to another page that is what the power of useNavigate is
    - const navigate = useNavigate();
    ```
      onClick={() => {
          navigate("form");
      }
    ```
