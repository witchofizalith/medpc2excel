# medpc2excel

medpc2excel is a Python package for convert single or multiple medpc data file into Excels. 
medpc2excel can also return a pandas DataFrame for further analysis

## Installation

I recommend installing an [Anaconda](https://www.anaconda.com/distribution/) distribution of Python -- Choose Python >=3.7. 

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install medpc2excel. Current version is 3.0.9

```bash
pip install medpc2excel
```

To upgrade medpc2excel (package here), run the following in the environment:
```bash
pip install medpc2excel --upgrade
```
## Version updating note
Add data explorer to visualize timestampe data

## Configure *.MPC file

Please include a medpc protocol file (*.MPC) that you used for behavior task.
The file name of this MPC file should be the same as in the medpc data file.
The medpc2excel will open the medpc data file and automatically search the used *.MPC file in the same directory.
In *.MPC file, please explicitly declare each array as below:
```text
<... your MPC code...>

    DIM C =9999  \ Levertype                     
    DIM D =9999  \ PelHLON                       
    DIM E =9999  \ PelHLOFF   
    
<... your MPC code ...>
```

## Running medpc2excel

The most quickest way to start is to open the GUi from a command line terminal in anaconda cmd prompt:

```
python -m medpc2excel
```

You can use data explorer tab to see the raster of each events.
![alt text](https://github.com/cyf203/medpc2excel/blob/master/example/example_fig2.jpg)

You also can import this module and use the function called medpc_read as following
```python
from medpc2excel.medpc_read import medpc_read

f = <file path>

ts_df, log = medpc_read(f, override = True, replace = False) # return a timestamp dataframe and a log string
```

Please download the  ```Example``` folder to your local disk and run the ```medpc2excel_example.py``` to give a try.

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change. 
Please make sure to update tests as appropriate

## Dependencies 

Pandas\
Numpy\
dill\
mplcursors\
openpyxl
