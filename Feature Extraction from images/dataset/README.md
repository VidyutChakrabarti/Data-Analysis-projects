### Download images
In order to download the images from the urls given in the csv files run this code in a notebook in local desktop:

1. Import necessary libraries:
```bash
import os
import pandas as pd
```

2. Create necessary folders for storing the images: 
```bash
DATASET_FOLDER = '../dataset/'
train = pd.read_csv(os.path.join(DATASET_FOLDER, 'train.csv'))
test = pd.read_csv(os.path.join(DATASET_FOLDER, 'test.csv'))
sample_test = pd.read_csv(os.path.join(DATASET_FOLDER, 'sample_test.csv'))
sample_test_out = pd.read_csv(os.path.join(DATASET_FOLDER, 'sample_test_out.csv'))
```

3. Before downloading check if the csv files are in the right format: 
```bash
!python sanity.py --test_filename ../dataset/sample_test.csv --output_filename ../dataset/sample_test_out.csv
```

4. Download the images: 
```bash 
from utils import download_images
download_images(sample_test['image_link'], '../images')
```

5. Check if properly downloaded or not: 
```bash
assert len(os.listdir('../images')) > 0
```
