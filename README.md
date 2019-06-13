# David Berga's metrics code #

This is the Matlab saliency code able to process saliency maps and metrics. Images, fixation maps and saliency maps should be saved in the following directories (by default):<br/>
    
    input/images/DATASET_NAME
    input/bmaps/DATASET_NAME
    input/dmaps/DATASET_NAME
    input/smaps/DATASET_NAME/MODEL_NAME
    
Although only necessary folders for computing saliency metrics are "images", "bmaps", "dmaps" and "smaps". Other metrics require region binary masks "mmaps" or scanpaths ("scanpaths" for GT, "smaps/DATASET_NAME/MODEL_NAME/scanpaths" for model scanpaths).<br/>
To run any dataset, copy your dataset files and make sure you have the same folder structure as in "test".<br/>
        
Run metrics from "input/", Example for test dataset:  
    
    main('test',0);

Export csv in "output/", Example: 
    
    see_results.m

Run saliency maps from "models/", Example for test dataset: 

    get_smaps('models',{'test'});
    
Before running saliency models, first try to delete them, e.g. "input/smaps/test/AIM"<br/>
Note: To add another model, make sure each model runs a matlab file with same format (input and output of function) and prefix "saliency_MODEL_NAME" as in "saliency_aim.m". You can also run shell commands through matlab for python-based models___<br/>

# Download Datasets #

Use the shell commands (download_parse_datasets/DATASET_NAME/download.sh) for downloading and parsing eye-tracking data (images, fixation maps and scanpaths) of previous experiments of Toronto (Bruce & Tsotsos, 2006), MIT1003 (Judd et al., 2009), KTH (Kootstra et al., 2011), CAT2000 Pattern (Borji & Itti, 2015) and SID4VAM (Berga et al., 2019).
    
# Fork of Zoya Bylinskii's metrics code #

Code is found in "include/saliency-master/"

Various code related to the MIT saliency benchmark website http://saliency.mit.edu will be found there. 
Please contact saliency@mit.edu with any questions.
If you use any of this code, please cite: 
<pre>
@article{salMetrics_Bylinskii,
    title    = {What do different evaluation metrics tell us about saliency models?},
    author   = {Zoya Bylinskii and Tilke Judd and Aude Oliva and Antonio Torralba and Fr{\'e}do Durand},
    journal  = {arXiv preprint arXiv:1604.03605},
    year     = {2016}
}
</pre>
