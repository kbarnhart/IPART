# Image-Processing based Atmospheric River Tracking (IPART) algorithms

## Dependencies

* Python2.7 or Python3.7.
* CDAT (Climatic Data Analysis Tool): (https://github.com/CDAT/cdat).
* numpy (developed in 1.16.5 in py2, tested 1.18.1 in py3)
* scipy (developed in 1.2.1 in py2, tested 1.4.1 in py3)
* matplotlib (2.2.3 for both py2 and py3, having [issues](https://github.com/matplotlib/matplotlib/issues/12820) with 3.1.3)
* basemap (developed in 1.2.0 in py2, tested 1.2.0 in py3)
* pandas (developed in 0.23.4 in py2, tested 1.0.3 in py3)
* networkx (developed in 1.11 and 2.2 in py2, tested 2.4 in py3)
* scikit-image (developed in 0.14.2 in py2, tested 0.16.2 in py3)


## Installation

Recommend building the Python environment using [Anaconda](https://www.anaconda.com/distribution/).

### Option 1, create conda env using environment file

After Anaconda installation, git clone this repository:

```
git clone https://github.com/ihesp/IPART
```

Then build a new conda environment using the environment file provided. For
Python 2.7:

```
cd IPART
conda env create -f environment_py2.yml
```

This creates a new environment named `ipartpy2`. Activate the environment using

```
conda activate ipartpy2
```

After that, you can check the list of packages installed by

```
conda list
```

Similarly for Python 3.7, use

```
conda env create -f environment_py3.yml
```


### Option 2, manually install all packages

After Anaconda installation, create a working environment:

```
conda create -n ipartpy3 python=3.7
conda activate ipartpy3
```

This creates a Python environment named "ipartpy3" with Python version 3.7.

Then install the above listed dependencies, e.g.

```
conda install numpy
```

This installs the current latest version of `numpy`. Most likely the latest versions will work, in case of compatibility issues, consider forcing a given version of a package, e.g.

```
conda install matplotlib=2.2.3
```

For installation of `CDAT`, checkout the [installation guides](https://github.com/CDAT/cdat/wiki/Install). This is likely the most difficult package to install, and consider leaving it to the end. To verify the CDAT installation, in a python session:

```
import cdms2
import MV2
import cdutil
```

If nothing prints out, the installation is successful. In case of errors, also consider their [partial installation instructions](https://github.com/CDAT/cdat/wiki/Additional-Installation-Configurations). Only the `cdms2` and `cdutil` modules are needed, the `vcs` module is not required.

Lastly, install `ipart`:

```
conda install -c guangzhi ipart
```

### Option 3, install from conda (experimental)

For py2:

```
conda create -n ipartpy2 python=2.7 -c guangzhi -c conda-forge ipart
```

For py3 (good luck with `cdms2` and `cdutil`):

```
conda create -n ipartpy3 python=3.7 -c guangzhi -c conda-forge ipart
```

Then activate the environment:

```
conda activate ipartpy2
```

or

```
conda activate ipartpy3
```



## tests

To validate installation, issue a new Python session and run

```
import ipart
```

If nothing prints out, installation is successful.

The `tests` folder also contains a number of `unittest`s, to run them:

```
python -m unittest discover -s tests
```

## Documentation

Further documentation can be found at [https://ipart.readthedocs.io/en/latest/](https://ipart.readthedocs.io/en/latest/).


## Example use case


| ![fig3](joss/fig3.png) |
| :--: |
|*(a) The IVT field in kg/m/s at 1984-01-26 00:00 UTC over the North Hemisphere. (b) the IVT reconstruction field (IVT_rec) at the same time point. (c) the IVT anomaly field (IVT_ano) from the THR process at the same time point.*|

| ![](joss/ar_track_198424.png) |
| :--: |
|*Locations of a track labelled "198424" found in year 1984. Black to yellow color scheme indicates the evolution.*|



## Inventory

* docs: readthedocs documentation.
* ipart: core module functions.
* notebooks: a series of jupyter notebooks illustrating the major functionalities of the package.
* scripts: example computation scripts. Can be used as templates to quickly develop your own working scripts.



## Contribution

If you encounter problems or would like to help improve the code, please don't
hesitate to fire up an issue or pull request.



