# Drag Your GAN: Interactive Point-based Manipulation on the Generative Image Manifold

<p align="center">
    <img src="DragGAN.gif", width="700">
</p>

**Figure:** *Drag your GAN.*

> **Drag Your GAN: Interactive Point-based Manipulation on the Generative Image Manifold** <br>
> Xingang Pan, Ayush Tewari, Thomas Leimkühler, Lingjie Liu, Abhimitra Meka, Christian Theobalt<br>
> *SIGGRAPH 2023 Conference Proceedings*

## Requirements

* Linux and Windows are supported, but we recommend Linux for performance and compatibility reasons.
* 1&ndash;8 high-end NVIDIA GPUs with at least 12 GB of memory. We have done all testing and development using Tesla V100 and A100 GPUs.
* 64-bit Python 3.8 and PyTorch 1.9.0 (or later). See https://pytorch.org for PyTorch install instructions.
* CUDA toolkit 11.1 or later.  (Why is a separate CUDA toolkit installation required?  See [Troubleshooting](./docs/troubleshooting.md#why-is-cuda-toolkit-installation-necessary)).
* GCC 7 or later (Linux) or Visual Studio (Windows) compilers.  Recommended GCC version depends on CUDA version, see for example [CUDA 11.4 system requirements](https://docs.nvidia.com/cuda/archive/11.4.1/cuda-installation-guide-linux/index.html#system-requirements).
* Python libraries: see [environment.yml](./environment.yml) for exact library dependencies.  You can use the following commands with Miniconda3 to create and activate your StyleGAN3 Python environment:
  - `conda env create -f environment.yml`
  - `conda activate stylegan3`
* Docker users:
  - Ensure you have correctly installed the [NVIDIA container runtime](https://docs.docker.com/config/containers/resource_constraints/#gpu).
  - Use the [provided Dockerfile](./Dockerfile) to build an image with the required library dependencies.

The code relies heavily on custom PyTorch extensions that are compiled on the fly using NVCC. On Windows, the compilation requires Microsoft Visual Studio. We recommend installing [Visual Studio Community Edition](https://visualstudio.microsoft.com/vs/) and adding it into `PATH` using `"C:\Program Files (x86)\Microsoft Visual Studio\<VERSION>\Community\VC\Auxiliary\Build\vcvars64.bat"`.

See StyleGan3's [Troubleshooting](./docs/troubleshooting.mdhttps://github.com/NVlabs/stylegan3/blob/main/docs/troubleshooting.md) for help on common installation and run-time problems.

## Download pre-trained StyleGAN2 weights

To download pre-trained weights, simply run:
```sh
sh scripts/download_model.sh
```
If you want to try StyleGAN-Human and the Landscapes HQ (LHQ) dataset, please download weights from these links: [StyleGAN-Human](https://drive.google.com/file/d/1dlFEHbu-WzQWJl7nBBZYcTyo000H9hVm/view?usp=sharing), [LHQ](https://drive.google.com/file/d/16twEf0T9QINAEoMsWefoWiyhcTd-aiWc/view?usp=sharing), and put them under `./checkpoints`.  

Feel free to try other pretrained StyleGAN.

## Run DragGAN GUI

To start the DragGAN GUI, simply run:
```sh
sh scripts/gui.sh
```

This GUI supports editing GAN-generated images. To edit a real image, you need to first perform GAN inversion using tools like [PTI](https://github.com/danielroich/PTI). Then load the new latent code and model weights to the GUI.

## Acknowledgement

This code is developed based on [StyleGAN3](https://github.com/NVlabs/stylegan3). Part of the code is borrowed from [StyleGAN-Human](https://github.com/stylegan-human/StyleGAN-Human).

## License

The code related to the DragGAN algorithm is licensed under [CC-BY-NC](https://creativecommons.org/licenses/by-nc/4.0/).
However, most of this project are available under a separate license terms: all codes used or modified from [StyleGAN3](https://github.com/NVlabs/stylegan3) is under the [Nvidia Source Code License](https://github.com/NVlabs/stylegan3/blob/main/LICENSE.txt).

Any form of use and derivative of this code must preserve the watermarking functionality.

## BibTeX

```bibtex
@inproceedings{pan2023draggan,
    title={Drag Your GAN: Interactive Point-based Manipulation on the Generative Image Manifold}, 
    author={Pan, Xingang and Tewari, Ayush, and Leimk{\"u}hler, Thomas and Liu, Lingjie and Meka, Abhimitra and Theobalt, Christian},
    booktitle = {ACM SIGGRAPH 2023 Conference Proceedings},
    year={2023}
}
```
