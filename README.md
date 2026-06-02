# Run metrics code #

This is the Matlab saliency code able to process saliency maps and metrics. 

Run metrics from "input/", Example for test dataset:  
    
    main('test',0);

This will export a csv in "output/" (main.m automatically runs see_results.m after storing results).
    
Images, fixation maps and saliency maps should be saved in the following directories (by default):<br/>
    
    input/images/DATASET_NAME
    input/bmaps/DATASET_NAME
    input/dmaps/DATASET_NAME
    input/smaps/DATASET_NAME/MODEL_NAME
    
Although only necessary folders for computing saliency metrics are "images", "bmaps", "dmaps" and "smaps". Other metrics require region binary masks "mmaps" or scanpaths ("input/smaps/DATASET_NAME/scanpaths" for GT, "input/smaps/DATASET_NAME/MODEL_NAME/scanpaths" for model scanpaths).<br/>
To run any dataset, copy your dataset files and make sure you have the same folder structure as in "test".<br/>
   
# Run Saliency models #

Run saliency maps from "models/", Example for test dataset: 

    get_smaps('models',{'test'});
    
Before running saliency models, first try to delete them, e.g. "input/smaps/test/SIM"<br/>
Note: To add another model, make sure each model runs a matlab file with same format (input and output of function) and prefix "saliency_MODEL_NAME" as in "saliency_sim.m". You can also run shell commands through matlab for python-based models. We have included an example code of all saliency models to make your tests (try to run install.sh in every subfolder before running them).
<img width="619" height="611" alt="image" src="https://github.com/user-attachments/assets/bdd2d2db-271f-4184-ad81-7e0aea2cae32" />

# Download Datasets #

* Download datasets' GT: Use the shell commands (download_parse_datasets/DATASET_NAME/download.sh) for downloading and moving eye-tracking data (images, binary fixation maps, fixation density maps and scanpaths) of previous experiments of Toronto (Bruce & Tsotsos, 2006), MIT1003 (Judd et al., 2009), KTH (Kootstra et al., 2011), CAT2000 Pattern (Borji & Itti, 2015).\
(or) Download and parse GT: [Here](https://drive.google.com/drive/folders/1Gur2DwPdOB7xBJNWCkiFaDCvqWY-mx3y?usp=sharing) are the parsers for ground truth data for each raw data from previous datasets.\
(or) Download the already parsed ground truth: [Here](https://drive.google.com/drive/folders/11W_wV_HCFfWEghzpW7kK3ikSmrrogne1?usp=sharing)\
You can download the saliency maps from [Here](https://drive.google.com/drive/folders/1yPJyHRD2tHuqYAvlJJCgt0vn7njgby0g?usp=sharing).

* For SID4VAM synthetic dataset (Berga et al., 2018, 2019), download all data (images and ground truth) [Here](https://drive.google.com/drive/folders/11VYqWsy0AY1aO7IJYqs_7ITJW8d-n5wi?usp=sharing).
<img width="600" height="509" alt="image" src="https://github.com/user-attachments/assets/40406ce0-a299-4bbb-a059-dd22a395e486" />

# Generate Synthetic Images with Salient Targets #

To synthesize your own dataset or image samples of pop-out/conspicuous targets (also their binary masks), check [SIG4VAM (Synthetic Image Generator for Visual Attention Modeling)](https://github.com/dberga/sig4vam).

<img width="624" height="174" alt="image" src="https://github.com/user-attachments/assets/eff7dc7d-b5cb-446c-8808-221248c18e41" />

# This is a fork of official MIT metrics code #

Forked code from https://github.com/cvzoya/saliency is found in "include/saliency-master/"

This specific benchmark is part of work done in the following papers, please consider to cite:
```

@inproceedings{Berga2019_ICCV,
  title = {SID4VAM: A Benchmark Dataset With Synthetic Images for Visual Attention Modeling},
  url = {http://dx.doi.org/10.1109/ICCV.2019.00888},
  DOI = {10.1109/iccv.2019.00888},
  booktitle = {2019 IEEE/CVF International Conference on Computer Vision (ICCV)},
  publisher = {IEEE},
  author = {Berga,  David and Vidal,  Xose Ramon Fernandez and Otazu,  Xavier and Pardo,  Xose M.},
  year = {2019},
  month = Oct,
  pages = {8788–8797}
}
@article{Berga_2019_VisRes,
title = "Psychophysical evaluation of individual low-level feature influences on visual attention",
journal = "Vision Research",
volume = "154",
pages = "60 - 79",
year = "2019",
issn = "0042-6989",
doi = "https://doi.org/10.1016/j.visres.2018.10.006",
url = "http://www.sciencedirect.com/science/article/pii/S0042698918302207",
author = "David Berga and Xosé R. Fdez-Vidal and Xavier Otazu and Víctor Leborán and Xosé M. Pardo"
}
@article{Berga_neurocomputing2020,
    title = {Modeling bottom-up and top-down attention with a neurodynamic model of V1},
    journal = {Neurocomputing},
    volume = {417},
    pages = {270-289},
    year = {2020},
    issn = {0925-2312},
    doi = {https://doi.org/10.1016/j.neucom.2020.07.047},
    url = {https://www.sciencedirect.com/science/article/pii/S0925231220311553},
    author = {David Berga and Xavier Otazu}
}
@article{Berga_neco2022,
    author = {Berga, David and Otazu, Xavier},
    title = "{A Neurodynamic Model of Saliency Prediction in V1}",
    journal = {Neural Computation},
    volume = {34},
    number = {2},
    pages = {378-414},
    year = {2022},
    month = {01},
    issn = {0899-7667},
    doi = {10.1162/neco_a_01464},
    url = {https://doi.org/10.1162/neco\_a\_01464},
    eprint = {https://direct.mit.edu/neco/article-pdf/34/2/378/1982874/neco\_a\_01464.pdf},
}
```
Various code related to the MIT saliency benchmark website http://saliency.mit.edu will be found there. 
Please contact saliency@mit.edu with any questions.
If you use any of this code, please cite: 
```
@article{salMetrics_Bylinskii,
    title    = {What do different evaluation metrics tell us about saliency models?},
    author   = {Zoya Bylinskii and Tilke Judd and Aude Oliva and Antonio Torralba and Fr{\'e}do Durand},
    journal  = {arXiv preprint arXiv:1604.03605},
    year     = {2016}
}
```
