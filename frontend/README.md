JS AMAZON CLONE

1. Create Folder Structure

   1. Create root folder as amazon
   2. Add frontend and backend folder
   3. Create src folder in frontend
   4. Create index.html with heading JS Amazon Clone in src
   5. run npm init in frontend folder
   6. npm install live-server
   7. add start command as live-server src --verbose
   8. run npm start

2. Design Website

   1. Create style.css
   2. Link style.css to index.html
   3. create div.grad-container
   4. create header, main and footer
   5. style html, body
   6. style grid-container, header, main and footer

3. Create Static Home Screen

   1. Create ul.products
   2. Create li
   3. Create div.product
   4. Add .product-image, .product-name, .product-brand, .product-price
   5. style ul.products and internal divs
   6. duplicate 2 times to show 3 products

4. Render Dynamic Home Screen

   1. Create data.js
   2. Export an array of 6 products
   3. Create screen/HomeScreen.js
   4. Export HomeScreen as an object with render() method
   5. Implement render()
   6. Import data.js
   7. Return products mapped to <li>(s) inside an ul
   8. Create app.js
   9. Link it to index.html as module
   10. Set main id to main_container
   11. Create router() function
   12. Set main_container innerHTML to HomeScreen.render()
   13. Set load event of window to router() function

5. Build URL Router

   1. Create routes as route:screen object for home screen
   2. Create utils.js
   3. Export parseReqeuestURL()
   4. Set URL as hash address split by slash
   5. Return resource, id and verb of url
   6. Update router()
   7. Set Request as parseRequestURL()
   8. Build parsedURL and compare with routes
   9. If routes exists render it, else render Erro404
   10. Create screens/Error404.js and render error message

6. Create Node.JS Server

   1. Run npm init in root amazon folder
   2. npm install express
   3. Create server.js
   4. Add start command as node backend/server.js
   5. require express
   6. Move data.js from frontend to backend
   7. Create route for /api/products
   8. Return products in data.js
   9. Run npm start

7. Load Products From Backend

   1. Edit HomeScreen.js
   2. Make render async
   3. Fetch products from 'api/products' in render()
   4. Make router() async and call await HomeScreen.render()

8. Add Webpack

   1. cd frontend
   2. npm install -D webpack webpack-cli webpack-dev-server
   3. npm uninstall live-server
   4. "start": "webpack-dev-server --mode development --watch-content-base --open"
   5. Move index.html, style.css and images to frontend folder
   6. Rename app.js to index.js
   7. Update index.html
   8. Add <script src="main.js"></script> before </body>
   9. npm start
   10. npm install axios
   11. Change fetch to axios in HomeScreen

9. Install Babel For ES6 Syntax

   1. npm install -D babel core, cli, node, preset-env
   2. Create .babelrc and set presets to @babel/preset-env
   3. npm install -D nodemon
   4. Set start: nodemon --watch backend --exec babel-node backend/server.js
   5. Convert require to import in server.js
   6. npm start

10. Enable Code Linting

    1. npm install -D eslint
    2. Install VSCode eslint extension
    3. Create .eslintrc and set module.exports for env to node
    4. Set VSCode setting for editor.codeActionOnSave cource.fixAll.eslint to true
    5. Check result for linting error
    6. npm install eslint-config-airbnb-base and eslint-plugin-import
    7. Set extends to airbnb-base
    8. Set parseOptions to ecmaVersion 11 and sourceType to module
    9. Set rules for no-console to 0 to ignore linting error

11. Install VSCode

    1. Javascript (ES6) code snippets
    2. ES7 React/Redux/GraphQL/React-Native snippets
    3. Prettier - Code formatter
    4. HTML&LESS grammar injections
    5. CSS Peek

12. Create Rating Component

    1. Create components/Rating.js
    2. Create div.rating
    3. Link to fontawesome.css in index.html
    4. Define Rating object with render()
    5. if !props.value return empty div
    6. else use fa fa-star, fa-star-half-o and fa-star-o
    7. last span for props.text || ''
    8. style div.rating, span and last span
    9. Edit HomeScreen
    10. Add div.product-rating and use Rating component

13. Prodcut Screen

    1. Get product id from request
    2. Implement /api/product/:id api
    3. Send AJAX request to product api

14. Prodcut Screen UI

    1. Create back to result link
    2. Create div.details with 3 columns
    3. Column 1 for product image
    4. Column 2 for product information
    5. Column 3 form product ation
    6. Style .details and all columns
    7. Create ad to cart button with add-button id
    8. after_render() to add event to the button
    9. redirect user to cart/:product_id

15. Product Screen Action

    1. after_render() to add event to the button
    2. Add event handler for the button
    3. Redirect user to cart/:product_id
    4. Implement after_render in index.js

16. Add To Cart Action

    1. Create CartScreen.js
    2. parseRequestUrl
    3. getProduct(request.id)
    4. addToCart
    5. getCartItems
    6. cartItems.find
    7. If existItem update qty
    8. else add item
    9. setCartItems

17. Cart Screen UI

    1. cartItems = getCartItems()
    2. Create 2 columns for cart items and cart action
    3. cartItems.length === 0 ? cart is empty
    4. Show item image, name, qty and price
    5. Cart action
    6. Subtotal
    7. Proceed to checkout button
    8. Add CSS style

18. Update and Delete Cart Items

    1. Add qty select next to each item
    2. after_render()
    3. Add change event to qty select
    4. getCartItems() and pass to addToCart()
    5. Set force to true to addToCart()
    6. Create rerender() as (component, areaName = 'content')
    7. component.render() and component.after_render()
    8. If force is true then rerender()
    9. Add delete button next to each item
    10. Add click event to qty button
    11. Call removeFromCart(deleteButton.id)
    12. Implement removeFromCart(id)
    13. setCartItems( getCartItems().filter)
    14. If id === parseRequestUrl().id ? redirect to '/cart'
    15. else rerender(CartScreen);
