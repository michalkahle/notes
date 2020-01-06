
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
