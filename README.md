# Data Annotation and ML Model Training Workflow

This set of instructions will guide you through the process of setting up the tools necessary for labeling data and training a machine learning model using your annotations. The workflow involves installing Anaconda, mmdetection, and Label Studio.

## Table of Contents
- [Installations](#installations)
- [Launching Label Studio (run_label_studio.py)](#launching-label-studio-run_label_studiopy)
- [Annotation workflow (workflow.py)](#annotation-workflow-workflowpy)


## Installations

### Anaconda

1. Download and install [Anaconda](https://www.anaconda.com/download/).

### MMDetection

This installation is done either in a Anaconda Prompt window (Windows), or a regular terminal window (Mac). Enter the following commands:
   
```bash
conda activate # Mac only
conda create --name openmmlab-2x python=3.8 -y conda activate openmmlab-2x

conda install pytorch==1.13.1 torchvision==0.14.1 torchaudio==0.13.1 cpuonly -c pytorch
# Note: newer versions of pytorch do not have wheel for compatible mmcv versions

pip install -U openmim
mim install mmcv-full
# Note: install mmcv-full version 1.7.1 by default, mmcv version 2.0.0 is also available but not compatible

mim install mmengine
# Note: (optional if using mim download for verifying installation, reccomended)

git clone --branch 2.x https://github.com/open-mmlab/mmdetection.git
cd mmdetection
pip install -v -e .
# Note: uninstalling previous version (git clone) required, clone the 2.x branch of mmdetection (version 2.28.0)
```

__Optional:__ To verify installation:

```bash
mim download mmdet --config yolov3_mobilenetv2_320_300e_coco --dest .

python demo/image_demo.py demo/demo.jpg yolov3_mobilenetv2_320_300e_coco.py yolov3_mobilenetv2_320_300e_coco_20210719_215349-d18dff72.pth --device cpu --out- file result.jpg
```

You should see a new image `result.jpg` on your current folder (mmdetection), where bounding boxes are plotted on cars, benches, etc.

__Troubleshooting:__ 

* Incompatibility: newer versions of mmcv (>= 2.0.0) is not compatible with mmdetection version 2.28.0, require uninstalling mmcv and reinstalling earlier versions
* Building wheel: wheel for mmcv is downloaded using the corresponding version of pytorch. If building wheel is not completed (building wheel keeps running for long time), check the [download link](https://download.openmmlab.com/mmcv/dist/{cuda-versioncpu}/torch{version}/index.html) of corresponding pytorch version 
* No module named mmcv._ext : this problem occur if mmcv is install prior to pytorch (e.g. reinstalling pytorch). Fix: create new environment and install in order.

### Label Studio

Enter commands into Anaconda Prompt terminal (Windows), or a regular terminal window (Mac).

```bash
pip install label-studio
label-studio start # To confirm installation
````
This should open Label Studio in your browser. You can safely close the browser and terminal tabs before proceeding.

## Launching Label Studio (run_label_studio.py)

This program protocol allows you to launch Label Studio such that you can easily access local or other data.

The following instructions assume you have completed the above installations.

```bash
conda activate openmmlab-2x
# To use the program, activate a conda environment in which the requirements are installed.


pip install inquirer

cd [Pathname of census-digitization repo.]/detection_model
# Go to the cloned github repository census-digitization. If you have not cloned the repository, do so now.

python run_label_studio.py
# Opens label_studio with the local data.
````

You will be asked for a port number for running the program. If you do not have another program running on port 8080, you may use this default option.

If you wish to import data into a project, you should choose to start Label Studio with local storage. Specify the location of your data through the data_storage_path variable in the `[IMPORT_DATA]` section of the configuration file (`detection_config.ini`) provided in the repository. Alternatively, enter the path in the terminal when asked. If you are not using the provided configuration file template, you should also provide the path to your configuration file.

## Annotation workflow (workflow.py)

This program allows you to create a label studio project, import local data into that project, and once labelled, to train a ML algorithm based on the data.

The instructions assume you have completed the above installations. Before proceeding, you should also run run_label_studio.py (above). While that program is active in the terminal, enter the following lines into a new terminal window.

```bash
# To use the program, activate a conda environment in which the requirements are installed.
conda activate openmmlab-2x

pip install inquirer

# Go to the cloned github repository census-digitization.
cd [Pathname of census-digitization repo]/detection_model

python workflow.py
````
The workflow is based on the configuration file that is a part of the repository (detection_config.ini). Before executing a task using the program, you should fill in the relevant section of the provided template.

There are four functionalities that help you manage your project (choose action by pressing space).

### Initiating a Label Studio project

You will be asked whether to use a configuration file for creating a new project. This is highly recommended. Fill in the required fields `[LABEL_STUDIO]` and `[INITIATE_PROJECT]` in the configuration file.

Next, you will be asked a path to your configuration file. You can leave this empty if you are using the provided configuration file.

You will be asked whether you want to create a label configuration file based on your entries. The default option is Yes.

Your project will be assigned a project id upon creation. You can choose to overwrite your configuration file to include this id.

After refreshing your browser, the new project should be visible in Label Studio.

### Importing local data to your project 

This allows you to annotate local data. Fill in the `[IMPORT_DATA]` section of the configuration file (recommended). Alternatively, provide information in the terminal.

Note that you can specify which project to import into through the ‘project id’ variable in the `[INITIATE_PROJECT]` section of the configuration file.

You will be asked whether to exclude duplicates and your preferred import method.

Your data will now be visible as tasks within the specified Label Studio project. You can annotate the data and come back to it later to export.

If you are unhappy with your labeling configuration, you may change the template and labels in Label Studio:
***
Settings > Labeling Interface > Browse Templates
***
This should be done before completing annotations using the previous configuration.

### Removing tasks from your project

Fill in the `[REMOVE_TASKS]` section of the configuration file, specifying a list of task id:s or a list of file names to remove from your project. You will choose between these options in the terminal. Additionally, you may remove all tasks in a project.

Again, you can specify which project to remove tasks from using the ‘project id’ variable in the `[INITIATE_PROJECT]` section of the configuration file.

### Exporting data from your project

Using the configuration file, specify your destination path and export type. The export type will depend on your data.

If the exported file is in `.zip` format, you can choose to unzip. You can unzip either in the parent directory or a newly created folder (annotation_coco). Finally, you can choose to include the data (not annotated) in a folder alongside the annotation results

### Training a ML model using your annotations

#### *Preparation:*

This functionality allows you to use the mmdetection framework to train a ML model using your annotated data as training and validation.

Again, it is highly recommended that you use the provided detection_config.ini file to configure the task. Here, you can provide the split of training, validation, and testing datasets, provide pathnames etc.)

You will have to choose a configuration for the detection model. It is recommended to use a [model configuration file](https://mmdetection.readthedocs.io/en/v2.28.0/tutorials/config.html) provided by mmdetection. 

If you use a model configuration file, you can overwrite essential variables easily in the detection_config.ini file.

#### *Workflow:*

After running workflow.py and selecting `[X] Train model`, you will be asked wheter to use a configuration file, and a path to this file if you are not using the provided template.

Then, you will be asked whether to write separate files for the different datasets (training, validation, testing). This is recommended.

You will be asked whether to add 'ignore' categories to configured datasets. In most cases, answering ‘no’ is appropriate[^1].

You can then choose to automatically adjust the model based on configured datasets. This allows the framework to adapt to each dataset during training and evaluation, simplifying the workflow and removing the need for manual fine-tuning.

[^1]: "ignore" categories refer to specific object categories or classes in your dataset that should be ignored during the training and evaluation of the object detection model. This is particularly useful when dealing with scenarios where certain objects may be present in images but are not of interest for the particular task at hand.

#### *Results:*

