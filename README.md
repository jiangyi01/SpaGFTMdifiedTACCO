# TACCO: Transfer of Annotations to Cells and their COmbinations

TACCO is a python framework for working with categorical and compositional annotations for high-dimensional observations, in particular for transferring annotations from single cell to spatial transcriptomics data. We use SpaGFT to modify TACCO and achieve a better performance.

## How to install environment for modified TACCO

### 1. Install enviroment for TACCO

The simplest way to install TACCO is to create a clean environment with `conda` using the `environment.yml` file from the TACCO repository:

```
conda env create -f ./environment.yml
```
(For older versions of `conda` one needs to download the `environment.yml` and use the local file for installation.)

### 2. Install enviroment for SpaGFT

Install SpaGFT from pypi via `pip`:

```
pip install SpaGFT
```

## How to use modified TACCO

Modified TACCO features a straightforward API for the compositional annotation of one dataset, given as an anndata object `adata`, with a categorically annotated second dataset, given as an anndata object `reference`.

```
import tacco as tc
tc.tl.annotate(adata, reference,S_spagft=24, lamada_mtb=0.8, annotation_key='my_categorical_annotation',result_key='my_compositional_annotation', method='OTGFT',multi_center=10)
```

If you want to compare our modified TACCO, you can use `SpaGFT_TACCO_example.ipynb`, in which the example used is from tutorial of Initial TACCO GitHub.

