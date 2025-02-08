# t2i_for_aphasia

This repository contains the code for our paper "Exploring applicability of Text-to-Image models
for generating aphasia rehabilitation material".

### Project Structure 📂

```
t2i_for_aphasia/
├── src/                     
│   ├── image generation/           
│   │   ├── flux-schnell.ipynb                    # image generation using flux schnell
│   │   ├── sdxl-turbo.ipynb                      # image generation using sd turbo
│   │   └── stable-diffusion-xl-base.ipynb        # image generation using stable diffusion xl
│   ├── metric visualization/               
│   │   ├── visclipscore.ipynb                    # visualization code for the clip scores
│   │   ├── vistifa.ipynb                         # visualization code for the tifa scores
│   ├── metrics/               
│   │   ├── evalclipscore.ipynb                   # evaluation code for clip score
│   │   ├── evaltifa.ipynb                        # evaluation code for tifa score
│   │   └── evalis.ipynb                          # evaluation code for is
├── output/                   
│   ├── generated images/               
│   │   ├── DALL-E 2/                             # DALL-E 2 generated images
│   │   ├── Flux Schnell/                         # Flux Schnell generated images (contains both 512x512x3 and 1024x1024x3 image sizes)
│   │   └── SDXL Turbo/                           # SDXL Turbo generated images (contains both 512x512x3 and 1024x1024x3 image sizes)
│   │   └── SDXL/                                 # SDXL Turbo generated images (contains both 512x512x3 and 1024x1024x3 image sizes)
│   ├── metrics/               
│   │   ├── clip/                                 # clip scores as pkl file for both image sizes
│   │   ├── tifa/                                 # tifa scores as pkl file for both image sizes
├── README.md                                     # Project documentation
└── prompts.txt                                    # the prompts used to generate the images information
```


### Replicating the experiments
1. Image Generation: 
    - DALL-E: 
        - images (1024x1024x3) are taken from the work of [Pierce et al.](https://pubs.asha.org/doi/abs/10.1044/2023_AJSLP-23-00142). These images are resized to 512x512x3 and used for analysis at lower resolution as well.

    - [SDXL](https://github.com/mihirm05/t2i_for_aphasia/blob/main/src/image%20generation/stable-diffusion-xl-base.ipynb), [Flux Schnell](https://github.com/mihirm05/t2i_for_aphasia/blob/main/src/image%20generation/flux-schnell.ipynb), and [SD Turbo](https://github.com/mihirm05/t2i_for_aphasia/blob/main/src/image%20generation/sdxl-turbo.ipynb):
        - input: input text prompts and dimensions of images to be generated [(512x512x3) or (1024x1024x3)]
        - output: generated images as pkl files
       

2. T2I metric evaluation:
    - [IS](https://github.com/mihirm05/t2i_for_aphasia/blob/main/src/metrics/evalis.ipynb):
        - input:
            - DALL-E: generated images
            - SDXL, Flux Schnell, and SD Turbo: pkl files of the generated images
        - output: incetion score value

    - [CLIPScore](https://github.com/mihirm05/t2i_for_aphasia/blob/main/src/metrics/evalclipscore.ipynb):
        - input:
            - DALL-E: generated images
            - SDXL, Flux Schnell, and SD Turbo: pkl files of the generated images
        - output: pkl files containing the CLIPScore

    - [TIFA](https://github.com/mihirm05/t2i_for_aphasia/blob/main/src/metrics/evaltifa.ipynb):
        - input: generated images
        - output: pkl files containing the TIFA values

3. Metric score visualization:
    - [CLIPScore](https://github.com/mihirm05/t2i_for_aphasia/blob/main/src/metric%20visualization/visclipscore.ipynb):
        - input: CLIPScore pkl files from metric evaluation
        - output: scatter plots and histograms for models
    - [TIFA](https://github.com/mihirm05/t2i_for_aphasia/blob/main/src/metric%20visualization/vistifa.ipynb):
        - input: TIFA pkl files from metric evaluation
        - output: scatter plots and histograms for models

    
    