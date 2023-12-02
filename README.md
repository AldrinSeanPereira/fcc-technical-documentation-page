# fcc-technical-documentation-page
## mini project of the RWD certification 

- The **MOST FRUSTRATING** project so far of the certfication, but I definitely learned from my mistakes

- **Easy part** :  Making everything look nice like borders, background, HTML structure

- **Hard part** :  to position the navigation and the text-content.

- **Temporary fix** : I eventually had to use relative and absolute positioning to get the job done

- The **ACTUAL SOLUTION** for the problem of positioning would be like this:
  - in HTML we have a `div` which contains `nav` and `main`
  - in CSS make the default positions to be mobile first, use `flex-direction: column` so `nav` on top and `main` on bottom
  - we want everything to fit the full viewport so let `body` be 100vh (meaning 100% of viewport height)
  - and let `#container` (having `nav` and `main`) be 100% height
  - we also want the `nav` and `main` to be vertically scrollable so set `overflow-y: auto` for them in CSS
    
   ```html
   <body>
      <div id="container">
        <nav></nav>
        <main></main>
      </div>
   </body>
   ```
   
   ```css
   body {
   height: 100vh;
   }
   
   #container {
      display: flex;
      flex-direction: column;
       height: 100%;
   }

   nav, main {
    overflow-y: auto;
   }
   ```
   
   - Then add a media query for larger screens, use `flex-direction: row` so `nav` on left and `main` on right
    ```css
    @media(min-width: 1000px) {
      #container {
        display: flex;
        flex-direction: row;
      }
    }
    ```

