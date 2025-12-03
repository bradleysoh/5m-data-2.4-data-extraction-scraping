 # CSS Selectors Demo in CodePen
 
 Follow these steps to run the example in CodePen:
 
 1. Open this CodePen in your browser:
    - https://codepen.io/timsamoff/pen/QQrPPy?editors=1100
 
 2. In the **HTML** panel of CodePen, replace the existing contents with the following HTML (start from '<!DOCTYPE html>', ignore '```html'):
 
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>CSS Selectors Demo</title>
        <link rel="stylesheet" href="styles.css">
    </head>
    <body>
    
        <h1>CSS Selectors Demonstration</h1>
        
        <!-- Element Selector Demo -->
        <h2>This is an h2 element (Element Selector)</h2>
        <h2>Another h2 element with the same styling</h2>
        
        <!-- ID Selector Demo -->
        <div id="content">
            <p>This div has id="content" (ID Selector)</p>
            <p>It has purple text and 15px font size</p>
        </div>
        
        <!-- Class Selector Demo -->
        <div class="main">
            <p>This div has class="main" (Class Selector)</p>
            <p>It has 10px margins on top and bottom</p>
        </div>
        
        <div class="main">
            <p>Another div with class="main"</p>
            <p>Same margins applied</p>
        </div>
        
        <!-- Table Demo -->
        <h3>Table Styling Demo</h3>
        <table>
            <thead>
                <tr>
                    <th>Header 1</th>
                    <th>Header 2</th>
                    <th>Footer  3</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>Data 1</td>
                    <td>Data 2</td>
                    <td>Data 3</td>
                </tr>
                <tr>
                    <td>Data 4</td>
                    <td>Data 5</td>
                    <td>Data 6</td>
                </tr>
            </tbody>
        </table>
        
        <p>This paragraph shows the universal selector effect</p>
        <span>This span also shows universal selector styling</span>
    </body>
    </html>
    ```
 
 3. In the **CSS** panel of CodePen, replace the existing contents with the following CSS (start from '/* Universal Selector...', ignore '```css'):
 
    ```css
    /* Universal Selector - affects ALL elements */
    /** {
        color: #c70039;
    }*/
    
    /* Element Selector - targets all h2 elements */
    h2 {
        color: #c70039;
        font-weight: bold;
        margin: 20px 0;
    }
    
    /* ID Selector - targets element with id="content" */
    #content {
        color: green;
        font-size: 20px;
        background-color: #f0f0f0;
        padding: 15px;
        border-radius: 5px;
        margin: 20px 0;
    }
    
    /* Class Selector - targets elements with class="main" */
    .main {
        margin-top: 10px;
        margin-bottom: 10px;
        background-color: #e8f4f8;
        padding: 15px;
        border-left: 4px solid #2196F3;
        font-size: 30px;
    }
    
    /* Table Styling */
    table {
        width: 100%;
        border-collapse: collapse;
        margin: 20px 0;
    }
    
    table,
    td {
        border: 1px solid green;
    }
    
    /* Alternative selector for table headers */
    thead > tr > th {
        border: 1px solid #2B4D57;
        background-color: orange;
        padding: 10px;
        font-weight: bold;
    }
    
    /* Alternative way to target th elements */
    thead th {
        border: 1px solid #2B4D57;
        background-color: #f2f2f2;
        padding: 10px;
    }
    
    /* Table cell styling */
    td {
        padding: 10px;
        text-align: left;
    }
    
    /* Additional styling for better presentation */
    body {
        font-family: Arial, sans-serif;
        max-width: 800px;
        margin: 0 auto;
        padding: 20px;
        background-color: white;
    }
    
    h1 {
        color: #333;
        text-align: center;
        margin-bottom: 30px;
    }
    
    h3 {
        color: #333;
        margin-top: 30px;
    }
    
    /* Override universal selector for headings to make them more readable */
    h1, h3 {
        color: #333 !important;
    }
    ```
 
 
 You should now see the headings, content blocks, and table styled according to the different CSS selectors (element, ID, class, and more).
