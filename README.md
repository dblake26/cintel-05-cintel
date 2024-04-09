# cintel-05-cintel

# P5: Interactive App with Continuous Intelligence
In this module, we introduce aspects of continuous intelligence - outputs updated on a regular basis or in real time as information becomes available. We provide only basic examples, but the principles enable a variety of continous intelligence aspects for many types of dashboards. 

If you decide to try the local development, you'll be able to deploy your live date site using GitHub Pages. To make it easy to build our app from a folder and export the app into the docs folder (for Pages), please move your app.py file into a folder. I named my folder "dashboard", so I have a dashboard/app.py file and no app.py in the root folder. This is a more common organization for Python projects. 

You may develop your app in the browser (recommended if you have NOT had 44-608) or develop your app on your machine locally (recommended if you have had 44-608 and/or prior practice with project virtual environments). 

## Your app.py or dashboard/app.py file should have the following sections:

imports (at the top), e.g., shiny, random, datetime
define a reactive calc to fake new data points
define the Shiny Core app_ui
The overall page options
A sidebar
The main section with ui cards, value boxes, and space for grids and charts
Your app should have similar functionality to this basic example before you begin: 

Basic App: https://github.com/denisecase/cintel-05-cintel-basicLinks to an external site. 

## Customize your requirements.txt
PyShiny Playground already includes all the packages listed below. Please do not add these packages to a requirements.txt running in the Playground - but include them in your requirements.txt that you would use for local development. 

faicons - for Font Awesome free Icons
pandas - for working with tabular data in Python
pyarrow - required by the new pandas
plotly - easy interactive charts
scipy - for the stats linear regression function to build a trend line for our chart
shiny - used to build our web app in Python
shinylive - used to build to our docs folder and host our app on GitHub Pages
shinywidgets - a wrapper for complex widgets like plotly charts

## Run Locally - Initial Start

After cloning your project down to your Documents folder, open the project folder for editing in VS Code.

Create a local project virtual environment named .venv, activate it, and install the requirements.

When VS Code asks to use it for the workspace, select Yes.
If you miss the window, after installing, select from the VS Code menu, View / Command Palette, and type "Python: Select Interpreter" and select the .venv folder.

Open a terminal (VS Code menu "View" / "Terminal") in the root project folder and run these commands (for Windows - the activate command is slightly different Linux/Mac).

```shell
py -m venv .venv
.venv\Scripts\Activate
py -m pip install --upgrade pip setuptools
py -m pip install --upgrade -r requirements.txt
```

Open a terminal (VS Code menu "View" / "Terminal") in the root project folder and run these commands.

```shell
shiny run --reload --launch-browser dashboard/app.py
```

Open a browser to <http://127.0.0.1:8000/> and test the app.

## Run Locally - Subsequent Starts

Open a terminal (VS Code menu "View" / "Terminal") in the root project folder and run these commands.

```shell
.venv\Scripts\Activate
shiny run --reload --launch-browser dashboard/app.py
```

## After Changes, Export to Docs Folder

Export to docs folder and test GitHub Pages locally.

Open a terminal (VS Code menu "Terminal" / "New Terminal") in the root project folder and run these commands.

```shell
shiny static-assets remove
shinylive export dashboard docs
py -m http.server --directory docs --bind localhost 8008
```

Open a browser to <http://[::1]:8008/> and test the Pages app.

## Push Changes back to GitHub

Open a terminal (VS Code menu "Terminal" / "New Terminal") in the root project folder and run these commands.

```shell
git add .
git commit -m "Useful commit message"
git push -u origin main
```

## Enable GitHub Pages

Go to your GitHub repo settings and enable GitHub Pages for the docs folder.
