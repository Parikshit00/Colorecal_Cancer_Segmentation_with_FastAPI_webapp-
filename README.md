# Description

A FastAPI WebApp for colorectal cancer segmentation with torch version of `Metapolyp` and `AttentionR2Unet`. The dataset of gastrointestinal polyp images and corresponding segmentation masks, manually annotated and verified by an experienced gastroenterologist is from ![PraNet](https://github.com/DengPingFan/PraNet), with training set from 50% of Kvasir-SEG and 50% of ClinicDB dataset.

The dataset download link can be found at ![Google drive](https://drive.google.com/drive/folders/10SYLHNvO0fSrhhVhj5U-cFgOnTH5uGJf)


The dataset consists of rgb images of regions of colon and a mask image to highlight the tumor areas.

![Dataset](/media/dataset.png)

# Models
1. **MetapolyP:** The code provides an implementation of the Meta-Polyp baseline model for polyp segmentation in `torch`. This model architecture is detailed in the ![original paper](https://arxiv.org/pdf/2305.07848v3.pdf).
   The folder `train_metapoly` consistes of model and its layer (converted to torch from its official tensorflow implemtation) inside `model.py`and `layers` folder respectively.
   To run the trainer, download the train dataset from google drive and place it inside as `train_metapoly/TrainDataset` and just run `python train.py`.
   ![model_metapoly](/media/model1.png)
3. **AttentionR2Unet:**
   The model that has been used is an advanced version of Unet which is a combination of `R2Unet` and `Attention UNet`. The model architecture looks as follows:
  ![model](/media/model.png)


# Citations
@inproceedings{jha2020kvasir, title={Kvasir-seg: A segmented polyp dataset}, author={Jha, Debesh and Smedsrud, Pia H and Riegler, Michael A and Halvorsen, P{\aa}l and de Lange, Thomas and Johansen, Dag and Johansen, H{\aa}vard D}, booktitle={International Conference on Multimedia Modeling}, pages={451--462}, year={2020}, organization={Springer} }  

@misc{trinh2023metapolyp,
      title={Meta-Polyp: a baseline for efficient Polyp segmentation}, 
      author={Quoc-Huy Trinh},
      year={2023},
      eprint={2305.07848},
      archivePrefix={arXiv},
      primaryClass={eess.IV}
}
