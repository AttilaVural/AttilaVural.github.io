The are currently three ways to display a Bokeh plot:

Bokeh Standalone:
* Compiles into a html file.
* You must configure ajax calls to update the data
* You must set up your own server for providing data

Server:
* Server page...
* automatically creates handlers
* Runs as a deamon in the background to recieve data requests

Raw JS: 
* Not relevant

The official documentation [(link)](https://docs.bokeh.org/en/latest/docs/reference/models/sources.html) explains the difference between the Application (Server) and the Documents (Standalone) as follows:
_Standalone documents: These documents don’t require a Bokeh server to work. They may have many tools and interactions such as custom JavaScript callbacks but are otherwise nothing but HTML, CSS, and JavaScript. These documents can be embedded into other HTML pages as one large document or as a set of sub-components with individual templating._

_Bokeh applications: These applications require a Bokeh server to work. Having a Bokeh server lets you connect events and tools to real-time Python callbacks that execute on the server. For more information about creating and running Bokeh apps, see Bokeh server._
  
  
  
But this does not mention anything about wanting a standalone plot with the possibility of fetching new data....
But this does: https://docs.bokeh.org/en/latest/docs/reference/models/sources.html

_The AjaxDataSource can be especially useful if you want to make a standalone document (i.e. not backed by the Bokeh server) that can still dynamically update using an existing REST API._

And they link to this code example, which does pretty much what I want:
  https://github.com/bokeh/bokeh/blob/3.0.3/examples/basic/data/ajax_source.py
