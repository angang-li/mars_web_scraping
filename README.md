# Mission to Mars

- [Mission to Mars](#mission-to-mars)
  - [1. Project summary](#1-project-summary)
  - [2. File descriptions](#2-file-descriptions)
  - [3. Instructions to run the web application](#3-instructions-to-run-the-web-application)
  - [4. Python version and libraries](#4-python-version-and-libraries)
  - [5. Web app screenshots](#5-web-app-screenshots)

## 1. Project summary

A web application that scrapes various websites for real-time data related to the Mission to Mars, stores scraped data in MongoDB, and displays the latest information in a single HTML page. Check out the web application [here](https://mars-web-scraper.herokuapp.com/)!

## 2. File descriptions

- `mission_to_mars.ipynb`: the Jupyter Notebook file that outlines all the scraping.

  * Scrape latest news title and paragraph text from the [NASA Mars News Site](https://mars.nasa.gov/news/).
  * Scrape the image url for the current featured Mars Image from [JPL Featured Space Image](https://www.jpl.nasa.gov/spaceimages/?search=&category=Mars).
  * Scrape the latest Mars weather tweet from the [Mars Weather twitter account](https://twitter.com/marswxreport?lang=en) 
  * Scrape Mars metrics (e.g. diameter, mass) from the [Mars Facts webpage](http://space-facts.com/mars/).
  * Scrape Mars hemispheres images and names from the [USGS Astrogeology site](https://astrogeology.usgs.gov/search/results?q=hemisphere+enhanced&k1=target&v1=Mars).

- `scrape_mars.py`: declares a function called `scrape` that executes all the above scraping and returns the scraped data.

- `app.py`: creates an app route called `/scrape` that calls the `scrape` function and store data in Mongo database; creates a root route `/` that queries the Mongo database and pass the mars data into an HTML template to display the data.

- `templates`
  - `index.html`: a template HTML file that display all data in the appropriate HTML elements.

- `static`
  - `css`
    - `reset.css`, `style.css`: CSS stylesheets.

## 3. Instructions to run the web application

1. Clone this repository.
2. Make sure MongoDB is installed. [Here](Installing-MongoDB.md) is installation instruction from Northwestern Data Science Bootcamp.
3. In terminal (or command line in Windows), type `mongod`
4. Open another terminal window, navigate to `mars-web-scraping/` directory (where this README file is located).
5. In the terminal, type `python app.py`. The webpage will display on local browser.

## 4. Python version and libraries

The code was developed using the Anaconda distribution of Python version 3.6. The following dependencies were used.

`pandas` <br>
`Flask` <br>
`BeautifulSoup` <br>
`splinter` <br>
`Flask-PyMongo`

## 5. Web app screenshots

<img src="Images/webpage1.png" alt="webpage screenshot 1" style="width: 60%; display: block; margin: auto;"><br>
<img src="Images/webpage2.png" alt="webpage screenshot 2" style="width: 60%; display: block; margin: auto;"><br>
<img src="Images/webpage3.png" alt="webpage screenshot 2" style="width: 60%; display: block; margin: auto;">