Audio-Classification


Pipeline for prototyping audio classification algorithms with TF 2.3


### Environment

```
conda create -n audio python=3.7
activate audio
pip install -r requirements.txt
```

### Jupyter Notebooks

Assuming you have ipykernel installed from your conda environment

`ipython kernel install --user --name=audio`

`conda activate audio`

`jupyter-notebook`

### Audio Preprocessing

clean.py can be used to preview the signal envelope at a threshold to remove low magnitude data

When you uncomment split_wavs, a clean directory will be created with downsampled mono audio split by delta time

`python clean.py`

![signal envelope](docs/signal_envelope.png)

### Training

Change model_type to: conv1d, conv2d, lstm

Sample rate and delta time should be the same from clean.py

`python train.py`

### Plot History

Assuming you have ran all 3 models and saved the images into logs, check `notebooks/Plot History.ipynb`

![history](docs/model_history.png)

`notebooks/Confusion Matrix and ROC.ipynb`

### Confusion Matrix

![conf_mat](docs/conf_mat.png)

### Receiver Operating Characteristic

![roc](docs/roc.png)

### Kapre

For computation of audio transforms from time to frequency domain on the fly

https://github.com/keunwoochoi/kapre  
https://arxiv.org/pdf/1706.05781.pdf
