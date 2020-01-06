## Conda

- environments
  - list: `conda env list`
  - create: `conda create --name <envname> pyton=3.6 matplotlib`
- packages
  - search online: `conda search <package-name>`
  - list installed: `conda list` as URLs: `--explicit`
  - add conda-forge: `conda config --add channels conda-forge`


## ipython kernels

- list: `jupyter kernelspec list`
- install Python kernel: `conda install ipykernel` followed by `python -m ipykernel install --user --name <env-name>`

## Jupyterlab

- manage extensions:
  - `jupyter labextension list`
  - `jupyter labextension install my-extension`
  - `jupyter labextension uninstall my-extension`
- build: `jupyter lab clean && jupyter lab build`
- run: `jupyter lab @`

## nbconvert
`jupyter nbconvert`
- `--no-input` - omit imput cells
