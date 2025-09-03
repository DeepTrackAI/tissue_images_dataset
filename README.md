# Tissue Images Dataset (tissue_images_dataset)

## Overview

This DeepTrackAI repository provides a copy of the **Segmented anisotropic ssTEM dataset of neural tissue**,  
a dataset of serial section Transmission Electron Microscopy (ssTEM) prepared for training and evaluating image segmentation methods.

The content mirrors the public dataset by Gerhard et al., available from both the [Original GitHub repository](https://github.com/unidesigner/groundtruth-drosophila-vnc) and [figshare (DOI: 10.6084/m9.figshare.856713)](https://doi.org/10.6084/m9.figshare.856713).

The dataset contains 2 stacks of ssTEM images of the *Drosophila melanogaster* third instar larva ventral nerve cord. Each stack consists of 20 serial sections. The imaged volume measures approximately 4.7 × 4.7 × 1 μm³, with a voxel resolution of 4.6 × 4.6 × 45–50 nm³.

### Summary
- **Number of stacks**: 2 (1 training, 1 test)  
- **Sections per stack**: 20 (40 total)  
- **Image size**: 1024 × 1024 pixels    
- **Image format**: 8-bit grayscale TIFF  
- **Labels**: For each class, binary images; for multi-class segmentation, 8-bit images with pixel values encoding structure type (see table below).

---

## Original Source

- **Title**: Segmented anisotropic ssTEM dataset of neural tissue  
- **Authors**: Stephan Gerhard, Jan Funke, Julien Martel, Albert Cardona, Richard Fetter
- **Source**: [Original GitHub repository](https://github.com/unidesigner/groundtruth-drosophila-vnc), [figshare (DOI: 10.6084/m9.figshare.856713)](https://doi.org/10.6084/m9.figshare.856713)  
- **License**: [Creative Commons Attribution 3.0 (CC BY 3.0)](https://creativecommons.org/licenses/by/3.0/)

If you use this dataset in your research, please follow the licensing requirements and properly attribute the original authors.

---

## Dataset Structure

```bash
/tissue_images_dataset
├── stack1/                     # Training stack 
│   ├── raw/                    # Raw ssTEM images
│   │   ├── 00.png  
│   │   ├── 01.png  
│   │   └── ... 
│   ├── membranes/              # Binary segmentation masks: membranes 
│   │   ├── 00.png  
│   │   ├── 01.png  
│   │   └── ... 
│   ├── mitochondria/           # Binary segmentation masks: mitochondria 
│   │   ├── 00.png  
│   │   ├── 01.png  
│   │   └── ... 
│   ├── synapses/               # Binary segmentation masks: synapses 
│   │   ├── 00.png  
│   │   ├── 01.png  
│   │   └── ... 
│   └── labels/                 # Multi-class segmentation masks 
│       ├── labels00000000.png  
│       ├── labels00000001.png  
│       └── ... 
└── stack2/                     # Test stack 
    └── raw/                    # Raw ssTEM images
        ├── 00.png  
        ├── 01.png  
        └── ... 

```
Each filename is a sequential numerical identifier, consistent across raw and segmentation folders.
In the `labels/` directory, each pixel is assigned one of the following values:

| Value | Structure                          |
|-------|------------------------------------|
| 0     | Membrane (0°)                      |
| 32    | Membrane (45°)                     |
| 64    | Membrane (90°)                     |
| 96    | Membrane (135°)                    |
| 128   | Membrane junction                  |
| 159   | Glia / Extracellular               |
| 191   | Mitochondria                       |
| 223   | Synapse                            |
| 255   | Intracellular                      |

---

## How to Access the Data

### Clone the Repository
```bash
git clone https://github.com/DeepTrackAI/tissue_images_dataset
cd tissue_images_dataset
```

---

## Attribution

This replication dataset is based on the original Segmented anisotropic ssTEM dataset of neural tissue dataset. When using this replication, please cite the original dataset.

### Cite the dataset:
Gerhard S, Funke J, Martel J, Cardona A, Fetter R. *Segmented anisotropic ssTEM dataset of neural tissue.* figshare. DOI: [10.6084/m9.figshare.856713](https://doi.org/10.6084/m9.figshare.856713)

```bibtex
@misc{gerhard2013sstem,
  title        = {Segmented anisotropic ssTEM dataset of neural tissue},
  author       = {Gerhard, Stephan and Funke, Jan and Martel, Julien and Cardona, Albert and Fetter, Richard},
  howpublished = {figshare},
  year         = {2013},
  doi          = {10.6084/m9.figshare.856713}
}
```

---

## License

This replication dataset is shared under the **Creative Commons Attribution-NonCommercial-ShareAlike 3.0 Unported** License, following the original licensing terms.
