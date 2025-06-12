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
}