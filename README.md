# SpaGFT modified TACCO

TACCO (Transfer of Annotations to Cells and their COmbinations) is a python framework for working with categorical and compositional annotations for high-dimensional observations, in particular for transferring annotations from single cell to spatial transcriptomics data. We use SpaGFT to modify TACCO and achieve a better performance.

## How to install environment for TACCO_SpaGFT

### 1. Install enviroment for TACCO

The simplest way to install TACCO is to create a clean environment with `conda` using the `environment.yml` file from the TACCO repository:

```bash
conda env create -f ./environment.yml
```
(For older versions of `conda` one needs to download the `environment.yml` and use the local file for installation.)

### 2. Install enviroment for SpaGFT

Install SpaGFT from pypi via `pip`:

```bash
pip install SpaGFT
```

We recommend [jupyter](https://jupyter.org/) for interactive usage. It can be installed and configured by
```bash
conda install jupyter
python -m ipykernel install --user --name=spagft_tacco_env --display-name=spagft_tacco_env
```

## How to use modified TACCO

Modified TACCO features a straightforward API for the compositional annotation of one dataset, given as an anndata object `adata`, with a categorically annotated second dataset, given as an anndata object `reference`.

```python
import tacco as tc
tc.tl.annotate(adata, reference,S_spagft=24, lamada_mtb=0.8, annotation_key='my_categorical_annotation',result_key='my_compositional_annotation', method='OTGFT',multi_center=10)
```
where `'my_categorical_annotation'` is the name of the categorical `.obs` annotation in `reference`, `'my_compositional_annotation'` is the name of the new compositional `.obsm` annotation to be created in `adata`, and `'OTGFT'` is the `TACCO_SpaGFT` method name in the modified TACCO API.

If you want to compare our modified TACCO, you can use `SpaGFT_TACCO_example.ipynb`, in which the example used is from [the tutorial of initial TACCO](https://simonwm.github.io/tacco/).

