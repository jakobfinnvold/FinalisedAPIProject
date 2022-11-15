# FinalisedAPIProject
Vær og vind med samme sinn

# Requirements
    ## Python packages
    Numpy (version 1.23.4) \cite{numpysource}
    Numpy-stl (version 2.17.1) \cite{numpySTL}
    Pillow (version 9.3) \cite{pillowsource}
    Requests (version 2.28.1) \cite{requestsource}
    SolidPython (version 1.1.3) \cite{solidpythonsource}
    Time 
    OS

    ## Other requirements
    Python 3.8 interpreter or newer (preferred)
    OpenSCAD
    
# How to use:
To use the program, first clone the repository do a desired place on your computer. 
In the cloned folder there will be three python files and one folder containing weather symbols.

To run the program, open a terminal inside the folder and type the following: 
  ```
   python3 master.py
  ```
The user will be promted with a question, asking to enter the desired location of the weather forecast. This is constrained to Norwegian cities only!
When this is entered, the program provides the user with the forecast data and produces an stl file named "yourWeather.stl". This is a 3D-printable model of the weather symbol and the wind speed from the forecast. 

# How the program works
After the user provides an input, the master file informs the weather class of what location is desired. The first method in the class then uses the location to extract longitudal and latitudal coordinates of the location based on frost API provided by Meterologisk Institutt. 

This data is used in the next method to get the forecast from the weatherAPI from Meterologisk Institutt. The method returns both the weather icon symbol string and a float number representing the wind speed. The master file now processes these return values and provides information to the STL generation class. The methods in this class produces 3 stl files, which also are merged inside the same class. These are the bottom plate, the weather symbol and the 3D-text of the wind speed. 

Both the bottom plate and the weather symbol models are made using numpy-stl, and the 3D-text is made using OpenSCAD. 

The final merged stl file is the final product, which as mentioned is fully 3D-printable. 
