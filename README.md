# Image Quantification 101

### To use
1. Create conda environment from yaml file:
    ```
    conda env create -f imagequant101_env.yml
    ```

2. Activate environment:
    ```
    source activate imagequant101
    ```
    
3. Start jupyter server:
    ```
    jupyter notebook
    ```
    
4. Explore and modify the various `.ipynb` notebooks

5. Answer sheets can be found on the `solutions` folder. To run them, simply move the [Solution] notebook you would like to run to the base `imagequantification101` repository.

### Troubleshooting
If the `imagequant101_env.yml` fails to install for whichever reason, try to create it manually with the following:

    conda create -y -n imagequant101 -c conda-forge python=3.9
    source activate imagequant101
    pip install jupyter
    pip install imageio
    pip install scikit-image
    pip install scikit-learn
    pip install matplotlib
    pip install pandas
    pip install seaborn
    pip install pyefd

### To cite
If you use the exercise notebooks from this tutorial, please acknowledge it as follows:
> Uhlmann, V. (2022). Image Quantification 101 Tutorial. [github.com/uhlmanngroup/imagequantification101](https://github.com/uhlmanngroup/imagequantification101)

### Further resources
* Miura, K. & Sladoje, N. (2020). Bioimage Data Analysis Workflows. [doi.org/10.1007/978-3-030-22386-1](https://doi.org/10.1007/978-3-030-22386-1)
* Bankhead, P. (2022). Introduction to Bioimage Analysis. [bioimagebook.github.io](https://bioimagebook.github.io/)
* Holmes, S. & Huber, W. (2018). Modern Statistics for Modern Biology. [www.huber.embl.de/msmb](https://www.huber.embl.de/msmb/)

### Acknowledgements
Part of the material from this tutorial was adapted from Paula Balcells' Bachelor Thesis work carried out in the Uhlmann group. 
