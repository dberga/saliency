# David Berga's metrics code #

This is the Matlab saliency code able to process saliency maps and metrics. Images, fixation maps and saliency maps should be saved in the following directories (by default):
    input/images/DATASET_NAME
    input/bmaps/DATASET_NAME
    input/dmaps/DATASET_NAME
    input/smaps/DATASET_NAME/MODEL_NAME
Although only necessary folders for computing saliency metrics are "images", "bmaps", "dmaps" and "smaps". Other metrics require region binary masks "mmaps" or scanpaths ("scanpaths" for GT, "smaps/DATASET_NAME/MODEL_NAME/scanpaths" for model scanpaths).
To run any dataset, copy your dataset files and make sure you have the same folder structure as in "test".
        
Run metrics from "input/"

    Example for test dataset:  main('test',0);

Export csv in "output/"

    Example: see_results.m

Run saliency maps from "models/"
    ___First try to delete "input/smaps/test/AIM"___
    Example for test dataset: get_smaps('models',{'test'});
    ___Note: To add another model, make sure each model runs a matlab file with same format (input and output of function) and prefix "saliency_MODEL_NAME" as in "saliency_aim.m". You can also run shell commands through matlab for python-based models___
    
# Fork of Zoya Bylinskii's metrics code #

#### include/saliency-master/ ####

Various code related to the MIT saliency benchmark website http://saliency.mit.edu will be found here. 
Please contact saliency@mit.edu with any questions.
If you use any of this code, please cite: 
<pre>
@misc{mit-saliency-benchmark,
  author       = {Zoya Bylinskii and Tilke Judd and Fr{\'e}do Durand and Aude Oliva and Antonio Torralba},
  title        = {MIT Saliency Benchmark},
  howpublished = {http://saliency.mit.edu/}
}
@article{salMetrics_Bylinskii,
    title    = {What do different evaluation metrics tell us about saliency models?},
    author   = {Zoya Bylinskii and Tilke Judd and Aude Oliva and Antonio Torralba and Fr{\'e}do Durand},
    journal  = {arXiv preprint arXiv:1604.03605},
    year     = {2016}
}
</pre>
