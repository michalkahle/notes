## Package managers
|                             | apt                | conda  | pip                | npm   |
| ---                         | ---                | ---    | ---                | ---   |
| list installed packages     | `list --installed` |        | `list`             |       |
| search for package in repos | `search`           | search | NA                 |       |
| install package             | `install`          | install| `install`          |install|
| upgrade package             | -                  |        | `install -U <pkg>` |       |
| upgrade all packages        | `upgrade`          |        | NA                 |       |
| uninstall package           | `remove <pkg>`     |        | `uninstall`        |       | 
| uninstall including config  | `purge <pkg>`      |        |                    |       |
| show information about pkg  | `show <pkg>`       |        | `show`             |       |


## Virtual environments
|                             | venv               | conda
| ---                         | ---                | ---                       |
| create virtual environment  |                    |create -n `name` [packages]|


## Linux
- check hash: `echo '<hash> <filename>' | sha256sum -c -`
- check LVM physical volume used and free space: `sudo pvdisplay`
- increase LV partition size: `lvextend -L+1G /dev/mapper/vg0-usr` and then: `resize2fs /dev/mapper/vg0-usr`
- ssh key autentication:
  - create key pair: `ssh-keygen`
  - copy id_rsa.pub to server: `ssh-copy-id username@hostname`
- ssh tunnel (use sudo if local port < 1000): `sudo ssh -L 80:localhost:8888 user@host`
- turn capslock into escape: `dconf write /org/gnome/desktop/input-sources/xkb-options "['caps:escape']"`

## apt
- find online: `apt search <package_name>`
- show details: `apt show <package_name>`
- install, remove, remove with config: `apt install <package_name>`, `apt remove <package_name>`, `apt purge <package_name>`
- refresh repo index: `apt update`
- upgrade all upgradeable: `apt upgrade`
- remove unnecessary: `apt autoremove`

## Conda
- add conda-forge to channels: `conda config --prepend channels conda-forge`
- environments
  - list: `conda env list`
  - create: `conda create --name <envname> pyton=3.6 matplotlib`
  - remove: `conda remove --name <envname> --all`
  - export / clone: `conda env export > my_env.yml` / `conda env create -f my_env.yml`
- packages
  - search online: `conda search <package-name>`
  - list installed: `conda list` as URLs: `--explicit`
  - list changes: `conda list --revisions`

## Jupyter
### kernels
- install Python kernel: `conda install ipykernel` followed by `python -m ipykernel install --user --name <env-name>`
- list: `jupyter kernelspec list`

### Jupyterlab
- manage extensions:
  - `jupyter labextension list`
  - `jupyter labextension install my-extension`
  - `jupyter labextension uninstall my-extension`
- build: `jupyter lab clean && jupyter lab build`
- run: `jupyter lab @`

### nbconvert
`jupyter nbconvert`
- `--to html` or `--to pdf`
- `--no-input` - omit imput cells
- `--template printviewlatex.tplx`
## TeX
- install Tex live: `sudo apt install texlive` or `sudo apt install texlive-full` (> 4GB!)
- update: `tlmgr update --self`, then `tlmgr update --all`
- install package: `tlmgr install <package_name>`
### Citations
Bibliography file
```bibtex
@misc{ Nobody06,
       author = "Nobody Jr",
       title = "My Article",
       year = "2006" }
```
LaTeX file:
```latex
\documentclass[11pt]{article}
\usepackage{cite}

\begin{document}

\title{My Article}
\author{Nobody Jr.}
\date{Today}
\maketitle

Blablabla said Nobody ~\cite{Nobody06}.

\bibliography{mybib}{}
\bibliographystyle{plain}
\end{document}
```




