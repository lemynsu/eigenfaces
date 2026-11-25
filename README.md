# Eigenfaces

Principal component analysis on 400 face photos: compress each 64×64 image to 20 numbers, rebuild it, and look at what those numbers capture.

![The mean face, the first eight eigenfaces, and faces rebuilt from 20 numbers each](images/eigenfaces.png)

## What it does

- Loads the Olivetti faces: 400 grayscale photos, 40 people, 10 photos each.
- Subtracts the mean face so only what makes each face different is left.
- Fits PCA with 20 components, taking every face from 4,096 pixel values down to 20 weights.
- Draws the components as images (the eigenfaces), rebuilds every face from its weights, and measures the error.
- Walks from the mean face along each of the first four eigenfaces to show what each direction encodes.

## Results

| | 20 components | 150 components |
| --- | --- | --- |
| Largest reconstruction error (L2 norm) | 6.25 | 2.10 |

Twenty components keep 76.3% of the variance in the faces, and the first component alone keeps 23.8%.

## Run it

```bash
pip install -r requirements.txt
jupyter notebook eigenfaces.ipynb
```

The dataset downloads on first run through scikit-learn.

## Stack

Python, NumPy, pandas, scikit-learn, Matplotlib.

The face photos are the Olivetti faces from AT&T Laboratories Cambridge, loaded through scikit-learn.
