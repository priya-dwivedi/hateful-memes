## Hateful Memes Model

### Training using VisualBERT

I have uploaded 3 notebooks

1. ```Generate_Visual_Embeddings.ipynb``` - Used to generate visual features using Detectron2 and Mask RCNN. This is an input to Visual BERT. VisualBERT uses visual embeddings generated here and text embeddings from BERT

2. ```VisualBERT_trainer.ipynb``` - VisualBERT trainer. Uses huggingface implementation of VisualBERT and loads in pretrained weights on nlvr dataset. I added in a classification head to the model and trained it. Current best results are :
* val accuracy: 0.62
* val ROC: 0.57

3. ```Roberta_HatefulMemes.ipynb``` - Just classifies on text. This was to set a lower baseline. Uses Roberta model from Huggingface. Best results are:
* val accuracy: 0.58
* val ROC: 0.535

### Link to google drive 
The google drive below has the hateful memes dataset, features.pkl to run VisualBERT and the best_weights so far.
https://drive.google.com/drive/folders/12WMFJ1xr0jhCGSt7RNFDa9hDh9_AOdYR?usp=sharing

### In progress
* Above implementation detects 50 boxes per image and takes visual features from them. I am upgrading this to 100 boxes per image. mmf uses 100 boxes per image
* Adding in race, ethnicity and gender information using Fairface classifier

