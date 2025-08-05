FaceFusion
==========

> Industry leading face manipulation platform.

[![Build Status](https://img.shields.io/github/actions/workflow/status/facefusion/facefusion/ci.yml.svg?branch=master)](https://github.com/facefusion/facefusion/actions?query=workflow:ci)
[![Coverage Status](https://img.shields.io/coveralls/facefusion/facefusion.svg)](https://coveralls.io/r/facefusion/facefusion)
![License](https://img.shields.io/badge/license-OpenRAIL--AS-green)


Preview
-------

![Preview](https://raw.githubusercontent.com/facefusion/facefusion/master/.github/preview.png?sanitize=true)


Windows Installation
------------

### 1. Prepare Your Platform

### GIT

```
winget install -e --id Git.Git
```

### Conda

```
winget install -e --id Anaconda.Miniconda3 --override "/AddToPath=1"
```

### FFmpeg

```
winget install -e --id Gyan.FFmpeg --version 7.0.2
```

### 2. Prepare Your Environment

Initialize conda for your terminal:

```
conda init --all
```

Create the environment:

```
conda create --name facefusion python=3.12 pip=25.0
```

Activate the environment:

```
conda activate facefusion
```

### 3. Install Your Accelerator


### CUDA

Compatible with NVIDIA graphic cards:

```
conda install nvidia/label/cuda-12.9.1::cuda-runtime nvidia/label/cudnn-9.10.0::cudnn
```

### TensorRT

Suitable for high performance NVIDIA graphic cards:

```
pip install tensorrt==10.12.0.36 --extra-index-url https://pypi.nvidia.com
```

### OpenVINO

Suitable for Intel Arc graphic cards:

```
conda install conda-forge::openvino=2025.1.0
```

### 4. Download Your Copy

Clone the repository:


```
git clone https://github.com/GHROTIC/facefusion-3.3.2-backup
```



Ensure to enter the directory:

```
cd facefusion
```

### 5. Install The Application


```
python install.py --onnxruntime default
```

```
python install.py --onnxruntime cuda
```

```
python install.py --onnxruntime directml
```

```
python install.py --onnxruntime openvino
```

```
python install.py --onnxruntime rocm
```


### 6. Reload Your Environment

```
conda deactivate
```

```
conda activate facefusion
```

### 7. Done

Finally, run the program:

```
python facefusion.py run --open-browser
```

Usage
-----

Run the command:

```
python facefusion.py [commands] [options]

options:
  -h, --help                                      show this help message and exit
  -v, --version                                   show program's version number and exit

commands:
    run                                           run the program
    headless-run                                  run the program in headless mode
    batch-run                                     run the program in batch mode
    force-download                                force automate downloads and exit
    benchmark                                     benchmark the program
    job-list                                      list jobs by status
    job-create                                    create a drafted job
    job-submit                                    submit a drafted job to become a queued job
    job-submit-all                                submit all drafted jobs to become a queued jobs
    job-delete                                    delete a drafted, queued, failed or completed job
    job-delete-all                                delete all drafted, queued, failed and completed jobs
    job-add-step                                  add a step to a drafted job
    job-remix-step                                remix a previous step from a drafted job
    job-insert-step                               insert a step to a drafted job
    job-remove-step                               remove a step from a drafted job
    job-run                                       run a queued job
    job-run-all                                   run all queued jobs
    job-retry                                     retry a failed job
    job-retry-all                                 retry all failed jobs
```
