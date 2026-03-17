## Installation

Follow the steps below to set up the environment and install **MinkowskiEngine** with CUDA 13.0 support.

### 1. Create and activate a new Conda environment
```bash
conda create -n mink-cu13 python=3.10
conda activate mink-cu13
````

### 2. Install dependencies

```bash
# Install OpenBLAS
conda install openblas-devel -c anaconda

# Install PyTorch compatible with CUDA 13.0
pip install torch torchvision

# (Recommended) Install the CUDA toolkit
conda install nvidia/label/cuda-{version}::cuda-toolkit
```

### 3. Clone and install MinkowskiEngine

```bash
git clone https://github.com/AzharSindhi/MinkowskiEngineCuda13.git
cd MinkowskiEngineCuda13

# Set CUDA home path and install
export CUDA_HOME=$CONDA_PREFIX
python setup.py install --blas=openblas
```

---

### Notes

* Ensure that your GPU drivers are compatible with **CUDA 13.0**.
* The `--blas=openblas` flag is used to build with OpenBLAS support for optimal performance.
* For troubleshooting or performance tuning, refer to the official [MinkowskiEngine documentation](https://github.com/NVIDIA/MinkowskiEngine).

## References

This repository is adapted from [CiSong10/MinkowskiEngine](https://github.com/CiSong10/MinkowskiEngine), which was modified for **CUDA 12.8**. However, that version did not function correctly in my setup, likely due to the need for root permissions to install OpenBLAS (e.g., using `sudo apt install build-essential python3-dev libopenblas-dev`). Additionally, issues persisted with **nvtx3**, even after following the recommended installation steps.

This repository provides an updated configuration intended to resolve both of these issues.


## Citing Minkowski Engine

If you use the Minkowski Engine, please cite:

- [4D Spatio-Temporal ConvNets: Minkowski Convolutional Neural Networks, CVPR'19](https://arxiv.org/abs/1904.08755), [[pdf]](https://arxiv.org/pdf/1904.08755.pdf)

```
@inproceedings{choy20194d,
  title={4D Spatio-Temporal ConvNets: Minkowski Convolutional Neural Networks},
  author={Choy, Christopher and Gwak, JunYoung and Savarese, Silvio},
  booktitle={Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition},
  pages={3075--3084},
  year={2019}
}
```

For multi-threaded kernel map generation, please cite:

```
@inproceedings{choy2019fully,
  title={Fully Convolutional Geometric Features},
  author={Choy, Christopher and Park, Jaesik and Koltun, Vladlen},
  booktitle={Proceedings of the IEEE International Conference on Computer Vision},
  pages={8958--8966},
  year={2019}
}
```

For strided pooling layers for high-dimensional convolutions, please cite:

```
@inproceedings{choy2020high,
  title={High-dimensional Convolutional Networks for Geometric Pattern Recognition},
  author={Choy, Christopher and Lee, Junha and Ranftl, Rene and Park, Jaesik and Koltun, Vladlen},
  booktitle={Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition},
  year={2020}
}
```

For generative transposed convolution, please cite:

```
@inproceedings{gwak2020gsdn,
  title={Generative Sparse Detection Networks for 3D Single-shot Object Detection},
  author={Gwak, JunYoung and Choy, Christopher B and Savarese, Silvio},
  booktitle={European conference on computer vision},
  year={2020}
}
```
