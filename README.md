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
└── prompt.txt                                    # the prompts used to generate the images information
```


### Replicating the experiments
1. Image Generation:
    - DALL-E: The images (1024x1024x3) are taken from the work of [Pierce et al.](https://pubs.asha.org/doi/abs/10.1044/2023_AJSLP-23-00142). These images are resized to 512x512x3
and used for analysis at lower resolution as well.
    - SDXL, Flux Schnell and SD Turbo notebooks yield pkl files. 