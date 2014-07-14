PiLR Dashboard Template
============

Description
-----------
The pilr_dashboard_panel function in the pilrdash package is called by all dashboards in
order to generate their display. It extracts a specified dataset from the PiLR server, and 
applies the specified function to the dataset. Results can be returned to the dashboard in 
various formats, such as Vega (for ggvis), static images, or a generic HTML format. This template
follows the necessary format for a function to be passed to pilr_dashboard_panel.   

pilr_dashboard_panel arguments
---------
Each of these arguments can be passed into the pilr_dashboard_panel function:  
`package_function` Function to be applied to the dataset  
`package_url` URL pointing to the package on GitHub  
`data` List of arguments for finding the dataset (data_set, schema, project, pilr_api_server)  
`return_type` Type to be returned from the function (r:vega, r:image, or r:html)  
`filter_params` List of parameters for choosing subsets of a dataset (participant, group, date)  
`dashboard_params` Dashboard parameters(?)  

Creating Your Function
----------------------
Custom dashboard functions can be created in R and hosted as a package on GitHub. To make this 
process as easy as possible, a dashboard function template can be cloned from <http://linktopackage.com>. 
All custom functions must include these three arguments:  
`data` the dataframe read in from a PiLR project  
`params` a list of all arguments sent to pilr_dashboard_panel above  
`...` a generic that allows any other argument to be passed through  
You may wish to update documentation for your function. If so, you can use the roxygen2 package to do this, 
as well as manually editing the DESCRIPTION file in the template.  

Access Code
-----------
When testing your function locally, pilr_dashboard_panel needs to read in your PiLR API
consumer key from a secure file. Create a text file named "pilrsecret.txt" under the folder
"R" in your function's package. Paste your access code in this file, followed by a blank line. 
Our template provides a .gitignore file which causes pilrsecret.txt to not be committed to a repo.  
