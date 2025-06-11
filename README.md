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