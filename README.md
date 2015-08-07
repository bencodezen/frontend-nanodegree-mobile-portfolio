# Website Performance Optimization Project

This is the fourth project on the Udacity - Front End Development Nanodegree program. The challenge of this project is to optimize the critical rendering path and make this page render as quickly as possible! 

## Getting Setup

### Live Site

- [http://bencodezen.github.io/website-optimization/](http://bencodezen.github.io/website-optimization/)

### Local Environment

1. Clone the repository in your desired directory
2. To inspect the site on your phone and/or to analyze it with PageInsights, you can run a local server

  ```bash
  $> cd /path/to/your-project-folder
  $> python -m SimpleHTTPServer 8080
  ```

3. Download and install [ngrok](https://ngrok.com/) to make your local server accessible remotely.

  ``` bash
  $> cd /path/to/your-project-folder
  $> ngrok 8080
  ```

4. Persue the site by going to `http://localhost:8080`

5. Copy the public URL ngrok gives you to run it through PageSpeed Insights!

## Optimizations

###Part 1: Improving PageSpeed Insights Score: index.html

- Move analytics scripts to the bottom of the page
- Add `media="print"` attribute to `print.css` to reduce requests
- Compressed `profilepic.jpg` and `pizzeria.jpg` to reduce the file size
- Inline `style.css` to reduce requests since the styles are not shared with other pages
- Import Google font in CSS to also reduce number of requests

###Part 2: Optimize Frames per Second in pizza.html

- Consolidate size calculations for pizzaResizer
- Switch out `querySelector` functions for the respective `getElement(s)By` functions (i.e., ID or class)
- Reduced WET selectors by extracting them to a variable to reduce the number of queries
- Moved all moving pizzas to their own layers
- Number of pizzas generated optimized with calculations based on the page as opposed to an arbitrary number
