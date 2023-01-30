# Bokeh Server vs. Standalone Documents
![image](https://user-images.githubusercontent.com/115409427/215541654-841f9ca4-cefd-4ba7-843e-0c4b6220917f.png)

**Goal:** I want to create a interactive front-end to visualize various data KPI scraped from twitter. Requirements:
* I must be able to host it on my github pages blog with some pre-selected sample data.
* It should be able to fetch new data using AJAX calls to a FLASK REST API backend.

To avoid reinventing the wheel, I will use _Bokeh_, which is a open source python library for visualizing data - especially for on web pages.

The are currently three ways to generate and display a Bokeh plot on a web page:

**Bokeh Standalone Documents:**
* Python code generates a static HTML file using the file_html(), save() or show() functions.
* You must configure ajax calls to update the data
* You must set up your own server for providing data

**Bokeh Server Applications:**
* Server page...
* automatically creates handlers
* Runs as a deamon in the background to recieve data requests

**Bokeh vizualizations generated from pure JS:**
* Experimental feature, which we won't delve into right now.

The official documentation [(link)](https://docs.bokeh.org/en/latest/docs/reference/models/sources.html) explains the difference between the Application (Server) and the Documents (Standalone) as follows:
_Standalone documents: These documents don’t require a Bokeh server to work. They may have many tools and interactions such as custom JavaScript callbacks but are otherwise nothing but HTML, CSS, and JavaScript. These documents can be embedded into other HTML pages as one large document or as a set of sub-components with individual templating._

_Bokeh applications: These applications require a Bokeh server to work. Having a Bokeh server lets you connect events and tools to real-time Python callbacks that execute on the server. For more information about creating and running Bokeh apps, see Bokeh server._
  
  
  
But this does not mention anything about wanting a standalone (static) plot with the possibility of fetching new data....
But this does: https://docs.bokeh.org/en/latest/docs/reference/models/sources.html

_The AjaxDataSource can be especially useful if you want to make a standalone document (i.e. not backed by the Bokeh server) that can still dynamically update using an existing REST API._

And they link to this code example, which does pretty much what I want:
  https://github.com/bokeh/bokeh/blob/3.0.3/examples/basic/data/ajax_source.py
